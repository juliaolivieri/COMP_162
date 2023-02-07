# Review of Introduction to R

Note: "classwork" questions are bolded. You are welcome to include more answers in your classwork submission.

## Exploring RStudio

1. **(CW) Create a new R script file, and save it as `lecture7.R`. You will submit this file for the "classwork 7" assignment.**
2. Add a comment to the beginning of your script by using `#`. What happens when you try to run this line of code? I recommend including comments throughout this classwork to help you remember what you did.
3. Evaluate the mathematical expression `(400/20) + 22` in the console. Then add it to your script file, and evaluate it there. Is there a difference? Which is preferrable?
4. Try writing `-3:6` in your script and evaluating it. What is the output? What do you think the output will be if you instead input `4:93`? Check to see if you were right.
5. Check the documentation of the `min` function by running `?min` in your script. What does this function do based on the documentation?
6. At the bottom of the documentation you should see some lines of code starting with `require(stats); require(graphics)` and ending with ` identical(n0, pmax(n0, 4)))`. Copy these lines of code into your script, highlight them, and press "Run." Do you see a plot appear in the "Plots" pane?
7.  After running this code, some objects should appear in the "Environment" RStudio pane. This is where you will see all the objects you have defined in your session.

## Mathematical operations/functions

1. **(CW) One of the most basic uses of R is as a calculator. Write down a line of code in your script to calculate the number of seconds in a year. Include a comment above it to keep track of what you were trying to calculate.**
3. Use the `%%` operator to check whether the following number is even: `(3.2^2) %/% 2` 
4. Use `>` to check whether `sqrt(3)` is greater than `log(3)`.
5. Use `<` to check whether `log(3)` is less than `log10(3)`.
6. R has the value of pi encoded in this variable: Try executing `pi` in your R script. 
7. (Challenge) A penny has a diameter of 0.750 mm. A quarter has a diameter of 24.26 mm. Calculate the difference in the areas of a quarter and a penny. Remember, the area of a circle is equal to $\pi (radius)^2$. The radius is equal to the diameter divided by two. 

## Assigning/printing variables

1. **(CW) Assign a variable to `var1` with the result of 5 different mathematical operations/functions, e.g. `floor((27 - 3) %% 5) + ceiling(-5.9)^2`.**
2. Assign a variable `var2` to a different result of mathematical operations/functions.
3. Assign a third variable to the result of `var1 == var2`.
4. Assign `var4` to `T`.
5. Assign `var5` to `TRUE`.
6. Check whether `var4` is equal to `var5` using `==`.
7. Print each variable.
8. (Challenge) Redo question 7 from the section above, but this time assign a variable for the diameter of a quarter, a variable for the diameter of a penny, a variable for the area of a quarter, a variable for the area of a penny, and a variable for the difference in area of the two.

## Variable types

1. **(CW) Check the types of five of the variables that you have defined in your script so far using the `str()`  function, e.g. `str(var1)`.**
2. Assign a variable `var6` to 5, and a variable `var7` to 5L.
3. Check the types of these two variables.
4. Check whether these two variables are equal.
5. Assign `var8` to `"5"`. What type is this variable?
6. Is `var8` equal to `var6`?

## "If/else" statements

Here is an example to show if/else syntax in R:

```
day <- "Monday"
if (day == "Saturday" ) {
  print("Weekend starts!")
} else if (day == "Sunday") {
  print("Weekend ends")
} else {
  print("Weekday")
}

```

1. Copy and paste this code into your script and execute it. What gets printed? Do you understand why this message is printed?
2. Change the value of the `day` variable to cause a different message to be printed.
3. **(CW) Define a variable called `var9`. Write code to print a different message depending on whether `var9` is positive, negative, or equal to 0.**
4. Define a variable called `age`. Output a different message for each age range:
  * 0-17: You are a minor.
  * 18-29: You are old enough to vote!
  * 30-34: You re old enough to become a senator!
  * 35 and older: You are old enough to become president!  
5. (Challenge) Define a variable `var9`. If `var9` is divisible by 2 and 7, print `cracklepop`. If it is only divisible by 2, print `crackle`. If it is only divisble by 7, print `pop`.

## For loops

Here is an example to show for loop syntax in R:

```
for (x in 1:10) {
  print(x)
}
```

1. Copy and paste this code into your script and execute it. What gets printed? Do you understand why these numbers are printed?
2. Change 1:10 to a different range in the loop. What do you expect to be printed this time? Does the output meet your expectation?
3. **(CW) Write a for loop to print $x^2$ for $x = 4, 5, 6, \ldots, 49, 50$.**
4. Use a for loop to calculate the sum of the numbers from 1 to 100.
5. (Challenge) Using your answer to question 5 of the section above, write code to print the numbers from 1 to 100. If the number is only divisible by 2, print `crackle`. If it is only divisble by 7, print `pop`.
6. (Challenge) Use a nested for loop to print `i - j` for all $i = 1, 2, ..., 7$ and $j = 3, ..., 10$.

