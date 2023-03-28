# Lecture 17 Classwork Questions

## Classwork 1

The commands in the GitHub from last class might be useful: https://github.com/juliaolivieri/COMP_162/blob/main/lecture16/classwork16.md

1. Open a new JupyterLab session. This notebook is what you'll turn in for your classwork today.
1. Import pandas.
1. Download the college majors dataset and load it using pandas: https://drive.google.com/file/d/1WK9sQdr_S7RHDUIdEBPZ88dPeOUvTY7E/view?usp=sharing
1. Find the number of rows and columns of the DataFrame.
1. What is the data type of each column?
1. Use the `value_counts()`  function to find the count of each uniqu value in every categorical column.
1. Filter the data based on one categorical variable value. Compute summary statistics before and after filtering. Do any of the summary statistics change?
1. Brainstorm at least three plots that would help you understand this data. Which variable(s) are involved? Are they quantitative or categorical?

## Classwork 5

Example code from class:

```
import seaborn as sns
import matplotlib.pyplot as plt

# Create a histogram of the "total_bill" variable
sns.displot(data=tips, x="total_bill")
plt.show()

# Create a histogram of the "total_bill" variable colored by "smoker" and faceted by "time"
sns.displot(data=tips, x="total_bill",hue = "smoker", col="time", kind = "hist")
plt.show()

sns.displot(data=tips, x = "tip", hue="time", kind="kde")
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

sns.relplot(
    data=penguins,
    x="bill_length_mm", y="bill_depth_mm", col="sex",
    hue="species", style="island", size="body_mass_g"
)
plt.show()

# Create a barplot of "day" by "total_bill" colored by "smoker"
sns.catplot(data=tips, kind="bar", x="day", y="total_bill", hue="smoker")
plt.show()

sns.catplot(data = penguins, x = "species", y = "body_mass_g", kind = "box", hue="sex")
plt.show()
```

Documentation for functions:
* `displot`: https://seaborn.pydata.org/generated/seaborn.displot.html
*  `relplot`: https://seaborn.pydata.org/generated/seaborn.relplot.html
* `catplot`: https://seaborn.pydata.org/generated/seaborn.catplot.html


1. Make a plot of a quantitative variable using `displot()`. Set `hue` equal to a categorical variable. Try with `kind = "hist"` and `kind = "kde"`. Which provides a better representation of your data?
1. Make a plot of a categorical variable vs a quantitative variable using `catplot()`. Set `hue` equal to a categorical variable. Try with `kind` equal to each of the following: `"strip", "swarm", "box", "violin", "boxen", "point", "bar"`. Which provides the best representation of your data?
1. Make the plots you brainstormed in Classwork 1.
1. Work on improving one of your plots so that it enhances understanding of the dataset. Save it by including `plt.savefig("my_img.png")` on the line before `plt.show()`. Submit it: https://forms.gle/SFBcSFnZg1i97er57

## Classwork 6

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

Documentation for functions:
* `pairplot`: https://seaborn.pydata.org/generated/seaborn.pairplot.html
*  `lmplot`: https://seaborn.pydata.org/generated/seaborn.lmplot.html
* `jointplot`: https://seaborn.pydata.org/generated/seaborn.jointplot.html


1. Create a `pairplot` for the dataset. Which pairs of variables seem most interesting based on this plot? If you color the pair plot by a categorical variable does it reveal any additional information?
1. Create a plot of with a regression line between two quantitative variables you just identified. Does it look like the two variables have a linear relationship?
1. Create a `jointplot` between these two variables. Color by a categorical variable. What extra information does the jointplot provide?
1. (Challenge) Explore different jointplot "kinds" : `"scatter", "kde", "hist", "reg"`. Which kind is most appropriate for your data?
