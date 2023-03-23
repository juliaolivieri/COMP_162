

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


1. Load the csv using the command `rock = pd.read_csv("mining.csv",index_col = 0)`. 
2. Use `iloc` to index only into the gems.
3. Use `loc` to index only into the gems.

R Markdown file to translate: https://juliaolivieri.github.io/

To load animal data frame: `animals = pd.DataFrame({"species": ["dog", "cat", "penguin"], "size": [40, 10, 80]}, index = [3, 6, 7])`
