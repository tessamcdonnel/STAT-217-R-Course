---
title       : Lab 3
description : Summarizing and Visualizing Data

--- type:NormalExercise lang:r xp:100 skills:1 key:fe98ce0ad3
## Using the srt() function to reveal Variable Types

If we want to know the *types of variables* in our data set, we can type the command `str(dataset)` into the R Console.

This will return all of the variable names as well as their type (i.e. numeric, factor, integer). 

*Categorical* variables will be will be `factor` variable types.

*Quantitative* variables will be `numeric` and `integer` variable types.

For this lab, we will continue to use the dataset `mtcars` from lab 2. 
*** =instructions
- Use the `str()` function to find the variable types of `mtcars`
- Click the 'Submit Answer' Button and take a look at the R output in the console.

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

R thinks the *Transmission* variable `am` is 'numeric' but really it should be coded as 'factor' because it is a categorical variable. The `am` variable only takes on two values *(0 = automatic, 1 = manual)*. 

In this exercise we are going to recode the `am` variable from a numeric to a factor variable type.


*** =instructions
- Copy this code to your R script: `mtcars$am <- factor(mtcars$am, labels = c("automatic", "manual"))`
- Use the `str()` function on `mtcars` 
- Click the 'Submit Answer' Button and take a look at the R output in the console. Make sure the `am` variable was correctly recoded to a factor variable
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

--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:ee655438c8
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

--- type:NormalExercise lang:r xp:100 skills:1 key:b715998152
## Summarizing Qauntitative Variables


In this exercise, you will learn how to use some of the R built-in functions to obtain statistics of your data set. Here are a few very common functions:

`mean(dataset$variable)`: gives you the mean of a specific quantitative variable

`median(dataset$variable)`: gives you the median of a specific quantitative variable

`sd(dataset$variable)`: gives you the standard deviation of a specific quantitative variable

`iqr(dataset$variable)`: gives you the interquartile range of a specific quantitative variable

The dataset we've been working with `mtcars` is already in your workspace.

*** =instructions
- Find the mean *weight* of the `mtcars` dataset using `mean()` function.
- Find the median *weight* of `mtcars` using `median()` function.
- Find the standard deviation of the *weight* variable in `mtcars` using the `sd()` function.

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




--- type:NormalExercise lang:r xp:100 skills:1 key:c7db7fdc55
## Summarizing categorical Variables

To summarize categorical variables, we can use the `table()` function to see the frequency of occurences at each level of the categorical variable.

To create a table, use the form:

`table(dataset$categ_var)`

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



--- type:NormalExercise lang:r xp:100 skills:1 key:9fc43281cb
## Contingency Tables

A contingency table is used to summarize the relationship betweeen categorical variables. 

In this exercise we will create a contingency table by cross-classifying two variables using the `table()` function with the form:

`table(dataset$var1, dataset$var2)`

Note: The variable listed first (var1) will go along the rows and the variable listed second (var2) will go along the columns.

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
--- type:NormalExercise lang:r xp:100 skills:1 key:9a4fea2da0
## Visualizing Quantitative Data in R
The two main visualizations of quantitative data are:

*Histogram* - represents the distribution of quantitative data

- use `hist(dataset$variable)` to create a histogram

*Boxplot* - used to visualize the variation of quantitative data

- use `boxplot(dataset$variable)` to create a boxplot

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


--- type:NormalExercise lang:r xp:100 skills:1 key:b65646dd8a
## Visualizing Categorical Data in R

The most common way to visualize categorical variables is by creating a *barplot*.

To do this in R, use the form:

`barplot(table(dataset$categ_var))`

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



--- type:NormalExercise lang:r xp:100 skills:1 key:c6f71ca0bd
## Visualizing Relationships between 2 Quantitative Variables

If we have two quantitative variables, we can visualize their relationship with the `plot()` function. 

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



--- type:NormalExercise lang:r xp:100 skills:1 key:fca8885b03
## Visualizing Quantitative Variables by Groups

Sometimes we want to compare a quantitative variable across the different groups of a categorical variable. 

To do this, we can use the `boxplot()` function of the form:

`boxplot(dataset$quant_var ~ dataset$categ_var)`

This will produce side by side boxplots.

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
