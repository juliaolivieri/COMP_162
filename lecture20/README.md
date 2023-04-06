# Classwork for Lecture 20

## Classwork 1

1. If a machine learning task involves predicting the percentage of a student's score in an exam, which type of task is it?
   1. Regression
   1. Classification
1. If a machine learning task involves predicting whether a customer will make a purchase or not, which type of task is it?
   1. Regression
   1. Classification
1. If a machine learning task involves predicting a person's age based on their social media usage, given a dataset with ages and corresponding social media usage data, which type of learning is it?
   1. Supervised learning
   1. Unsupervised learning
1. If a machine learning task involves grouping similar news articles together without prior knowledge of their categories, which type of learning is it?
   1. Supervised learning
   1. Unsupervised learning


Variable | Description
--|--
`CRIM` | per capita crime rate by town
`ZN` | proportion of residential land zoned for lots over 25,000 sq.ft.
`INDUS` | proportion of non-retail business acres per town
`CHAS` | Charles River dummy variable (= 1 if tract bounds river; 0 otherwise)
`NOX` | nitric oxides concentration (parts per 10 million)
`RM` |  average number of rooms per dwelling
`AGE` | proportion of owner-occupied units built prior to 1940
`DIS` |  weighted distances to five Boston employment centres
`RAD` | index of accessibility to radial highways
`TAX` | full-value property-tax rate per $10,000
`PTRATIO` | pupil-teacher ratio by town
`LSTAT` | % lower status of the population
`MEDV` | Median value of owner-occupied homes in $1000's
`expensive` | Is equal to “no” if the cost is <= $21,000, otherwise “yes”

## Classwork 2

Code from class:
```
X_train, X_test, y_train, y_test = model_selection.train_test_split(cancer.iloc[:, :-2], cancer[["worst fractal dimension"]], random_state=123)

reg = linear_model.LinearRegression().fit(X_train, y_train)

reg.score(X_test, y_test)

pd.DataFrame({"column" : X_test.columns, "coefficient" : reg.coef_[0]}).sort_values("coefficient")
``` 

1. Load the Boston Housing data, available here: https://drive.google.com/file/d/126E1-mxV5J4wtXwCVSF5oOyaaFUgCT9o/view?usp=share_link
1. Import the required packages: 
   ```
   import matplotlib.pyplot as plt
   import pandas as pd
   import seaborn as sns
   from sklearn import model_selection
   from sklearn import linear_model
   ```
1. Split the data into a train and test set using `model_selection.train_test_split()`. Let the output column be `MEDV` and do not include the column "expensive".
1. Train a linear regression model on this data.
1. Find the score of the model on the test data and the training data.
1. Find the coefficients of the model.
1. Which variables have the largest effect on the prediction?
1. (Challenge) Try subsetting to only the one or two variables with the largest absolute coefficients and training the model again. How does the score change?

## Classwork 2

Code from class:
```
reg = linear_model.Ridge().fit(X_train, y_train)
reg = linear_model.Lasso().fit(X_train, y_train)

reg = linear_model.Lasso(alpha = 0.1).fit(X_train, y_train)
reg = linear_model.Ridge(alpha = 0.1).fit(X_train, y_train)
```

1. Train a linear model on the housing data using ridge regression. Find its score on the training and test data.
1. Which variable has the largest-magnitude positive coefficient? Negative coefficient?
1. How do the training and test scores compare with the original linear regression model?
1. Train a linear model on the housing data using lasso regression. Find its score on the training and test data.
1. Which variable has the largest-magnitude positive coefficient? Negative coefficient?
1. Which variables have coefficients equal to zero?
1. How do the training and test scores compare with the original linear regression model and the ridge regression model?
1. Try modifying the alpha parameter for both of these models. Which model results in the highest accuracy on the test data?
1. (Challenge) Create plots to visualize the relationships between `MEDV` and key prediction variables.
