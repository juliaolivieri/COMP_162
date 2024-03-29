# Lecture 16 Classwork

## Classwork 1

Do the following in a new Jupyter Notebook in JupyterLab:

1. Assign the sum of 1 and -4 as `a`.
1. Assign the absolute value of `a` as `b` (use the `abs()` function).
1. Assign `b` minus 1 as `d`.
1. Test whether `d` is greater than 2. 
1. The Python Standard Library includes a module random containing a function `randint()`. Given two integers, `randint()` will contain an integer in that range. For example, `randint(1,6)` will return an integer between 1 and 6 (inclusive). Use this function to find a random number between 0 and 36.
1. (Challenge) What happens when you set a random seed with the `seed()` function before running `randint()`? Why might this function be useful? https://docs.python.org/3/library/random.html 

## Classwork 2

Code from class:
```
example_list = [5, -2.3, 10, 11, 3]
fruits = ["apple", "banana", "cherry"]

example_list[0] # result is 5
fruits[1] # result is "banana"
example_list[2:4] # result is [10, 11]
```

1. Slice the following array so that you are left with the last three elements: `["I", "am", "having", "fun", "with", "Python"]`

## Classwork 3

Code from class:
```
animals.iloc[0,0] # results in "dog"
animals.loc[3, "species"] # results in "dog"
```

1. Copy and run the following code to load the `animals` DataFrame:
   ```
   import pandas as pd
   
   animals = pd.DataFrame({"species": ["dog", "cat", "penguin"], "size": [40, 10, 80], "name": ["Typo", "Ralph", "Pinky"], "age": [5, 18, 12]}, index = [3, 6, 7])
   ```
1. What are two ways to index into the "10" entry?

## Classwork 4

Code from class:
```
animals.iloc[0:2, 1:4]
animals.loc[[3, 6],["size", "name", "age"]]
```

1. Download the `mining.csv` file: https://drive.google.com/file/d/1Z6_ejcVUrmB39BO3GJ2bmwD8lrrX2TvW/view?usp=sharing
2. Load `mining.csv` into a DataFrame called `mine` using this command:
   `mine = pd.read_csv("mining.csv",index_col = 0)`
3. Index into the "pearl" entry using `.iloc[]`
4. Index into the "diamond" entry using `.loc[]`
5. Use `.iloc[]` to subset to a DataFrame only containing gems, and no "rock"
6. Use `.loc[]` to subset to a DataFrame only containing gems, and no "rock"
7. (Challenge) Assign an entry to be "topaz" and an entry to be "amethyst" in such a way that you can still index to include all gems and no "rock". Use both methods to index into only the gems in the augmented DataFrame.

## Classwork 5

All of the commands we have learned today have analogs in R. The table below provides a reference for each command in both R and Python.

1. To practice the commands we've learned today, as well as see their relationship with the R commands that we've already learned, "translate" each line of the following R Markdown file to Python in your Jupyter Notebook: https://juliaolivieri.github.io/. The `taxis.csv` file is available here: https://drive.google.com/file/d/1yzcou-mgYXhanO_gP69TZyEC_2S5sm0f/view?usp=share_link. You can check the output of your notebook against the output in the R Markdown file.
2. Which variables are binary? Which command is most useful for identifying binary variables?
3. For any of these commands, do you prefer the syntax or output from R rather than Python, or vice versa?

R syntax | Python syntax | Description
-- | -- | --
`read_csv("test.csv")`| `pd.read_csv("test.csv")`| read csv called `test.csv`
`write_csv(test_df, "test.csv")` | `test_df.to_csv("test.csv",index=False)`| Write data frame `test_df` to file called `test.csv` (without index column)
`test_df[1,]` | `test_df.iloc[0,:]`| Index into the first row of data frame `test_df`
`test_df[,1]` | `test_df.iloc[:,0]`| Index into the first column of data frame `test_df`
 `library("testPackage")` | `import testPackage` | Load a package called `testPackage`
`typeof(x)` | `type(x)` | Find type of object `x`
 `head(test_df)` | `test_df.head()`| Get the first few lines of a data frame called `test_df`
 `tail(test_df)`| `test_df.tail()`| Get the last few lines of a data frame called `test_df`
 `str(test_df)` | `test_df.info()`| Find column names and data types of data frame called `test_df`
 `summary(test_df)` | `test_df.describe(include = "all")` | Generate summary statistics for data frame columns
 `test_df$col1` | `test_df["col1"]` | Access column named `"col1"` from data frame `test_df`
 `test_df[,c("name", "age", "height")]` | `test_df[["name", "age", "height"]]` | Subset data frame `test_df` to just columns  `"name"`, `"age"`, and `"height"` 
 `filter(test_df, school == "UOP")`| `test_df[test_df["school"] == "UOP"]` | Subset data frame `test_df` to only rows for which `"school"` is equal to `"UOP"`
 `filter(test_df, age > 18)` | `test_df[test_df["age"] > 18]` | Subset data frame `test_df` to only rows for which `"age"` is greater than 18
  `test_df %>% group_by(color) %>% summarize(count = n()) %>% arrange(desc(count))`| `test_df.value_counts("color")` | Find the count of each value for categorical variable `"color"` in data frame `test_df` in descending order

