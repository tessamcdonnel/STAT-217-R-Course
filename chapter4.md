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


In this exerceise we'll using another built-in R dataset called `peanut_allergy` which contains data on children involved in a peanut allergy experiment. 

There are 3 variables in the data set: `had_early_risk`, `regimen`, and `allergic`.

This data set is already in your workspace so if you type  `peanut_allergy` into your R console, the entire data will come up in the output.


*** =instructions
- take a random sample of 25 from the variable `allergic` in the `peanut_allergy` dataset
- take a random sample of 50 from the variable `regimen` in the `peanut_allergy` dataset
*** =hint

*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/peanut_allergy.R")


```

*** =sample_code
```{r}
# take a random sample of 25 from the variable allergic


# take a random sample of 50 from the variable regimen

```

*** =solution
```{r}
# take a random sample of 25 from the variable allergic
sample(peanut_allergy$allergic, 25)

# take a random sample of 50 from the variable regimen
sample(peanut_allergy$regimen, 50)
```

*** =sct
```{r}
test_function("sample", args = c("x", "size"))
```

--- type:NormalExercise lang:r xp:100 skills:1 key:190f70cfa4
## Random Samples Continued...

In this exercise, we are going to take two random samples and assign them to object names using the assignment notation `<-`. 


Note: Remember that after we create an object (i.e. sample1 and sample2) we need to type the object name to view it *(I have already typed this for you in the R Script)*.
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


--- type:NormalExercise lang:r xp:100 skills:1 key:2217632b88
## Using the set.seed() function

You probably noticed that two samples you took (of the same variable and size) were not the same. 

This is because `sample1` and `sample2` are *random* samples; so each time R takes a random sample of 30 from `allergic` it will be different.

If we just want one random sample, it can get confusing to to find results because each time we run the `sample()` command, we will get different numbers. 

One way to control this is using `set.seed(number)` function. If you type this before creating your random sample, your sample won't change every time you Run or Knit it.

Note: *Any* number can go inside the `set.seed()` function
*** =instructions
- type `set.seed(1234)` in the R Script
- now, take a random sample of 30 from `allergic` in `peanut_allergy` dataset
*** =hint

*** =pre_exercise_code
```{r}

source("https://www.openintro.org/stat/data/peanut_allergy.R")


```

*** =sample_code
```{r}
# Type set.seed(1234)

# take a random sample of 30 from `allergic` 
```

*** =solution
```{r}
# Type set.seed(1234)
set.seed(1234)

# take a random sample of 30 from `allergic` 
sample(peanut_allergy$allergic, 30)
```

*** =sct
```{r}
test_function("set.seed", args = "seed")

test_function("sample", args = c("x", "size"))

```
