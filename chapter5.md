---
title       : Lab 4b
description : Population and Sample Means


--- type:NormalExercise lang:r xp:100 skills:1 key:57cc190216
## Review Random Sampling

In this lab we'll be using another built-in R dataset called `ChickWeight` which contains data from an experiment on the effect of diet on chicks. 

- There are 4 variables in the data set: `weight`, `Time`, `Chick`, and `Diet`.
- This data set is already in your workspace so if you type  `ChickWeight` into your R console, the entire data will come up in the output.


In this exercise we are going take random samples from `ChickWeight` using the `sample()` function.

Remember, to take a random sample and save it to an object, use the format:

`sample_name <- sample(dataset$variable, number)`.

Note: Remember that after we create an object we need to type the object name to view it *(I have already typed this for you in the R Script)*.

*** =instructions
- take a random sample of 25 from the variable `weight` in the `ChickWeight` dataset, assign this to `sample_wt`.
- take a random sample of 50 from the variable `Diet` in the `ChickWeight` dataset, assign this to `sample_diet`
*** =hint
- For the 1st instruction, follow the format in the lesson but use ChickWeight$weight and 25

- For the 2nd instruction, follow the format in the lesson but use ChickWeight$Diet and 50
*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# take a random sample of 25 from the variable weight in ChickWeight dataset
sample_wt <- 

sample_wt

# take a random sample of 50 from the variable Diet in ChickWeight dataset
sample_diet <- 

sample_diet
```

*** =solution
```{r}
# take a random sample of 25 from the variable weight in ChickWeight dataset
sample_wt <- sample(ChickWeight$weight, 25)

sample_wt

# take a random sample of 50 from the variable Diet in ChickWeight dataset
sample_diet <- sample(ChickWeight$Diet, 50)

sample_diet
```

*** =sct
```{r}
test_function("sample", args = c("x", "size"))

```



--- type:NormalExercise lang:r xp:100 skills:1 key:7e24794db5
## Population Distribution


For this exercise, you are going to find the *population distribution* of the quantitative variable `weight` in dataset `ChickWeight`.

We will treat the `ChickWeight` dataset as the entire population of interest.

*** =instructions
- use the `mean()` function to find the mean `weight` of the population of chicks in `ChickWeight`
- use the `sd()` function to find the standard deviation of chick `weight`
- use the `hist()` function to create a histogram of chick `weight`
- Click the 'Submit Answer' button and look at the R output
*** =hint
- Remember, to find the mean use format `mean(dataset$variable)`
- This is the same for `sd()` and `hist()`
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

Most of the time we don't know what the *population mean* is, but we can **estimate** this value with a random sample. 

In this exercise, you will create a random sample of 75 from the `weight` variable in the `ChickWeight` dataset and then compare the *sample mean* `weight` of chicks to the *population mean* you found in the last exercise.
*** =instructions
- use `sample()` to take a sample of 75 from the `weight` variable, assign this to `my_sample`
- use the `mean()` function to find the mean of `my_sample`
- use the `sd()` function to find the standard deviation of `my_sample`
- use the `hist()` function on `my_sample`
- click 'Submit Answer' and look at the R output.
- How do these values compare to the *population mean*?
*** =hint
For the first instruction, use the format `sample(dataset$variable, #)`

Type `mean(my_sample)`, `sd(my_sample)`, and  `hist(my_sample)` for other instructions.
*** =pre_exercise_code
```{r}


```

*** =sample_code
```{r}
# Use the format sample(dataset$variable, #) to get a sample of 75 from the `weight` variable
my_sample <- 

# Find the mean of your new sample

# Find the sd of your new sample

# Create a histogram of your new sample

```

*** =solution
```{r}
# Use the format sample(dataset$variable, #) to get a sample of 75 from the `weight` variable
my_sample <- sample(ChickWeight$weight, 75)

# Find the mean of your new sample
mean(my_sample)

# Find the sd of your new sample
sd(my_sample)

# Create a histogram of your new sample
hist(my_sample)

```

*** =sct
```{r}
test_function("sample", args = c("x", "size"))
test_function("mean", args = "x")
test_function("sd", args = "x")
test_function("hist", args = "x")
```

--- type:NormalExercise lang:r xp:100 skills:1 key:d7a8f825e2
## Confidence Interval for Population Mean

Assume that the population mean `weight` of chicks is unknown so we obtained a random sample. 

Finding the sample mean is okay but adding a margin of error gives us much more insight.

In this exercise, we are going to use R as a calculator to find a 95% confidence interval for the population mean *weight*.

Note: The equation in the *plots* panel is the formula for a confidence interval for a population mean.
*** =instructions
Suppose I sampled 75 of the chicks from `ChickWeight` and found some sample statistics:

* mean weight is 116.2
* standard deviation is 67.5
* for n = 75 and alpha = 0.05, the *t* value is 1.99
    
    
Use R as a calculator to find a 95% confidence interval for the population mean *weight* based on this sample data.

*** =hint
Use the formula in the *plots* panel with p = 0.15, and n = 50

Find 'upper bound' and 'lower bound' seperately
*** =pre_exercise_code
```{r}
plot(-1:1, -1:1, type = "n", xlab="", ylab="", xaxt = 'n', yaxt = 'n')
text(0, 0, expression(bar(x) %+-% t ^ {"*"} *  frac(s, sqrt(n))), cex = 4)


```

*** =sample_code
```{r}
#Lower confidence bound

#Upper confidence bound
```

*** =solution
```{r}
#Lower confidence bound
116.2 - 1.99 * (67.5/sqrt(75))

#Upper confidence bound
116.2 + 1.99 * (67.5/sqrt(75))
```

*** =sct
```{r}

```