# Lecture 11

## Correlation

Commands from lecture:
```
# calculate the correlation between the count and temperature_F columns of bike_sharing
cor.test(bike_sharing$count, bike_sharing$temperature_F)

# calculate the pairwise correlations between temperature_F, humidity, windspeed, and count
cor(select(bike_sharing, temperature_F, humidity, windspeed, count))

# Create every pairwise scatterplot between temperature_F, humidity, windspeed, and count
pairs(select(bike_sharing, temperature_F, humidity, windspeed, count))
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
3. Find the pair-wise correlation for all quantitative variables using `cor()` (you will need to use `select()` to remove `sex` and `sport`).
4. Plot the pair-wise scatterplots for all quantitative variables using `pairs()` (you will need to use `select()` to remove `sex` and `sport`).
5. Based on the correlation matrix, which two variables have the **highest** correlation? Use `cor.test()` to find more details about the correlation of these two variables (what is the p value? What is the confidence interval?)
6. Based on the correlation matrix, which two variables have the **lowest** correlation? Use `cor.test()` to find more details about the correlation of these two variables (what is the p value? What is the confidence interval?)
7. (Challenge) Find the pair of variables with the lowest correlation and a p value of < 0.05.
8. (Challenge) Try filtering by sex or sport and check how the pairwise correlations change. Do the variables have higher or lower correlations after filtering?

