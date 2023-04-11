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

Code from class:
```
from sklearn import cluster
kmeans = cluster.KMeans(n_clusters=3).fit(X)

kmeans.labels_

kmeans.predict(X)
```


1. Make the toy datasets by copying the following code and running it:
   ```
   X, y = datasets.make_blobs(random_state=1)
   blob = pd.DataFrame(X)
   blob["y"] = y

   X, y = datasets.make_moons(n_samples=200, noise=0.05, random_state=0)
   moons = pd.DataFrame(X)
   moons["y"] = y

   X, y = datasets.make_circles(n_samples=200, noise = 0.05, random_state=1, factor = .3)
   circles = pd.DataFrame(X)
   circles["y"] = y
   ```
1. Run the following code to perform k-means clustering on each of these toy datasets, and plot the result:
   ```
   kmeans = cluster.KMeans(n_clusters=3).fit(blob[[0, 1]])
   blob["kmeans_3"] = kmeans.labels_
   sns.relplot(data = blob, x = 0, y = 1, hue = "kmeans_3")
   plt.show()

   kmeans = cluster.KMeans(n_clusters=2).fit(circles[[0, 1]])
   circles["kmeans_2"] = kmeans.labels_
   sns.relplot(data = circles, x = 0, y = 1, hue = "kmeans_2")
   plt.show()

   kmeans = cluster.KMeans(n_clusters=2).fit(moons[[0, 1]])
   moons["kmeans_2"] = kmeans.labels_
   sns.relplot(data = moons, x = 0, y = 1, hue = "kmeans_2")
   plt.show()
   ```
1. Change the `n_clusters` variable for each of these toy datasets. How does this affect the result?
1. (Challenge) Vary the parameters used to make the toy datasets (change `n_samples`, `noise`, etc). How do these parameters affect the clusters? 

## Classwork 3

Code from class:
```
agg = AgglomerativeClustering(n_clusters=3, linkage="ward").fit(X)

agg.labels_
```

1. Make the toy datasets by copying the following code and running it:
   ```
   X, y = datasets.make_blobs(random_state=1)
   blob = pd.DataFrame(X)
   blob["y"] = y

   X, y = datasets.make_moons(n_samples=200, noise=0.05, random_state=0)
   moons = pd.DataFrame(X)
   moons["y"] = y

   X, y = datasets.make_circles(n_samples=200, noise = 0.05, random_state=1, factor = .3)
   circles = pd.DataFrame(X)
   circles["y"] = y
   ```
1. Run the following code to perform k-means clustering on each of these toy datasets, and plot the result:
   ```
   agg = cluster.AgglomerativeClustering(n_clusters=3, linkage = "ward").fit(blob[[0, 1]])
   blob["agg_3"] = agg.labels_
   sns.relplot(data = blob, x = 0, y = 1, hue = "agg_3")
   plt.show()

   agg = cluster.AgglomerativeClustering(n_clusters=2, linkage = "ward").fit(circles[[0, 1]])
   circles["agg_2"] = agg.labels_
   sns.relplot(data = circles, x = 0, y = 1, hue = "agg_2")
   plt.show()

   agg = cluster.AgglomerativeClustering(n_clusters=2, linkage = "ward").fit(moons[[0, 1]])
   moons["agg_2"] = agg.labels_
   sns.relplot(data = moons, x = 0, y = 1, hue = "agg_2")
   plt.show()
   ```
1. Change the `n_clusters` variable for each of these toy datasets. How does this affect the result?
1. Change the `linkage` variable to `complete`, `single`, and `average`. How does this affect the result?
1. (Challenge) Vary the parameters used to make the toy datasets (change `n_samples`, `noise`, etc). How do these parameters affect the clusters? 

## Classwork 4

Code from class:
```
dbscan = DBSCAN(eps = 1).fit(X)

dbscan.labels_
```


1. Make the toy datasets by copying the following code and running it:
   ```
   X, y = datasets.make_blobs(random_state=1)
   blob = pd.DataFrame(X)
   blob["y"] = y

   X, y = datasets.make_moons(n_samples=200, noise=0.05, random_state=0)
   moons = pd.DataFrame(X)
   moons["y"] = y

   X, y = datasets.make_circles(n_samples=200, noise = 0.05, random_state=1, factor = .3)
   circles = pd.DataFrame(X)
   circles["y"] = y
   ```
1. Run the following code to perform k-means clustering on each of these toy datasets, and plot the result:
   ```
   dbscan = cluster.DBSCAN(eps = 1, min_samples = 5).fit(blob[[0, 1]])
   blob["dbscan"] = dbscan.labels_
   sns.relplot(data = blob, x = 0, y = 1, hue = "dbscan")
   plt.show()

   dbscan = cluster.DBSCAN(eps = 0.3, min_samples = 5).fit(circles[[0, 1]])
   circles["dbscan"] = dbscan.labels_
   sns.relplot(data = circles, x = 0, y = 1, hue = "dbscan")
   plt.show()

   dbscan = cluster.DBSCAN(eps = 0.3, min_samples = 5).fit(moons[[0, 1]])
   moons["dbscan"] = dbscan.labels_
   sns.relplot(data = moons, x = 0, y = 1, hue = "dbscan")
   plt.show()
   ```
1. Change the `eps` variable for each of these toy datasets. How does this affect the result?
1. Change the `min_samples` variable for each of these toy datasets. How does this affect the result?
1. (Challenge) Vary the parameters used to make the toy datasets (change `n_samples`, `noise`, etc). How do these parameters affect the clusters? 
