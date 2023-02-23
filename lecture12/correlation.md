# Correlation practice

## Multiple choice questions

### What does a correlation coefficient measure?

A. The strength of the relationship between two variables.

B. The difference in means between two variables.

C. The causality between two variables.

D. The variability of one variable.


### Which of the following correlation coefficients represents the strongest relationship between two variables?

A. -0.2

B. 0

C. 0.5

D. -0.8

### Which of the following statements about correlation is true?

A. Correlation implies causation.

B. Correlation can only be positive.

C. Correlation is a linear relationship between two variables.

D. The value of the correlation coefficient depends on the order of the variables in the calculation.

### Which of the following is a possible interpretation of a Spearman correlation coefficient of 0.8?

A. There is a strong positive linear relationship between the variables.

B. There is a strong positive monotonic relationship between the variables.

C. There is no relationship between the variables.

D. The variables are perfectly negatively correlated.

### What is the effect of outliers on Pearson correlation?

A. Outliers have no effect on Pearson correlation.

B. Outliers increase the strength of Pearson correlation.

C. Outliers decrease the strength of Pearson correlation.

D. The effect of outliers on Pearson correlation depends on their location and magnitude.

## Coding questions

Commands from lecture:
```
# calculate the Spearman correlation between the count and temperature_F columns of bike_sharing
cor.test(bike_sharing$count, bike_sharing$temperature_F, method = "spearman")

# calculate the pairwise Spearman correlations between temperature_F, humidity, windspeed, and count
cor(select(bike_sharing, temperature_F, humidity, windspeed, count), method = "spearman)
```

| Variable | Description |
| -- | -- |
| `rcc` | red blood cell count |
| `wcc` | white blood cell count |
| `hc` | hematocrit, percent |
| `hg` | hemaglobin concentration |
| `ferr` | plasma ferritins |
| `ht` | height, cm |
| `wt` | weight, kg|
| `sex` | either `f` or `m` |
| `sport` | Takes on the following values: `B_Ball`, `Field`, `Gym`, `Netball`, `Row`, `Swim`, `T_400m`, `T_Sprnt`, `Tennis`, `W_Polo`|

Questions
1. Load the tidyverse package.
2. Read the following csv into a data frame called `ais` in R: https://drive.google.com/file/d/1WY7MHz3TnBvMPYJXq8UecPrhgAt8krAJ/view?usp=sharing
3. Find the pair-wise Spearman correlation for all quantitative variables using `cor()` (you will need to use `select()` to remove `sex` and `sport`).
4. Does any pair have a higher Spearman correlation than Pearson correlation?
5. Based on the Spearman correlation matrix, which two variables have the **highest** correlation? Use `cor.test()` to find more details about the correlation of these two variables (what is the p value?)
6. Based on the Spearman correlation matrix, which two variables have the **lowest** correlation? Use `cor.test()` to find more details about the correlation of these two variables (what is the p value?)
7. (Challenge) Find the pair of variables with the lowest Spearman correlation and a p value of < 0.05.
