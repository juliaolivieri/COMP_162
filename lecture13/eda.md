# Exploratory Data Analysis with R Markdown

**Note: The happiness score is a function of the other variables, so we can focus on relationships between the other variables**

------
| Variable | Description |
--- | ---
| `Country` | Country measured|
| `Region` | Region the country is in|
| `HappinessScore` | Happiness score (a function of the following columns)|
| `StandardError` | The standard error of the happiness score |
| `GDPperCapita`| The GDP per capita |
| `Family` | "having someone to count on in times of trouble" |
| `LifeExpectancy` | Life expectancy |
| `Freedom` | Freedom |
| `Trust` | Trust (absence of corruption in business and government)|
| `Generosity` | Generosity|

1. Read in the data: https://drive.google.com/file/d/1dmzOeslYzCTRzbeSWqKN0QSGc58LSRok/view?usp=sharing
2. Perform exploratory data analysis on this data. Examples:
* Find the data type of each column
* Find the number of countries in each region
* Sort the countries by a variable (e.g. `LifeExpectancy`)
* Find the average `GDPperCapita` by `Region`
3. In R Markdown write a few observations from your analysis so far.
4. Create some exploratory visualizations. Suggestions:
* Create pairwise scatterplots of some of the quantitative variables using `pairs()`
* Create a scatterplot of one quantative variable vs the other, adding a linear regression line with `geom_smooth(method=lm)`
* Create a boxplot of one of the quantitative variables by `Region`
5. Add some explanatory text to describe what you found.

