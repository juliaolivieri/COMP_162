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

