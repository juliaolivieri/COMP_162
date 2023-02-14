# Lecture 9 Classwork

## First plotting exercise
Example commands from lecture:
```
# Plots the variables displ and hwy against each other
ggplot(mpg,
       aes(x = displ, y = hwy)) + 
  geom_point()
  
# The same as above, except x and y aren't explicitly assigned
ggplot(mpg,
       aes(displ, hwy)) + 
  geom_point()

# Saves the most recent plots as "my_first_plot.png" in the current working directory
ggsave(“my_first_plot.png”)
```

1. **(Classwork) Open a new R script file. This is what you will turn in for today's classwork.**
2. **(Classwork) Load the "tidyverse" library.**
3. View the dataset mpg with `View(mpg)` (this dataset is pre-loaded with the tidyverse package).
4. **(Classwork) Use the code above to create a plot of `displ` vs `hwy`.**
5. **(Classwork) Save this plot using `ggsave()` (example command above). You may want to set your working directory to a convenient place for the plot to be output.**
6. Plot `cty` against `hwy`. What is the relationship of these two variables?
7. What does `ggplot(mpg, aes(model, manufacturer)) + geom_point()` show? Is it useful? What modifications would make it more informative?
8. (Challenge) Consider the following commands. Try to guess what each one will look like before running it. You’ll need to guess a little because you haven’t seen all the datasets and functions yet.
* `ggplot(mpg, aes(cty, hwy)) + geom_point()`
* `ggplot(diamonds, aes(carat, price)) + geom_point()`
* `ggplot(economics, aes(date, unemploy)) + geom_line()`
* `ggplot(mpg, aes(cty)) + geom_histogram()`

## Changing plot aesthetics
Example commands from lecture:
```
# plots displ vs hwy, with point color determined by class
ggplot(mpg,
       aes(displ, hwy, color = class)) + 
  geom_point()

# plots displ vs hwy, with point color determined by class,
# point shape determined by drv, and point size determined by cyl
ggplot(mpg,
       aes(displ, 
           hwy, 
           color = class, 
           shape = drv, 
           size = cyl)) + 
  geom_point()
```

1. **(Classwork) Plot `cty` vs `hwy` and color by `drv`, determine shape by `fl`, and size by `displ`.**
2. Try making three different plots of `cty` vs `hwy`, the first with color by `drv`, the second with `shape` by `fl`, and the third with size by `displ`.
3. Plot `displ` vs `cty`. Try mapping color to `hwy`. What happens?
4. Try mapping a quantitative variable to shape. What happens?

## Faceting
Example commands from lecture:
```
ggplot(mpg,
       aes(displ, hwy, color = class)) + 
  geom_point() +
  facet_wrap(~class)
```
1. **(Classwork) Plot `displ` vs `hwy` and facet by `cyl`.**
2. Try coloring the points by `class` in the previous plot.
3. Try faceting by each variable other than `displ` and `hwy`. Which seem the most useful? Which seem the least useful?
