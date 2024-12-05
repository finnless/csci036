**Cheat Sheet for Data Science Exam**

---

**Linear Models**
- **Equation**:   `y = c₁ + c₂·x`

**Residuals**
- **Residual**:  `actual - predicted`
  - **Positive**: Model underpredicts
  - **Negative**: Model overpredicts
- **Calculate Residuals**:
  ```r
  data %>%
    mutate(prediction = c₁ + c₂·x) %>%
    mutate(residual = y - prediction)
  ```

**Comparing Models**
- **Sum of Absolute Residuals**: `sum(abs(residual))`
- **Sum of Squared Residuals**: `sum(residual^2)`
- **Best Model**: Use `lm()` to minimize ∑(residuals²)
  ```r
  model <- lm(y ~ x, data)
  ```

**Extract Coefficients**
- `model$coefficients`

**Plotting Model**
- ```r
  ggplot(data) +
    geom_point(aes(x, y)) +
    geom_abline(intercept = model$coefficients[1],
                slope = model$coefficients[2])
  ```

**Model Functions**
- **Add Predictions**: `data %>% add_predictions(model)`
- **Add Residuals**: `data %>% add_residuals(model)`

**Assessing Models**
- **Residuals Plot**: No patterns; residuals ~ N(0, σ²)
  ```r
  ggplot(data) + geom_density(aes(residual))
  ```

**Correlation**
- **Correlation Coefficient (r)**: -1 ≤ r ≤ 1
  - **r = +1**: Perfect positive linear
  - **r = -1**: Perfect negative linear
  - **r = 0**: No linear relationship
- **R² (Coefficient of Determination)**:
  - Proportion of variance explained
  - ```r
    summary(model)$r.squared
    ```

---

**Non-linear Models**

**Quadratic Model**
- Equation: `y = c₁ + c₂·x + c₃·x²`
- **Create x² Term**:
  ```r
  data %>%
    mutate(x2 = x^2)
  ```
  or
  ```r
  model <- lm(y ~ x + I(x^2), data)
  ```

**Cubic Model**
- Includes x³ term similarly

**Splines**
- **Natural Splines**:
  ```r
  model <- lm(y ~ ns(x, df), data)
  ```
  - `ns()`: Natural spline with degrees of freedom `df`
- **Plotting Splines**:
  ```r
  data %>%
    gather_predictions(model) %>%
    ggplot() +
    geom_point(aes(x, y)) +
    geom_line(aes(x, pred), color = "red")
  ```
- **Overfitting**: Avoid high `df`; may not generalize well

---

**Categorical Variables in Models**
- **Include Categorical Predictors**:
  ```r
  model <- lm(y ~ factor_var, data)
  ```
- **Predictions**: Group means for each category
- **Convert Numeric to Factor**:
  ```r
  data %>% mutate(var = as.factor(var))
  ```

**Variables as Numeric or Categorical**
- Decide based on context (e.g., time sequence vs. groups)

---

**Models with Multiple Predictors**

**Two Numerical Predictors**
- **Without Interaction**:
  ```r
  model <- lm(y ~ x1 + x2, data)
  ```
- **With Interaction**:
  ```r
  model <- lm(y ~ x1 * x2, data)
  ```

**One Numerical and One Categorical Predictor**
- **Model**:
  ```r
  model <- lm(y ~ num_var * factor_var, data)
  ```
- **Plotting Predictions**:
  ```r
  data %>%
    gather_predictions(model) %>%
    ggplot() +
    geom_line(aes(num_var, pred, color = factor_var))
  ```

---

**Data Transformations and Residuals**

**Log Transformations**
- **Power Law**: `log(y) = c₁ + c₂·log(x)`
  - Transform both x and y
- **Exponential**: `log(y) = c₁ + c₂·x`
  - Transform y
- **Example**:
  ```r
  data %>%
    mutate(log_y = log(y),
           log_x = log(x)) %>%
    lm(log_y ~ log_x, data = .)
  ```
- **Original Equation**: `y = e^(intercept) · x^(slope)`

**Using Residuals**
- Helps identify effects of other variables
- **After Modeling**:
  ```r
  data %>%
    add_residuals(model) %>%
    ggplot() +
    geom_point(aes(other_var, residual))
  ```

---

**Overfitting and Data Splitting**

**Overfitting**
- Model fits training data too closely
- **Detection**:
  - Split data into training/test sets
  - Compare performance on unseen data

**Training/Test Split**
- **Split Data**:
  ```r
  set.seed(123)
  training <- sample_frac(data, 0.8)
  testing <- setdiff(data, training)
  ```
- **Evaluate Model**:
  ```r
  model <- lm(y ~ predictors, data = training)
  testing %>%
    add_predictions(model) %>%
    summarize(MSE = mean((y - pred)^2))
  ```

---

**Predicting Categorical Outcomes**

**Logistic Regression**
- **Binary Outcome** (0/1)
- **Model**:
  ```r
  model <- glm(y ~ predictors, data, family = "binomial")
  ```
- **Predictions**:
  ```r
  data %>%
    add_predictions(model, type = "response") %>%
    mutate(pred_class = if_else(pred >= 0.5, 1, 0))
  ```
- **Assess Accuracy**:
  ```r
  summarize(accuracy = mean(pred_class == y))
  ```

**Support Vector Machines (SVM)**
- **Classification** for two classes
- **Linear Kernel**:
  ```r
  model <- svm(class ~ x1 + x2, data, kernel = "linear")
  ```
- **Non-linear (Radial) Kernel**:
  ```r
  model <- svm(class ~ x1 + x2, data, kernel = "radial", cost = C)
  ```
- **Predictions**:
  ```r
  predictions <- predict(model, newdata)
  ```

---

**Key Functions & Packages**

- **lm()**: Linear models
- **glm()**: Generalized linear models
- **ns()**: Natural splines (`splines` package)
- **add_predictions()**: From `modelr` package
- **add_residuals()**: From `modelr` package
- **data_grid()**: Creates grid of predictor values
- **svm()**: Support Vector Machine (`e1071` package)
- **mutate()**, **ggplot()**, **geom_point()**, **geom_line()**: From `tidyverse`

**General Tips**

- Always check residuals for patterns
- Be cautious of overfitting; validate with test data
- Transform variables to linearize relationships when appropriate
- For categorical variables, ensure correct data type (`factor`)
- When in doubt, plot your data and model predictions!

---

*(End of Cheat Sheet)*