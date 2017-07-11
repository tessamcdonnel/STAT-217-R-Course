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


In this exerceise we'll using another built-in R dataset called `ChickWeight` which contains data from an experiment on the effect of diet on chicks. 

- There are 4 variables in the data set: `weight`, `Time`, `Chick`, and `Diet`.
- This data set is already in your workspace so if you type  `ChickWeight` into your R console, the entire data will come up in the output.


*** =instructions
- take a random sample of 25 from the variable `weight` in the `ChickWeight` dataset
- take a random sample of 50 from the variable `Diet` in the `ChickWeight` dataset
*** =hint
For the 1st instruction, follow the format in the lesson but use ChickWeight$weight and 25

For the 2nd instruction, follow the format in the lesson but use ChickWeight$Diet and 50
*** =pre_exercise_code
```{r}


```

*** =sample_code
```{r}
# take a random sample of 25 from the variable weight


# take a random sample of 50 from the variable Diet

```

*** =solution
```{r}
# take a random sample of 25 from the variable weight
sample(ChickWeight$weight, 25)

# take a random sample of 50 from the variable Diet
sample(ChickWeight$Diet, 50)
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
- take a random sample of 30 from the variable `weight` in the `ChickWeight` dataset, assign this sample to `sample1`
- take another random sample of 30 from the same variable, but assign this sample to `sample2`
- After clicking 'Submit Answer', look at the contents of `sample1` and `sample2`. Are they the same?
*** =hint

*** =pre_exercise_code
```{r}


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
sample1 <- sample(ChickWeight$weight, 30)


sample1

# take another random sample of 30 from the variable allergic
sample2 <- sample(ChickWeight$weight, 30)


sample2
```

*** =sct
```{r}
test_function("sample", args = c("x", "size"))
```

--- type:NormalExercise lang:r xp:100 skills:1 key:2217632b88
## Using the set.seed() function

You probably noticed that two samples you took (of the same variable and size) were not the same. 

This is because `sample1` and `sample2` are *random* samples; so each time R takes a random sample of 30 *weights* the values will be different.

One way to control this is using `set.seed(number)` function. If you type this before creating your random sample, your sample won't change every time you Run or Knit it.

Note: *Any* number can go inside the `set.seed()` function
*** =instructions
- type `set.seed(1234)` in the R Script
- now, take a random sample of 30 from the `weight` variable in the `ChickWeight` dataset
*** =hint

*** =pre_exercise_code
```{r}


```

*** =sample_code
```{r}
# Type set.seed(1234)

# take a random sample of 30 chick weights 
```

*** =solution
```{r}
# Type set.seed(1234)
set.seed(1234)

# take a random sample of 30 from `allergic` 
sample(ChickWeight$weight, 30)
```

*** =sct
```{r}
test_function("set.seed", args = "seed")

test_function("sample", args = c("x", "size"))

```

--- type:NormalExercise lang:r xp:100 skills:1 key:b86b269872
## <<<New Exercise>>>


*** =instructions

*** =hint

*** =pre_exercise_code
```{r}
plot(-1:1, -1:1, type = "n", xlab="", ylab="", xaxt = 'n', yaxt = 'n')
text(0, 0, expression(sd == sqrt(frac(p*(1-p), n))))
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
