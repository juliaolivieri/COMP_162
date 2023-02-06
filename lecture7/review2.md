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
2. 

### Working with R's preloaded datasets

1. 

### Exploring your data frame

1.

### Subsetting data frames

1. 

## Installing packages

1. 

## Changing the working directory

1. 

## Reading/writing your own data

1. 


