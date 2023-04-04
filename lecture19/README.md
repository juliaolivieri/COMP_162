# Classwork for Lecture 19

## Classwork 1

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

1. Load the air quality dataset into your notebook.
1. Familiarize yourself with the data by performing some exploratory data analysis.
1. Calculate the Spearman and Pearson correlation matrices.
1. Plot the Spearman and Pearson correlation matrices.
1. Decide on at least one research hypothesis that can be tested using the following methods:
   * t test (binary variable vs quantitative variable)
   * linear regression (quantitative variable vs quantitative variable)
   
## Classwork 3

1. Perform at least one t test on the data.
   * Create a plot to visualize the relationship between the variables that you tested.
   * Can you reject the null hypothesis?
1. Perform at least one linear regression on the data.
   * Create a plot to visualize the relationship between the variables that you tested.
   * Can you reject the null hypothesis?
   
## Classwork 4

What is your current understanding of the term “machine learning”?

## Classwork 5

1. Re-calculate the linear model from Classwork 3 using sklearn with all the data. Do you get the same coefficient and intercept?
1. “Predict” the value of the independent variable based on this model. Use metrics.r2_score() and  metrics.mean_squared_error() to evaluate the prediction.
1. Split the data into a training and testing set.
1. Train a new linear model using the training data.
1. “Predict” the independent variable from the training set using this model. Use metrics.r2_score() and  metrics.mean_squared_error() to evaluate the prediction.
1. “Predict” the independent variable from the testing set using this model. Use metrics.r2_score() and  metrics.mean_squared_error() to evaluate the prediction.
1. Which prediction is the most accurate? Least? Does this make sense to you?
1. (Challenge) Try a few different random seeds for the train/test split. How different are your answers?

