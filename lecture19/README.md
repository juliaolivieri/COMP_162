# Classwork for Lecture 19

## Classwork 1

The GitHub link from last class might be helpful: https://github.com/juliaolivieri/COMP_162/tree/main/lecture18

With books.csv dataset:

Assign a new variable called "Season” based on the "PublishMonth" column. Let "Season"  be defined as follows:
   * “Season” equals “Winter”  if “PublishMonth”  equals 1, 2, or 3
   * “Season”  equals “Spring”  if “PublishMonth” equals 4, 5, or 6
   * “Season”  equals “Summer” if “PublishMonth” equals 7, 8, or 9
   * “Season”  equals “Fall”  if “PublishMonth” equals 10, 11, or 12

(Challenge) Define the following columns:
   * “TimePeriod” based on the “PublishYear” column, with at least 4 categories.
   * “Popularity” based on the “RatingDistTotal” column, with at least 3 categories. 
   
## Classwork 2

Code from class:
```
aq.corr()

aq.corr(method = "pearson")
aq.corr(method = "spearman")

sns.heatmap(aq.corr(),annot=True)
plt.show()
```

1. Load the air quality dataset into your notebook.
1. Familiarize yourself with the data by performing some exploratory data analysis.
1. Calculate the Spearman and Pearson correlation matrices.
1. Plot the Spearman and Pearson correlation matrices.
1. Decide on at least one research hypothesis that can be tested using the following methods:
   * t test (binary variable vs quantitative variable)
   * linear regression (quantitative variable vs quantitative variable)
   
## Classwork 3

Code from class:
```
from scipy import stats

cold_aq = aq[aq["temp_level"] == "cold"]
warm_aq = aq[aq["temp_level"] == "warm"]
stats.ttest_ind(cold_aq["CO"], warm_aq["CO"]) 

stats.linregress(x = aq["NMHC"], y = aq["CO"])
```

1. Import the stats module:  `from scipy import stats`
1. Perform at least one t test on the data.
   * Create a plot to visualize the relationship between the variables that you tested.
   * Can you reject the null hypothesis?
1. Perform at least one linear regression on the data.
   * Create a plot to visualize the relationship between the variables that you tested.
   * Can you reject the null hypothesis?
   
## Classwork 4

What is your current understanding of the term “machine learning”?

## Classwork 5

Code from class:
```
from sklearn import linear_model
from sklearn import model_selection
from sklearn import metrics

reg = linear_model.LinearRegression().fit(aq[["NMHC"]], aq[["CO"]])
   
print(reg.coef_)
print(reg.intercept_)
   
X_train, X_test, y_train, y_test = model_selection.train_test_split(aq[["NMHC"]], aq[["O"]], random_state=1234)
reg = LinearRegression().fit(X_train, y_train)
y_pred = reg.predict(X_test)
   
metrics.r2_score(y_test, y_pred)
metrics.mean_squared_error(y_test, y_pred)
```

1. Import all necessary sklearn modules:
   ```
   from sklearn import linear_model
   from sklearn import model_selection
   from sklearn import metrics
   ``` 
3. Re-calculate the linear model from Classwork 3 using sklearn with all the data. Do you get the same coefficient and intercept?
4. “Predict” the value of the independent variable based on this model. Use metrics.r2_score() and  metrics.mean_squared_error() to evaluate the prediction.
5. Split the data into a training and testing set.
6. Train a new linear model using the training data.
7. “Predict” the independent variable from the training set using this model. Use metrics.r2_score() and  metrics.mean_squared_error() to evaluate the prediction.
8. “Predict” the independent variable from the testing set using this model. Use metrics.r2_score() and  metrics.mean_squared_error() to evaluate the prediction.
9. Which prediction is the most accurate? Least? Does this make sense to you?
10. (Challenge) Try a few different random seeds for the train/test split. How different are your answers?

