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

--- type:NormalExercise lang:r xp:100 skills:1 key:15bd840872
## Working with Variables

We can also use arithetic operators on variables. 

For example, if I want to add two variables together, i would type `dataset$var1 + dataset$var2`. If I want to save this sum as a new variable, I would assign it to a name `dataset$newvar <- dataset$var1 + dataset$var2`.

In this exercise, we will be creating a new variable *density of car* named `density`. 

The mtcars data set is alrady in your work space. The variables you will need to access to create a *density* variable are *displacement* named `disp` and *weight* named `wt`.

For simplicity, we will let:

*density = weight/displacement*

*** =instructions
- Use the formula `dataset$density <- dataset$var1 / dataset$var2` to create a density variable.
- Use the `names()` function on `mtcars` to make sure that `density` was added to the variables.
*** =hint
substitute `mtcars` for dataset
*** =pre_exercise_code
```{r}
mtcars
```

*** =sample_code
```{r}
# Create *density* variable for mtcars
mtcars$density <- 

# Use names() to check if *density* was added
```

*** =solution
```{r}
# Create *density* variable for mtcars
mtcars$density <- mtcars$wt / mtcars$disp

# Use names() to check if *density* was added
names(mtcars)
```

*** =sct
```{r}
test_object("mtcars$density")

test_student_typed("names(mtcars)")
```









--- type:NormalExercise lang:r xp:100 skills:1 key:f759511088
## Using R functions to find Statistics

In this exercise, you will learn how to use some of the R built-in functions to obtain statistics of your data set. Here are a few very common functions:

`mean(dataset$variable)`: gives you the mean of a specific quantitative variable

`median(dataset$variable)`: gives you the median of a specific quantitative variable

`sd(dataset$variable)`: gives you the standard deviation of a specific quantitative variable

`summary(dataset$variable)`: gives a few summary statistics of a specific quantitative variable

The dataset we've been working with `mtcars` is already in your workspace.

*** =instructions
- Find the mean *weight* of the `mtcars` dataset using `mean()`.
- Find the median *weight* of `mtcars` using `median()`.
- Find the standard deviation of the `mtcars` `wt` variable.

*** =hint
substitute `mtcars` for dataset

*** =pre_exercise_code
```{r}
mtcars
```

*** =sample_code
```{r}
# Find the mean weight (wt) of mtcars 

# Find the median weight (wt) of mtcars

# Find the standard deviation of the weight (wt) of mtcars.
```

*** =solution
```{r}

# Find the mean weight (wt) of mtcars 
mean(mtcars$wt)

# Find the median weight (wt) of mtcars
median(mtcars$wt)

# Find the standard deviation of the weight (wt) of mtcars.
sd(mtcars$wt)
```

*** =sct
```{r}
test_function("mean", args = "x")
test_function("median", args = "x")
test_function("sd", args = "x")


```
--- type:NormalExercise lang:r xp:100 skills:1 key:59b987e2d7
## Using < > != == to make Comparisons



*** =instructions

*** =hint

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}

```

*** =solution
```{r}

```

*** =sct
```{r}

```
