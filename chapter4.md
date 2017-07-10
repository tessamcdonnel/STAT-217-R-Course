---
title       : Lab 4a
description : Distribution of Sample Proportions and Confidence Intervals for Population Proportions


--- type:NormalExercise lang:r xp:100 skills:1 key:1c2ca885bb
## Taking Random Samples from a Variable 

In this lab, you are going to learn how to take random samples from a variable using the `sample()` function.

The `sample()` function takes two arguements:

1) variable that you want to sample
2) sample size

To take a random sample of a variable use the format:

`sample(dataset$variable, number)`


In this exerceise we'll taking two random samples from another built-in R dataset called `peanut_allergy` which contains data on children involved in a peanut allergy experiment. 

This data set is already in your workspace so if you type  `peanut_allergy` into your R console, the entire data will come up in the output.


Note: Remember that after we create an object (i.e. sample1 and sample2) we need to type the object name to view it.
*** =instructions
- take a random sample of 30 from the variable `allergic` in the `peanut_allergy` dataset, assign this sample to `sample1`
- take another random sample of 30 from the same variable, but assign this sample to `sample2`
- After clicking 'Submit Answer', look at the contents of `sample1` and `sample2`. Are they the same?
*** =hint

*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/peanut_allergy.R")


```

*** =sample_code
```{r}
# take a random sample of 30 from the variable allergic
sample1 <- 

sample1

# take another random sample of 30 from the variable allergic
sample2 <- 

sample2
```

*** =solution
```{r}
# take a random sample of 30 from the variable allergic
sample1 <- sample(peanut_allergy$allergic, 30)


sample1

# take another random sample of 30 from the variable allergic
sample2 <- sample(peanut_allergy$allergic, 30)


sample2
```

*** =sct
```{r}
test_function("sample", args = c("x", "size"))
```
