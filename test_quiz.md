1. Download 12-2 quiz information and review from canvas

TODO:
Things I don't understand:
 - add_predictions
 - add_residuals
 - data_grid()


# Modelling Day 1 - Complete Notes

## Linear Models

Linear Model: y = c1 + c2 * x 

### Assessing Models: Residuals

Residual: Actual data value - predicted data value

Positive Residual: model *underpredicts* - actual value is higher than predicted value
Negative is inverse

calculate all residuals example: 

```{r, results = FALSE}
childcare_costs_ca %>% 
  mutate(prediction = -400 + 10 *flfpr_20to64 ) %>%
  mutate(residual = mc_infant - prediction)
```

If all your y-values are between 0 and 1: a residual of 5 is terrible!   
If your y-values range from 10,000 to 80,000: a residual of 5 is great!
Residuals for different data are not comparable.

### Comparing Models

Option 1: SUm the absolute values of the residuals

```{r, results = FALSE}
childcare_costs_ca %>% 
  mutate(prediction = -400 + 10 *flfpr_20to64 ) %>%
  mutate(residual = mc_infant - prediction) %>% 
  summarize(sum(abs(residual)))
```

On its own, this tell us nothing! 
(only compare this number to other models for the same data, aggregating the residuals in the same way)

Option 2: Sum the squares of the residuals

```{r, results = FALSE}
childcare_costs_ca %>% 
  mutate(prediction = -400 + 10 *flfpr_20to64 ) %>%
  mutate(residual = mc_infant - prediction) %>%
  summarize(sum(residual^2))
```


### Finding the *best* model according to some criteria: lm()

For sum(residuals^2): Use lm() function 

Format: lm(y_col ~ x_col, data = dataset_name_here)

```{r, results = FALSE}
childcare_model <- lm(mc_infant ~ flfpr_20to64, data = childcare_costs_ca)
childcare_model
# To get coefficients of model: 
childcare_model$coefficients
```

For example, can use this and geom_abline() to plot the model: 

```{r, results = FALSE}
childcare_costs_ca %>% 
  ggplot() + 
  geom_point(aes(x = flfpr_20to64, y = mc_infant)) + 
  geom_abline(aes(intercept = childcare_model$coefficients[1], 
                  slope = childcare_model$coefficients[2]))
```

### Helpful modelR functions - for models made with lm()

*add_predictions*: takes in a data set with a column that has the same name as the predictor variable, and adds a new column with what the model predicts for those values. 

```{r, results = 'hide'}
childcare_costs_ca %>% add_predictions(childcare_model)


rates <- tibble(flfpr_20to64 = c(60, 65, 70, 75, 80))
rates 
rates %>% add_predictions(childcare_model)
```

*add_residuals*: takes takes in a data set with a column that has the same name as the predictor variable AND a column that has the same name as the predicted variable, and adds a new column with the residuals

```{r, results = 'hide'}
childcare_costs_ca %>% add_residuals(childcare_model) 

## This command won't work - need actual data values too to be able to calculate residuals
rates %>% add_residuals(childcare_model)
```

### Assessing models by Plotting Residuals

Even if you know a model is "best" according to some criteria, does that mean it's a good model? No, not necessarily.  

(1) Want there to be no patterns in the residuals. 

Model shouldn't consistently overestimate certain parameter ranges and consistently underestimate other parameter ranges. Sometimes data is not linear, so a linear model may not be the best fit. 

(2) Residuals should be normally distributed (look like a "Bell Curve") centered around 0: 

That residuals are distributed this way is an assumption made by the lm function

If your residuals are far from normally distributed, that's a sign using the lm function maybe wasn't the best choice
(your data has "skew")

example plot of residuals:

```{r, results = FALSE}
#For childcare model 
ggplot(childcare_costs_ca_resids) + geom_density(aes(x = resid))
```

### Correlation

*is* comparable across different models

*Correlation*: A number between -1 and 1 that describes how linearly related two variables are (Mathematically: a scaled version of covariance)

r = +1: a perfect line with (any) positive slope

r = -1: a perfect line with (any) negative slope 

Correlation = 0: Doesn't imply there's no relationship between the two variables, it just says there's not a linear relationship. 

Square of the correlation = R^2 value = "Coefficient of determination" = how much of the variance int the y-variable (dependent variables) can be explained by the x-variable (independent variable). 

Can get from the output of an lm function using summary.

```{r, results = 'hide', fig.show='hide'}
summary(childcare_model)
summary(childcare_model)$r.square
```

Remember: Correlation does not mean causation!



# 11-13 Class Notes - Non-linear Models and Categorical Variables

## Non-linear Models

### Quadratic and Cubic Models

- **Quadratic Model**: y = c1 + c2*x + c3*x^2 
  - Use when data looks like a parabola.
- **Cubic Model**: y = c1 + c2*x + c3*x^2 + c4*x^3 
  - Use when there are three distinct trends.

**Methods:**
- Use `mutate` to create x^2, x^3 columns.
- Use `I()` within `lm()`.

Recommendation: Try a linear model first and examine residuals.

### Splines

Use piece-wise polynomial curves for modeling `ns(xcol, df)`.
```{r}
mod1 <- lm(y ~ ns(x, 1), data = sim6)  # 1 degree of freedom
```
- Increase degrees of freedom for better curve fitting.

Plotting example:
```{r}
sim6 %>% 
  gather_predictions(mod1, mod2, mod3, mod4, mod5) %>% 
  ggplot() +
  geom_point(aes(x,y)) + geom_line(aes(x = x, y = pred), color = "red") +
  facet_wrap(~ model)
```
**Drawbacks**: No precise equation, and the right number of degrees of freedom is ambiguous. Better for trends than predictions.

### Overfitting

Occurs when the model fits the data too closely and fails on new data.

Example of overfitting with 20 degrees of freedom:
```{r}
mod20 <- lm(y ~ ns(x, 20), sim6)
```

## Categorical Models

Handle variables that might be either numeric or categorical based on context.

For the `sim2` data set:
```{r}
mod2 <- lm(y ~ x, data = sim2)
```
**Function**:
- `data_grid()`: Gets all unique values for a predictor variable.

**Example**:
```{r}
grid <- data_grid(sim2, x) %>% add_predictions(mod2)
```
Predictions are just the averages for each category.

### Variables That Could be Numeric or Categorical

Consider whether the variable should be treated as sequential or independent.

- **Numeric Example**: Yearly trends.
- **Categorical Example**: Graduation year as a class year.

**Transformations**:
- Numeric: Treat as number for sequential data.
- Categorical: Convert to factor or character for independent predictions.

Example with graduation year:
```{r}
ice_cream2 <- ice_cream %>% mutate(grad_year = as.character(grad_year))
imod <- lm(ice_cream_amount ~ grad_year, data = ice_cream2)
```


# TODO: copy from chat. Then convert next 3 notes. Then review all while writing on sheet.


https://platform.openai.com/playground/chat?preset=CNYispQdpoLHnCqv360qWC03