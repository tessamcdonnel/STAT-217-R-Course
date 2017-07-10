---
title       : Lab 3
description : Summarizing and Visualizing Data

--- type:NormalExercise lang:r xp:100 skills:1 key:fe98ce0ad3
## Using the srt() function to reveal Variable Types

If we want to know the *types of variables* in our data set, we can type the command `str(dataset)` into the R Console.

This will return all of the variable names as well as their type (i.e. numeric, factor). *Categorical* variables will be will be `factor` variable types and *quantitative* variables will be `numeric`.

For this lab, we will continue to use the dataset `mtcars` from lab 2. 
*** =instructions
- Use the `str()` function to find the variable types of `mtcars`

*** =hint

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# Find the variable types of mtcars
```

*** =solution
```{r}
# Find the variable types of mtcars
str(mtcars)
```







*** =sct
```{r}
test_student_typed("str(mtcars)")
```

--- type:NormalExercise lang:r xp:100 skills:1 key:53e494b387
## Changing Variable Types

As you can see from the last exercise, each variable in `mtcars` is coded as numeric, but this is incorrect.

Take a look at the `mtcars` dataset by typing `?mtcars` into the R Console. 

R thinks the *Transmission* variable (am) is 'numeric' but really it should be coded as 'factor' because it only takes on values 0 and 1. 

In this exercise we are going to recode the `am` variable to a factor.


*** =instructions
- Copy this code to your R script: mtcars$am <- factor(mtcars$am, labels = c("automatic", "Manual"))
- Use the `str()` function on `mtcars` to make sure the `am` variable was correctly recoded to a factor variable

*** =hint

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# Type the code from the 'Instructions' box to change the *am* variable to a factor variable

# Use the str() function on mtcars
```

*** =solution
```{r}
# Type the code from the 'Instructions' box to change the *am* variable to a factor variable
mtcars$am <- factor(mtcars$am, labels = c("automatic", "Manual"))
# Use the str() function on mtcars
str(mtcars)
```

*** =sct
```{r}

```
