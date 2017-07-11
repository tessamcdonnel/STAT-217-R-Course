---
title       : Lab 4b
description : Population and Sample Means


--- type:NormalExercise lang:r xp:100 skills:1 key:57cc190216
## Population Mean and Distribution

In this lab we'll be using another built-in R dataset called `ChickWeight` which contains data from an experiment on the effect of diet on chicks. 

- There are 4 variables in the data set: `weight`, `Time`, `Chick`, and `Diet`.
- This data set is already in your workspace so if you type  `ChickWeight` into your R console, the entire data will come up in the output.

We will treat this data set as the entire population of interest.

For this exercise, you are going to find the *population distribution* of the quantitative variable `weight` in dataset `ChickWeight`.

*** =instructions
- use the `mean()` function to find the mean `weight` of the population of chicks in `ChickWeight`
- use the `sd()` function to find the standard deviation of chick `weight`
- use the `hist()` function to create a histogram of chick `weights`
*** =hint

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# Find the mean weight of chicks in the population (dataset)

# Find the standard deviation of weight for chicks in the population (dataset)

# Create a histogram of chick weights
```

*** =solution
```{r}
# Find the mean weight of chicks in the population (dataset)
mean(ChickWeight$weight)
# Find the standard deviation of weight for chicks in the population (dataset)
sd(ChickWeight$weight)
# Create a histogram of chick weights
hist(ChickWeight$weight)
```

*** =sct
```{r}
test_function("mean", args = "x")
test_function("sd", args = "x")
test_function("hist", args = "x")
```

--- type:NormalExercise lang:r xp:100 skills:1 key:4face42bf0
## Sample Mean and Distribution

* random sample of 75 chicks and find summary stats/ hist on it

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

--- type:NormalExercise lang:r xp:100 skills:1 key:d7a8f825e2
## Confidence Interval for Population Mean


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
