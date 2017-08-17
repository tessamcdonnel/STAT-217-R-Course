---
title       : Lab 8
description : Correlation and Simple Linear Regression



--- type:NormalExercise lang:r xp:100 skills:1 key:283c94164f
## Gun violence data

In this pre-lab, we'll be using a data set called `gun_violence_us` which contains gun ownership and mortality statistics in the United States.

- there are 3 variables: `state`, `ownership_rate`, `mortality_rate`
- `gun_violence_us` is already in your workspace

`ownership_rate`: percentage of adults in each state who own a gun
`mortality_rate`: number of deaths per 100,000 people 

Let's begin by exploring the data set.
*** =instructions
- Use the `head()` function on `gun_violence_us` to view the first six observations.
- Use the `summary()` function on `gun_violence_us` to obtain summary statistics for each variable.
*** =hint
Use the format `head(dataset)` for the first instruction and `summary(dataset)` for the second instruction.
*** =pre_exercise_code
```{r}
source("http://www.openintro.org/stat/data/gun_violence_us.R")
```

*** =sample_code
```{r}
# Use the `head()` function on `gun_violence_us` to view the first six observations.


# Use the `summary()` function on `gun_violence_us` to obtain summary statistics for each variable.


```

*** =solution
```{r}
# Use the `head()` function on `gun_violence_us` to view the first six observations.
head(gun_violence_us)

# Use the `summary()` function on `gun_violence_us` to obtain summary statistics for each variable.
summary(gun_violence_us)

```

*** =sct
```{r}
test_function("head", args = "x", incorrect_msg = "Make sure to use 'gun_violence_us' instead of 'dataset' inside the head() function.")

test_function("summary", args = "object", incorrect_msg = "Follow the format 'summary(dataset)' with the specified data set to obtain a summary of the entire data set.")

```

--- type:NormalExercise lang:r xp:100 skills:1 key:b81533a6c6
## Correlation

Suppose we want to test whether there is a relationship between `ownership_rate` and `mortality_rate` in the `gun_violence_us` data set.

Let's start by visualizing the relationship between these variables with the `plot()` function.

Remember, to create a scatterplot use the format:

`plot(dataset$var1, dataset$var2)`
*** =instructions
Use the `plot()` function to visualize the relationship between `ownership_rate` and `mortality_rate` where:

* var1 = `ownership_rate`
* var2 = `mortality_rate`
*** =hint

*** =pre_exercise_code
```{r}
source("http://www.openintro.org/stat/data/gun_violence_us.R")
```

*** =sample_code
```{r}
# Use the `plot()` function to visualize the relationship between `ownership_rate` and `mortality_rate`


```

*** =solution
```{r}
# Use the `plot()` function to visualize the relationship between `ownership_rate` and `mortality_rate`
plot(gun_violence_us$ownership_rate, gun_violence_us$mortality_rate)


```

*** =sct
```{r}
test_function("plot", args = c("x", "y"), incorrect_msg = "Remember to follow the format in the lesson with the specified data set and variables.")

success_msg("Nice! Now look at the plot. We can see that as gun ownership rates increase, mortality rates also increase")
```

--- type:NormalExercise lang:r xp:100 skills:1 key:23b4d73093
## Measuring correlation with the cor() function

We can use the `cor()` estimate the correlation between two quantitative variables 

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
