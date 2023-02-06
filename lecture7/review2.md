# Review of Data Structures

## Vectors

### Creating vectors

1. Use the `c()` function to create a vector containing the numbers 4, 10, and 15. Assign it to `var10`.
2. Use the `c()` function to create a vector containing the words `apple`, `orange`, `grapefruit`, and `lime`. Save this vector as `fruits`.
3. Try using `c()` to combine vectors `c(4, 10)` and `15`, and save the result as `var11`.  
4. What happens when you run `var10 == var11`?
5. Set `var12` equal to a range of your choice (e.g. 2:8).
6. Use the `length()` function to find the length of each of the vectors you have defined.
7. Use the `str()` function to check the type of each vector you have defined.
8. Try using `c()` to combine `var10` and `fruits`. What is the type of the resulting vector?

### Accessing vector values

Remember, R indexing starts at 1. We use brackets to index into a vector.
1.  What do you expect to be the output of `var10[2]`? Check to see if you're right.
2.  What do you expect to be the output of `fruits[3:4]`? Check to see if you're right.
3.  What do you expect to be the output of `var12[c(1, 3, 6)]`? Check to see if you're right.
4.  What do you expect to be the output of `var11[1:length(var11)]`? Check to see if you're right.
5.  Try indexing into the vector `fruits` to get the value `lime`.
6.  Subset `var12` to the third entry through the last entry.

### Mathematical operations on vectors

1. Find the sum of all values of `var12` using the `sum()` function.
2. Find the sum of the squares of all values of `var12`.
3. Subtract 1 from every entry of `var10`.
4. Copy the following vectors into your script (they now have more data than last week):
```
tesla_price <- c(131.49, 128.78, 127.17, 133.42, 143.75, 143.89, 144.43, 160.27, 177.9, 166.66, 173.22, 181.41, 188.27, 189.98)
apple_price <- c(135.94, 135.21, 135.27, 137.87, 141.11, 142.53, 141.86, 143.96, 145.93, 143, 144.29, 145.43, 150.82, 154.5)
date <- c("Jan17", "Jan18", "Jan19", "Jan20", "Jan23", "Jan24", "Jan25", "Jan26", "Jan27", "Jan30", "Jan31", "Feb1", "Feb2", "Feb3")
```
5. Find the difference between `tesla_price` and `apple_price`. On which day was the price difference the largest?
6. Find the average of the `tesla_price` vector using the `sum()` and `length()` functions. Do the same with the `apple_price` vector.
7. Find the average of each of the price vectors using the `mean()` function.
8. Find the average of the `tesla_price` vector's first four entries (corresopnding to Jan17 through Jan20), and do the same for `apple_price`.
9. Find the average difference between `tesla_price`  and `apple_price`.

## Data Frames

### Creating data frames

1. Try creating your first data frame from the vectors defined in the previous section. Use the following code:

```
stocks <- data.frame(
  date=date,
  tesla=tesla_price,
  apple=apple_price
)
```
2. Try defining a data frame called `animals` using the following vectors as columns:

```
species <- c("dog", "cat", "penguin")
age <- c(7, 10, 3)
name <- c("Mittens", "Martha", "Typo")
feathers <- c(FALSE, FALSE, TRUE)
```
3. Try creating a data frame called `people` with columns `name`, `age`, and `birth_month`. Include entries for at least 4 people.
4. Use the `View()` command to visualize each of these data frames.
5. Use the `str()` command on each of these three data frames. What does it tell you?

### Loading and exploring a data frame

1. To look at the data sets available for analysis in R, use the command `data()`. 
2. These datasets vary in size and quality. You can load one in using the `data()` function, e.g. `data(iris)`. Load in several data frames until you find one with at least 4 columns and at least 20 rows (you can use the `str()` function to help). 
3. Try using the `head()` command on the data frame you loaded in the previous question, e.g. `head(iris)`. What does this function do?
4. Try using the `summary()` command on this data frame. What does this tell you that the `str()` command didn't tell you?
5. Each column of a data frame is a vector. We can access each one of these vectors using the `$` symbol. For example, if we wanted to access the `Species` column of the `iris` data frame, we would use `iris$Species`. Try accessing the individual columns of your data frame and running `summary()` on them.

### Subsetting data frames

We can access rows and columns of data frames using square brackets, similar to vectors. The format is `df[rows, columns]` where `df` is our data frame, `rows` is a vector representing the rows we want to access, and `columns` is a vector representing the columns we want to access. If we leave `rows` blank, e.g. `df[,columns]`, all columns will be selected. Similarly, if we leave `columns` blank like `df[rows,]` then all columns will be selected.

1. What do you think will be the result of `species[1,1]`? Run the code to check.
2. What do you think will be the result of `species[2,]`? Run the code to check.
3. What do you think will be the result of `species[,3]`? Run the code to check.
4. Write a line of code to subset the `species` dataframe to just the first and second columns.
5. Write a line of code to subset the `species` dataframe to just the first and third rows.
6. Write a line of code to subset the `species` dataframe to the second and third rows, and the first and second columns.

## Installing packages

1. You can install an R package using the `install.packages()` function, for example `install.packages("tidyverse")`. Try running this command to make sure the package is installed.
2. You can load an R package into your session using the `library()` function, e.g. `library(tidyverse)`. Load the `tidyverse` package into your current session.
3. You can check which packages are loaded in your current session by going to the "Packages" tab in the bottom right pane of the RStudio console. Click on one of the checked packages to go to its documentation.

## Changing the working directory

1. Now that we are about to start reading and writing data in R, we need to figure out where R thinks we are in our computer's file system. To do this, run the command `getwd()` to get the current working directory.
  * On a mac this will look something like: `/Users/jolivie1` (except with your username instead of `jolivie1`)
  * On a PC this will look something like: `C:\Users\jolivie1` (except with your username instead of `jolivie1`)
2. We will now change the working directory to the desktop. If you would prefer to work in another folder, you can set the working directory to whichever folder you would like to work in.
  * On a mac this will look something like: `setwd("/Users/jolivie1/Desktop")` (except with your username instead of `jolivie1`)
  * On a PC this will look something like: `C:\Users\jolivie1\Desktop` (except with your username instead of `jolivie1`)
3. Now running `getwd()` should show your new working directory.
 

## Reading/writing your own data

1. Download the following file to your working directory location (this is the desktop if you followed the instructions from the previous section): 
2. Read this file into a data frame in R using the following command: `read_csv(“auto.csv”)`
3. Write this data frame to a .csv file using the following command: `write_csv(small_auto,"small_auto.csv")`.


