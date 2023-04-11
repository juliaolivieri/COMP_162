# Classwork 21 

## Classwork 1

Code from class:
```
X_train, X_test, y_train, y_test = model_selection.train_test_split(cancer.iloc[:,:-2], cancer[["benign"]], random_state = 123)

reg = linear_model.LogisticRegression().fit(X_train, y_train)

reg.score()

metrics.confusion_matrix(y_test, y_pred)
```

The GitHub from last class is available here: https://github.com/juliaolivieri/COMP_162/tree/main/lecture20

1. Start a new notebook for today's classwork.
1. Load in the required libraries:
   ```
   import matplotlib.pyplot as plt
   import pandas as pd
   import seaborn as sns
   
   from sklearn import cluster
   from sklearn import datasets
   from sklearn import metrics
   from sklearn import model_selection
   from sklearn import linear_model
   ```
1. Load the housing dataset from last time (https://drive.google.com/file/d/126E1-mxV5J4wtXwCVSF5oOyaaFUgCT9o/view?usp=sharing) and split it into training and test data.
1. Train a logistic regression model on this dataset, using every column except `MEDV` and `expensive` as your input, and `expensive` as the output.
   * How accurate is the model?
   * Which variables have the largest-magnitude coefficients?
   * Create a confusion matrix. Which category is your model best at predicting?
1. (Challenge) Use seaborn to visualize the relationship between `expensive`  and the variables that contribute most to the model.

## Classwork 2

