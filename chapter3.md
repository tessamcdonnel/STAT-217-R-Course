---
title       : Lab 3
description : Summarizing and Visualizing Data

--- type:NormalExercise lang:r xp:100 skills:1 key:fe98ce0ad3
## Using the srt() function to reveal Variable Types

If we want to know the *types of variables* in our data set, we can type the command `str(dataset)` into the R Console.

This will return all of the variable names as well as their type (i.e. numeric, factor, integer). 

*Categorical* variables will be will be `factor` variable types and *quantitative* variables will be `numeric` and `integer`.

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


--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:ef8bf46853
## Quick Review of Variable Types

Is a `factor` coded variable an example of a *quantitative* variable or a *categorical* variable?

*** =instructions
- Quantitative
- Categorical
*** =hint

*** =pre_exercise_code
```{r}

```

*** =sct
```{r}
msg_bad <- "That's incorrect. A factor variable is a categorical variable!"
msg_success <- "Good answer!"

test_mc(correct = 2, feedback_msgs = c(msg_bad, msg_success))
```
--- type:NormalExercise lang:r xp:100 skills:1 key:53e494b387
## Changing Variable Types

As you can see from the last exercise, each variable in `mtcars` is coded as numeric, but this is incorrect.

Take a look at the `mtcars` dataset by typing `?mtcars` into the R Console. 

R thinks the *Transmission* variable (am) is 'numeric' but really it should be coded as 'factor' because it only takes on values 0 and 1 *(0 = automatic, 1 = manual)*. 

In this exercise we are going to recode the `am` variable to a factor.


*** =instructions
- Copy this code to your R script: `mtcars$am <- factor(mtcars$am, labels = c("automatic", "manual"))`
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
mtcars$am <- factor(mtcars$am, labels = c("automatic", "manual"))
# Use the str() function on mtcars
str(mtcars)
```

*** =sct
```{r}

```

--- type:NormalExercise lang:r xp:100 skills:1 key:b715998152
## Using R Functions To Find Statistics


In this exercise, you will learn how to use some of the R built-in functions to obtain statistics of your data set. Here are a few very common functions:

`mean(dataset$variable)`: gives you the mean of a specific quantitative variable

`median(dataset$variable)`: gives you the median of a specific quantitative variable

`sd(dataset$variable)`: gives you the standard deviation of a specific quantitative variable

`iqr(dataset$variable)`: gives you the interquartile range of a specific quantitative variable

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



--- type:NormalExercise lang:r xp:100 skills:1 key:9a4fea2da0
## Graphing Histograms in R


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
