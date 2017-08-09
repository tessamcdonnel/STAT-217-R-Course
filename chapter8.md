---
title       : Lab 7
description : Inference for Categorical Data



--- type:NormalExercise lang:r xp:100 skills:1 key:616c48f5cf
## One sample z-test

In this course, we will use the one sample z-test to test whether a population *proportion* differs from a specific value.

To perform a one sample z-test, we'll be using a data set called `nc` which contains data on the North Carolina birth records in 2004. 

- there are 13 variables in this data set but we will use 
- there are 154 subjects 
- `nc` is already in your workspace

This data set contains a categorical variable called `lowbirthweight` with 2 levels:

- `low` (low birthweight)
- `not low` (not low birthweight)

Let's begin by exploring the `lowbirthweight` variable in the `nc` data set.

*** =instructions
- Use the `table()` function to get a summary of the `lowbirthweight` variable.
- Copy and paste the code below to generate a table with row/column totals:

`addmargins(table(nc$lowbirthweight))`

- Use R (or a hand calculator) to find the proportion of births that were classified as low birthweights.

*** =hint
Remember, to make a table use the format: `table(dataset$variable)`.
*** =pre_exercise_code
```{r}
```

*** =sample_code
```{r}
# Type table(dataset$categ_var) with specified data set and variable to get a table summary

# Copy and paste addmargins(table(nc$lowbirthweight)) to get margin totals

# Use R as a calculator to find the proportion of births that were classified as low birthweights.


```

*** =solution
```{r}
# Type table(dataset$categ_var) with specified data set and variable to get a table summary

# Copy and paste addmargins(table(nc$lowbirthweight)) to get margin totals

# Use R as a calculator to find the proportion of births that were classified as low birthweights.

```

*** =sct
```{r}

```














--- type:NormalExercise lang:r xp:100 skills:1 key:5d43584cb1
## Using the prop.test() function

Suppose that a previous study estimated the low birthweight to be 10%. In other words, 10% of all births in North Carolina are under weight. 


In this exercise you will use the `prop.test()` function to: perform a z-test to determine if our population proportion of `lowbirthweight` differs from .10, and, 

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
