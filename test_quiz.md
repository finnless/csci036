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

# 11-18 Class Notes Linear Models Two Variables

## Modelling with Two Predictor Variables

### Example: sim4 Data Set

**Model Formula**: y = c1 + c2 * x1 + c3 * x2

```r
sim4_mod <- lm(y ~ x1 + x2, data = sim4)
```

- Visualize using `geom_line` to plot slices by fixing one variable and varying the other.
- Use `data_grid` to get combinations of predictors without duplicates.

```r
data_grid(sim4, x1, x2) %>% add_predictions(sim4_mod)
```

### Plotting Example

```r
data_grid(sim4, x1, x2) %>% ggplot() + 
  geom_line(aes(x = x1, y = pred, color = x2, group = x2))
```

- All lines have the same slope, different intercept for each value of x2.

## Modeling: Two Numerical Variables with Interactions

**Model Formula with Interaction**: y = c1 + c2 * x1 + c3 * x2 + c4 * x1 * x2

```r
sim4_interaction <- lm(y ~ x1 * x2, data = sim4)
```

- Opt to include interaction terms when slopes should depend on another variable.

### Plot Interaction Data

```r
data_grid(sim4, x1, x2) %>% 
  add_predictions(sim4_interaction) %>% 
  ggplot() + geom_line(aes(x = x1, y= pred, color = x2, group = x2))
```

- Lines now have different slopes due to the interaction term.

### Visualization with geom_tile

```r
data_grid(sim4, x1, x2) %>% 
  add_predictions(sim4_interaction) %>% 
  ggplot() + geom_tile(aes(x = x1, y = x2, fill = pred))
```

**seq_range**: Use to sample evenly across the range of a variable.

```r
dg5 <- sim4 %>% data_grid(
  x1 = seq_range(x1, 5), 
  x2 = seq_range(x2, 5)
)
```

## Models with One Categorical and One Numerical Predictor

### Example: sim3 Data Set

```r
sim3_preds <- sim3 %>% data_grid(x1, x2) %>% gather_predictions(mod_wo_int, mod_int)
```

- Compare models with and without interaction:

```r
mod_wo_int <- lm(y ~ x1 + x2, data = sim3)
mod_int <- lm(y ~ x1 * x2, data = sim3)
```

### Model Visualization using Facets

```r
sim3_preds %>%
  ggplot() + geom_line(aes(x = x1, y = pred, color = x2)) + 
  geom_point(data = sim3, aes(x = x1, y = y, color = x2)) + 
  facet_wrap(~ model)
```

### Residuals Check

```r
sim3 %>% 
  gather_residuals(mod_int, mod_wo_int) %>% 
  ggplot() + geom_point(aes(x = x1, y = resid, color = x2)) + 
  facet_grid(x2 ~ model)
```

- Check for patterns in residuals to determine the better model.

## Models with Two Categorical Predictors

- Works similarly to having one categorical predictor but involves combinations of categorical levels.

# 11-20 Class Notes: Data Transformations, Residuals, Overfitting

## Key Concepts

### Data Transformations

- **Logarithms**: Useful for transforming polynomial models into linear models.
  - Conversion: log(y) = log(a1) + a2 log(x)
- **Example**: Using diamonds dataset, we can transform price prediction to a linear relationship using log transformations.
  - Transform using R: `log2(price) = log2(a1) + a2 * log2(carat)`

```{r}
diamonds3 <- diamonds2 %>% mutate(lprice = log2(price), lcarat = log2(carat))
lmod <- lm(lprice ~ lcarat, data = diamonds3)
# Model equation: log2(price) = 12.194 + 1.681 * log2(carat)
# Reconstruct original equation: price = a1 * carat^a2
a1 <- 2^(lmod$coefficients[1])
a2 <- lmod$coefficients[2]
```

### Logarithmic and Exponential Models

- **Logarithmic Model**: `y = c1 + c2 * log(x)`
- **Exponential Model**: `y = a * b^x` when `log(y) = c1 + c2 * x`
- Determine model type by visual inspection of graphs:
  - If y vs. log(x) or log(y) vs. x appears linear.

### Explaining One Variable with Another

- Use residuals to determine what part of a variable's change isn't explained by another known variable.
- Example: Removing dependence on `carat` to understand `price` influences by cut and clarity.

```{r}
diamonds4 <- diamonds3 %>% 
  mutate(pred_price = a1 * carat^a2) %>% 
  mutate(residual = price - pred_price)
# Analyze residuals using boxplots by `cut` or `clarity`
diamonds4 %>% ggplot() + geom_boxplot(aes(x = cut, y = residual))
```

### Overfitting

- Occurs when a model fits the training data too well but performs poorly on new data.
- **Detection**: Split data into training and test sets, and compare residual sum of squares.

```{r}
training_data <- sim6
test_data <- sim6_new
# Compare mean residuals
training_resid <- training_data %>% add_residuals(mod20) %>% summarize(mean(resid^2))
test_resid <- test_data %>% add_residuals(mod20) %>% summarize(mean(resid^2))
```

### Training/Test Data

- Dividing data ensures model evaluation accuracy.
- Typical splits: 70-80% training, 20-30% test.
- Use random sampling or stratification based on context.

```{r}
dtraining <- sample_n(diamonds3, nrow(diamonds3) * 0.8)
dmod2 <- lm(lprice ~ lcarat + cut + clarity, data = dtraining)
```

## Discussion

Understand the nature of your data:
- Transform variables to linear relationships when necessary.
- Recognize overfitting through cross-validation (train/test evaluation).
- Use residuals to uncover hidden relationships and ensure model validity.


# 11-25 Class Notes - Predicting Categorical Variables

## Logistic Regression

Predicts probability p of an outcome being 1 using glm() [generalized linear models] with family set to "binomial". Transformations are applied to ensure predictions range between 0 and 1.

Example Usage:

```{r}
mod_logit <- glm(y ~ x, data = ex, family = "binomial")
```

Add predictions with a transformed probability scale:

```{r}
ex %>% add_predictions(mod_logit, type = "response")
```

Simple prediction method: If predicted p >= 0.5, predict 1; otherwise, predict 0.

Assess model accuracy by fraction of correct predictions:

```{r}
ex_preds %>% summarize(frac_correct = mean(predicted_outcome == y))
```

## Multiple Predictor Variables

Logistic regression works with multiple predictor variables, including categorical types.

Example Data:

```{r}
mod2 <- glm(class ~ x + y, data = df, family = "binomial")
```

## Support Vector Machines

Classify data into two categories using svm() from e1071 package. Models can classify using hyperplanes.

Example Usage:

```{r}
mod_svm <- svm(class ~ x + y, data = df, kernel = "linear")
```

Plot predictions made by the SVM:

```{r}
dg %>% add_predictions(mod_svm) %>% 
  ggplot() + geom_point(aes(x, y, color = pred), alpha = 0.05)
```

For non-linear separations, customize kernel and cost parameters:

```{r}
mod_svm4 <- svm(class ~ x + y, data = df3, scale = FALSE, kernel = "radial", cost = 5)
```

