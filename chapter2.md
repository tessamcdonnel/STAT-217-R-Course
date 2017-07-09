---
title       : Lab 2
description : Using R to Explore Data Sets

--- type:NormalExercise lang:r xp:100 skills:1 key:f8b383874f
## Getting Started with Data

In this exercise, you will learn how to identify fundamental attributes of a data set.

One of R's built-in data sets is called `mtcars`. This data set is already in your workspace so if you type  `mtcars` into your R console, the entire data will come up in the output.

Sometimes the data can be very long so instead of viewing the entire thing, we can get a jist of the data by typing `head(dataset)` to get the first 6 entries or `tail(dataset)` to get the last 6 entries. 

If we just want to know the variables in the data set, we can type `names(dataset)` into the console.

If we want to know the dimensions of a dataset (ie. how many variables and entries) use the `dim(dataset)` function.

*** =instructions
- Use the `head()` function to get the first 6 entries of the mtcars data set
- Use `tail()` to get the last 6 entries.
- Find the variable names by using the `names()` function.
- Use `dim()` to find the dimensions of mtcars
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

#Use appropriate function to find the dimension of mtcars
```

*** =solution
```{r}
#Use appropriate function to find first 6 entries of mtcars
head(mtcars)

#Use appropriate function to find last 6 entries of mtcars
tail(mtcars)

#Use appropriate function to find the variables of mtcars
names(mtcars)

#Use appropriate function to find the dimension of mtcars
dim(mtcars)
```

*** =sct
```{r}

test_function("head", args = "x")
success_msg("Nice job!")

test_function("tail", args = "x")
success_msg("Good work!")

test_function("names", args = "x")
success_msg("Good work!")

test_function("dim", args = "x")
success_msg("Good work!")
```




--- type:NormalExercise lang:r xp:100 skills:1 key:795745ad44
## Accessing Specific Variables  using $

In this exercise you will be learning how to access specific variables within a data set by using the format `dataset$variable`.

From the previous exercise, we saw that `mtcars` has a *miles per gallon* variable named `mpg`. If we want to look at this variable by itself, we can type `mtcars$mgp` into the R console; this will return a list of *miles per gallon* entries. 


*** =instructions
- The mtcars data set also has the variable *weight* named `wt`. Use `$` to access the `wt` variable from the mtcars data set.
*** =hint

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# Access wt from mtcars like we did for the mpg variable
```

*** =solution
```{r}
# Access wt from mtcars like we did for the mpg variable
mtcars$wt
```

*** =sct
```{r}
test_student_typed("mtcars$wt")
```
