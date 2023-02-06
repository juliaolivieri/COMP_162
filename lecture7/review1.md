# Review of Introduction to R

## Exploring RStudio

1. Create a new R script file, and save it as `lecture7.R`.
2. Add a comment to the beginning of your script by using `#`. What happens when you try to run this line of code?
3. Evaluate the mathematical expression `(400/20) + 22` in the console. Then add it to your script file, and evaluate it there. Is there a difference? Which is preferrable?
4. Try writing `-3:6` in your script and evaluating it. What is the output? What do you think the output will be if you instead input `4:93`? Check to see if you were right.
5. Check the documentation of the `min` function by running `?min` in your script. What does this function do based on the documentation?
6. At the bottom of the documentation you should see some lines of code starting with `require(stats); require(graphics)` and ending with ` identical(n0, pmax(n0, 4)))`. Copy these lines of code into your script, highlight them, and press "Run." Do you see a plot appear in the "Plots" pane?
7.  After running this code, some objects should appear in the "Environment" RStudio pane. This is where you will see all the objects you have defined in your session.

## Mathematical operations/functions

1. One of the most basic uses of R is as a calculator. Write down a line of code in your script to calculate the number of seconds in a year. Include a comment above it to keep track of what you were trying to calculate.
3. Use the `%%` operator to check whether the following number is even: `(3.2^2) %/% 2` 
4. Use `>` to check whether `sqrt(3)` is greater than `log(3)`.
5. Use `<` to check whether `log(3)` is less than `log10(d)`.
6. R has the value of pi encoded in this variable: Try executing `pi` in your R script. 
7. A penny has a diameter of 0.750 mm. A quarter has a diameter of 24.26 mm. Calculate the difference in the areas of a quarter and a penny. Remember, the area of a circle is equal to $\pi (radius)^2$. The radius is equal to the diameter divided by two. 

## Assigning/printing variables

## Variable types

## "If/else" statements

## For loops

