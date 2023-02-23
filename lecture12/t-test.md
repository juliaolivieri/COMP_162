### T-test practice

Commands from lecture:
```
# perform a t test with count as the dependent variable and workingday as the independent variable
t.test(count ~ workingday, data = bike_sharing)
```

1. Perform a t-test using the ais data, with `sex` as the independent variable and `ht` as the dependent variable. Do you detect a difference in mean height by sex?
2. Perform a t-test using `sex` as the independent variable and `wcc` as the dependent variable. Do you detect a difference in mean height by sex?
3. (Challenge) For each quantitative variable in the dataset, use a t-test to check whether there's a significant difference in means by sex using `alpha = 0.05`.
