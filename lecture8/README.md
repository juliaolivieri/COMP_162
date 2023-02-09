# Lecture 8 Classwork

## Setup
1. **(Classwork) Download the Star Wars dataset from this link: https://drive.google.com/file/d/1dVNkH9l13vIsuMTGWCV1HxxTgeeUH6gi/view?usp=sharing**
2. **(Classwork) Open a new R script file. This is what you will turn in for today's classwork.**
3. **(Classwork) Load the tidyverse library (`library(tidyverse)`).**
4. **(Classwork) Load the Star Wars data. Note that you will need to use `setwd()` to set your working directory to the location of `starwars.csv`. If you have trouble with that, you can use "File --> Import Dataset --> From Text (base)"**
```
starwars <- read_csv("starwars.csv")
```

## The `arrange()` function
Example commands from lecture:
```
# returns the data frame sorted by name (but the result isn't saved)
arrange(starwars, name)

# saves the result of sorting the data frame by name
starwars <- arrange(starwars, name)

# saves the result of sorting the data frame by eye_color, then height
starwars <- arrange(starwars, eye_color, height)

# saves the result of sorting the data frame by eye_color, then height in descending order
starwars <- arrange(starwars, eye_color, desc(height))

```
1. **(Classwork) Sort the data frame by `hair_color`.**
2. Sort the data frame by `age` in descending order.
3. Sort the data frame by `hair_color`, then `age` in descending order.
4. Sort the data frame by `hair_color` in descending order, then `age` in ascending order.
5. (Challenge) Sort the data frame by every column in the data frame, choosing ascending order for half and descending order for half. 


## The `select()` function
Example commands from lecture:
```
# Select the columns name, age, and species
small_starwars <- select(starwars, name, age, species)

# Remove the gender and homeworld columns, but keep all others
tiny_starwars <- select(starwars, -gender, -homeworld)
```
1. **(Classwork) Create a data frame called `selected1` with only the columns `hair_color`, `eye_color`, and `name`.** 
2. Create a data frame called `selected2` that includes all columns except `hair_color` and `eye_color`.
3. Create a data frame that includes only the `height`, `homeworld`, and `species` columns.
4. (Challenge) Create a data frame that includes all columns except `hair_color`, `eye_color`, `mass`, and `height`. Try doing this in two ways: by including all other columns, and by dropping these specific columns.  

## The `mutate()`  function
Example commands from lecture:
```
# command to add a column called height_inches  that is the height column divided by 2.54
starwars <- mutate(starwars, height_inches = height/2.54)

# command to add a column equal to the sum of the height and age columns
starwars <- mutate(starwars, height_age = height + age)
```
1. **(Classwork) Add a column called `mass_div_height` that is equal to the `mass`  column divided by the `height` column.**
2. Add a column called `sqrt_mass` that is equal to the square root of the `mass` column.
3. Add a column that is equal to `(mass - age) + height`.
4. (Challenge) Add a column called `elder` that equals `True` if the character is older than 65, and False otherwise.

## The `filter()` function
Example commands from lecture:
```
# Command to filter the data frame to only rows for which species equals "Droid"
droids <- filter(starwars, species == “Droid”)

# Command to filter the data frame to only rows for which age is greater than 65
elders <- filter(starwars, age > 65)
```
1. **(Classwork) Create a data frame called `from_tatooine` that only contains rows for which `homeworld` is equal to `Tatooine`.**
2. Create a data frame called `tallest` that only contains rows for which `height` is greater than 190.
3. Create a data frame called `smallest` that only contains rows for which `height` is less than 170.
4. Create a data frame called `blue_eyes` that only contains characters whose `eye_color` is equal to `blue`.

## The `group_by()` and `summarize()` functions
Example commands from lecture:
```
# finds the mean height of each species
grouped_data <- group_by(starwars, species)
summarized_data <- summarize(grouped_data, average_height = mean(height))
```

| Function | Aggregation type |
| ------- | ----- |
| `sum()` | Sum |
| `n()` | Count values |
| `mean()` | Average |
| `max()` | Highest value |
| `min()` | Lowest value | 
| `sd()` | Standard deviation |


1. **(Classwork) Find the average `age` by `gender`**
2. Find the maximum `age` by `homeworld`.
3. Find the sum of `mass` by `hair_color`.

## The Pipe (`%>%`)
Example commands from the lecture:
```
# Grouping by species, finding the average height of each species, and sorting by average height **without** the pipe
grouped_data <- group_by(starwars, species)
summarized_data <- summarize(grouped_data, average_height = mean(height))
summarized_data <- arrange(summarized_data, average_height)
View(summarized_data)

# Grouping by species, finding the average height of each species, and sorting by average height **with** the pipe
starwars %>%
    group_by(species)%>% 
    summarize(average_height = mean(height)) %>%
    arrange(average_height) %>%
    View()

```
1. **(CW) Try re-writing the answer to the previous classwork question using the pipe operator**
2. Try filtering the data frame to columns for which `species` is equal to `Human` and sorting by `age` using `%>%`.
3. (Challenge) Try stringing the `arrange()`, `select()`, `mutate()`, `filter()`, `group_by()`, and `summarize()` functions all together using `%>%`.
4. (Challenge) Try re-writing all of the previous classwork questions using `%>%`.
