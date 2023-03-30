# Lecture 18 Classwork

The goodreads data set can be downloaded at this link: https://drive.google.com/file/d/1Oqs4GN01e35_6BAfrEPYbfGvUC7ARR5p/view?usp=sharing

Each row corresponds to one book. Column definitions are the following:

Variable | Description
--|--
`Name` | The title of the book
`RatingDist1` | The number of 1-star ratings
`RatingDist2` | The number of 2-star ratings
`RatingDist3` | The number of 3-star ratings
`RatingDist4` | The number of 4-star ratings
`RatingDist5` | The number of 5-star ratings
`RatingDistTotal` | The total number of ratings
`pagesNumber` | The number of pages in the book
`PublishDay` | The day of the month the book was published
`PublishMonth` | The month the book was published (1-12)
`Publisher` | The publisher of the book
`CountsOfReview` | The number of reviews the book has received (different from ratings)
`PublishYear` | The year the book was published
`Language` | The language the book is written in
`Authors` | The author(s) of the book
`Rating` | The average rating given to this book (out of 5)

## Importing code from class

```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as sns

# Stops columns from being cut off when displayed
pd.set_option('display.max_colwidth', None)
```

## Sorting code from class

```
books.sort_values(“Rating”)
books.sort_values([“Rating”, “PublishYear”])
books.sort_values([“Rating”, “PublishYear”], ascending = False)
```

## Filtering code from class

```
books = books[(books[“PublishYear”] > 1800) & (books[“PublishYear”] < 2024)]
books = books[(books[“Language”] == “eng”) | (books[“Language”] == “en-US”) | (books[“Language”] == “en-GB”)]
```

## Creating a new column code from class

```
books[“RatingsPlusReviews”] = books[“RatingDistTotal”] + books[“CountsOfReviews”]	
books[“fracRated1”] = books[“RatingDist1”]/books[“RatingDistTotal”]
books[“Rated5MinusRated1”] = books[“RatingDist5”] - books[“RatingDist1”]
```

## Making a categorical column out of a quantitative column code from class

```
books[“Length”] = “tiny”
books.loc[books[“pagesNumber”] > 20, “Length”] = “short”
books.loc[books[“pagesNumber”] > 150, “Length”] = “medium”
books.loc[books[“pagesNumber”] > 350, “Length”] = “long”
```
