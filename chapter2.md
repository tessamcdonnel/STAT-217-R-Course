---
title       : Lab 2
description : Using R to Explore Data Sets

--- type:NormalExercise lang:r xp:100 skills:1 key:f8b383874f
## Getting Started with Data

In this exercise, you will learn how to identify fundamental attributes of a data set.

One of R's built-in data sets is called `mtcars`. This data set is already in your workspace so if you type  `mtcars` into your R console, the entire data will come up in the output.

Sometimes the data can be very long so instead of viewing the entire thing, we can get a jist of the data by typing `head(dataset)` to get the first 6 entries or `tail(dataset)` to get the last 6 entries. 

If we just want to know the variables in the data set, we can type `names(dataset)` into the console.

*** =instructions
- Use the `head()` function to get the first 6 entries of the mtcars data set
- Use `tail()` to get the last 6 entries.
- Find the variable names by using the `names()` function.
- Click the 'Submit Answer' Button and take a look at the R output in the console.


*** =hint
The data set is named `mtcars` so substitute `mtcars` for `(dataset)`.

*** =pre_exercise_code
```{r}
mtcars
```

*** =sample_code
```{r}
#Use appropriate function to find first 6 entries of mtcars

#Use appropriate function to find last 6 entries of mtcars

#Use appropriate function to find the variables of mtcars
```

*** =solution
```{r}
#Use appropriate function to find first 6 entries of mtcars
head(mtcars)

#Use appropriate function to find last 6 entries of mtcars
tail(mtcars)

#Use appropriate function to find the variables of mtcars
names(mtcars)
```

*** =sct
```{r}

test_function("head", args = "x")
success_msg("Nice job!")

success_msg("Good work!")
```
