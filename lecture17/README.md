# Lecture 17 Classwork Questions

## Classwork 1

The commands in the GitHub from last class might be useful: https://github.com/juliaolivieri/COMP_162/blob/main/lecture16/classwork16.md

1. Open a new JupyterLab session. This notebook is what you'll turn in for your classwork today.
1. Import pandas.
1. Download the dataset and load it in using pandas: 
1. Find the number of rows and columns of the DataFrame.
1. What is the data type of each column?
1. Use the `value_counts()`  function to find the count of each uniqu value in every categorical column.
1. Filter the data based on one categorical variable value. Compute summary statistics before and after filtering. Do any of the summary statistics change?
1. Brainstorm at least three plots that would help you understand this data. Which variable(s) are involved? Are they quantitative or categorical?
1. (Challenge)

## Classwork 2

Example code from class:

```
import seaborn as sns

# Create a histogram of the "total_bill" variable
sns.displot(data=tips, x="total_bill")
plt.show()

# Create a histogram of the "total_bill" variable colored by "smoker" and faceted by "time"
sns.displot(data=tips, x="total_bill",hue = "smoker", col="time", kind = "hist")
plt.show()

# Create a scatterplot of "total_bill" vs "tip"
sns.relplot(
    data=tips,
    x="total_bill", y="tip"
)
plt.show()

# Create a scatterplot of "total_bill" vs "tip" colored by "smoker", faceted by "time", with marker style determined by "smoker" and size of the marker determined by "size"
sns.relplot(
    data=tips,
    x="total_bill", y="tip", col="time",
    hue="smoker", style="smoker", size="size"
)
plt.show()

# Create a barplot of "day" by "total_bill" colored by "smoker"
sns.catplot(data=tips, kind="bar", x="day", y="total_bill", hue="smoker")
plt.show()
```

1. Make the plots you brainstormed in Classwork 1.
1. Try each "kind" value for the `catplot()` and `displot()` functions on the data. Which is most informative for the variable(s) you're looking at?
1. Create as many images as you can that show insights from the dataset.
1. Submit your favorite image that you created to this link: https://forms.gle/SFBcSFnZg1i97er57

## Classwork 3

Example code from class:
```
penguins = sns.load_dataset("penguins")

# creating pairwise scatterplots of all quantitative variables
sns.pairplot(data=penguins)
plt.show()

# creating pairwise scatterplots of all quantitative variables colored by species
sns.pairplot(data=penguins, hue="species")
plt.show()

# adding a regression line to a scatterplot
sns.lmplot(data=tips, x="total_bill", y="tip", col="time", hue="smoker")
plt.show()

# Create a scatterplot along with distribution plots for the variables
sns.jointplot(data=penguins, x="flipper_length_mm", y="bill_length_mm", hue="species")
plt.show()
```
