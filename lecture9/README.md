# Lecture 9 Classwork

This book is a great resource for ggplot2: https://ggplot2-book.org/ 

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
Columns of the `mpg` data:

| **Variable** | **Description** |
----|---
| manufacturer | The company who is responsible for making the vehicle |
| model | The model of the car |
| displ | The displacement or engine size of the engine in the standard model of the vehicle (in liters) |
| year | The model year of the vehicle  |
| cyl | The number of cylinders in the vehicle’s engine |
| trans | The type of transmission inside of the vehicle (manual or automatic) |
| drv | “drv” stands for “drivetrain” which is either forward, rear, or 4-wheel drive |
| cty | The number of city miles per gallon that the car is able to achieve|
| hwy | The number of highway miles per gallon that the car is able to achieve|
| fl | The vehicle’s fuel type (e = ethanol, d = diesel, r = regular, p = premium, c = CNG) |
| class | The “type” of the vehicle (ex: compact, subcompact, midsize, etc.) |

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
5. (Challenge) You should have access to the `diamonds` dataset (it is pre-loaded with the `ggplot2` package). Try plotting different variables against each other. Which aesthetic choices let you tell the best story? The variables are as follows:


| **Variable** | **Description** |
--------------- | -----------
| price | price in US dollars |
| carat | weight of the diamond |
| cut | quality of the cut |
| color | diamond color |
| clarity | measurement of how clear the diamond is |
| x | length in mm |
| y | width in mm |
| z | depth in mm |
| depth | total depth percentage |
| table | width of top of diamond relative to widest point |


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
4. What happens when you color by the same variable that you're faceting by?
5. What happens when you color by a different variable?
6. (Challenge) Try faceting in the `diamond` dataset as well. When do you think faceting is preferable to using aesthetics to distinguish groups?

## Changing `geom()`
Example commands from lecture:
```
# Create a histogram of the hwy variable
ggplot(mpg,
       aes(hwy)) +
  geom_histogram()
  
# Create a histogram of the hwy variable with a bin width of 5
ggplot(mpg,
       aes(hwy)) +
  geom_histogram(binwidth=5)
  
# Create a bar plot of the fl variable
ggplot(mpg,
       aes(fl)) +
  geom_bar()
```
1. **(Classwork) Create a histogram of the `cty` variable.** 
2. Create a bar plot of the `class` variable.
3. Explore the distribution of the `carat` variable in the diamonds dataset using a histogram (`diamonds` is pre-loaded). What binwidth reveals the most interesting patterns?
4. Try making either a histogram or bar plot for each variable in mpg, depending on whether it's quantitative or categorical.
5. (Challenge) What happens when you use color in these plots?
6. (Challenge) Scroll through this list of the "top 50 ggplot2 visualizations": http://r-statistics.co/Top50-Ggplot2-Visualizations-MasterList-R-Code.html. Copy and pastethe code for one that is of interest to you. Can you make a version of that plot using the `mpg` data? 
