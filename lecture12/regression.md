# Regression practice

## Multiple choice questions

### In linear regression, what is the variable that we are trying to predict called?

A. Independent variable

B. Dependent variable

C. Control variable

D. Confounding variable

### Which of the following is true about the slope coefficient in a simple linear regression model?

A. It represents the average value of the dependent variable.

B. It represents the change in the dependent variable for a one-unit increase in the independent variable.

C. It represents the standard deviation of the dependent variable.

D. It represents the correlation between the dependent and independent variables.

### What does the R-squared value tell us about a linear regression model?

A. The strength of the relationship between the independent and dependent variables.

B. The average error in the predicted values.

C. The proportion of the variance in the dependent variable that is explained by the independent variable.

D. The proportion of the variance in the independent variable that is explained by the dependent variable.

### What is the range of possible values for R-squared?

A. -1 to 1

B. 0 to 1

C. 0 to infinity

D. -infinity to infinity

### In hypothesis testing for linear regression, what is the null hypothesis?

A. There is no significant relationship between the independent and dependent variables.

B. There is a significant relationship between the independent and dependent variables.

C. The slope of the regression line is zero.

D. The intercept of the regression line is zero.


## Coding questions

Commands from lecture:
```
# perform linear regression
model <- lm(wt ~ ht, data = ais)
summary(model)

# plot add the linear regression line to a plot in ggplot
ggplot(ais, aes(ht, wt)) +
  geom_point() +
  geom_smooth(method=lm)
```

1. Using `ht` as the independent variable, perform regressions with several other quantitative variables in the dataset as dependent variables. Which has the highest $R^2$ value? Which has the lowest standard error?
2. For each of these regressions, use `ggplot` to plot the variables against each other and add in the regression line.
