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


In this exercise we'll be using a dataset called `peanut_allergy` which contains data on children involved in a peanut allergy study. 

- there are 3 variables in this data set: `had_early_risk`, `regimen`, and `allergic`.
- there are 628 subjects 
- `peanut_allergy` is already in your workspace


*** =instructions
- Take a random sample of 25 from the variable `allergic` in the `peanut_allergy` dataset.
- Take a random sample of 50 from the variable `regimen` in the `peanut_allergy` dataset.
*** =hint
For the 1st instruction, follow the format in the lesson but use peanut_allergy$allergic and 25.

For the 2nd instruction, follow the format in the lesson but use peanut_allergy$regimen and 50.
*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/peanut_allergy.R")


```

*** =sample_code
```{r}
# take a random sample of 25 from the allergic variable


# take a random sample of 50 from the regimen variable

```

*** =solution
```{r}
# take a random sample of 25 from the allergic variable
sample(peanut_allergy$allergic, 25)

# take a random sample of 50 from the regimen variable
sample(peanut_allergy$regimen, 50)
```

*** =sct
```{r}
test_function("sample", args = c("x", "size"), index = 1, incorrect_msg = "Follow the format in the lesson with the specified dataset (peanut_allergy), variable (allergic), and number (25)!")
test_function("sample", args = c("x", "size"), index = 2, incorrect_msg = "Follow the format in the lesson with the specified dataset (peanut_allergy), variable (regimen), and number (50)!")

```

--- type:NormalExercise lang:r xp:100 skills:1 key:190f70cfa4
## Random Samples Continued...

In this exercise, we are going to take two random samples and assign them to object names using the assignment notation `<-`. 


Note: Remember that after we create an object (i.e. sample1 and sample2) we need to type the object name to view it *(I have already typed this for you in the R Script)*.
*** =instructions
- take a random sample of 20 from the variable `allergic` in the `peanut_allergy` dataset, assign this to `sample1`
- take another random sample of 20 from the same variable, but assign this sample to `sample2`
- After clicking 'Submit Answer', look at the contents of `sample1` and `sample2`. Are they the same?
*** =hint
Make sure you follow the format: `sample(dataset$variable, number)` with specified dataset, variable and number.
*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/peanut_allergy.R")

```

*** =sample_code
```{r}
# take a random sample of 20 from the variable allergic
sample1 <- 

sample1

# take another random sample of 20 from the variable allergic
sample2 <- 

sample2


```

*** =solution
```{r}
# take a random sample of 20 from the variable allergic
sample1 <- sample(peanut_allergy$allergic, 20)


sample1

# take another random sample of 20 from the variable allergic
sample2 <- sample(peanut_allergy$allergic, 20)


sample2

```

*** =sct
```{r}
test_object("sample1", incorrect_msg = "Make sure you follow the format: sample(dataset$variable, number) with specified dataset, variable and number.")

test_object("sample2", incorrect_msg = "Make sure you follow the format: sample(dataset$variable, number) with specified dataset, variable and number.")
success_msg("Nice job! Look at the R output in the bottom right panel. Do the contents of sample1 and sample2 match up?.")

```

--- type:NormalExercise lang:r xp:100 skills:1 key:2217632b88
## Using the set.seed() function

You probably noticed that two samples you took (of the same variable and size) were not the same. 

This is because `sample1` and `sample2` are *random* samples; so each time R takes a random sample of 20 from `allergic`, the values will be different.

Sometimes we want to have a *consistent* random sample because it's confusing when the values change every time you Knit a R Markdown document. To do this, we use the `set.seed(number)` function. If you type this **before** creating your random sample, your sample will be the ***same*** random sample every time you Knit the document.

Note: Any number can go inside the `set.seed()` function.
*** =instructions
- Type `set.seed(1234)` in the R Script.
- Now, use the `sample()` function to get a random sample of 20 from the `allergic` variable in the `peanut_allergy` dataset.
*** =hint
- You can copy and paste `set.seed(1234)` or type `set.seed(__)` with any number in the parenthesis.

- To take a random sample of a variable use the format:

`sample(dataset$variable, number)`

*** =pre_exercise_code
```{r}

source("https://www.openintro.org/stat/data/peanut_allergy.R")

```

*** =sample_code
```{r}
# Type set.seed(1234)

# take a random sample of 20 from the allergic variable 



```

*** =solution
```{r}
# Type set.seed(1234)
set.seed(1234)

# take a random sample of 20 from the allergic variable 
sample(peanut_allergy$allergic, 20)
```

*** =sct
```{r}
test_function("set.seed", args = "seed", eval = NA, incorrect_msg = "Copy and paste the set.seed() function from the first instruction. You can can change the number inside the function if you want; I arbitrarily chose '1234' but any whole number will work.")

test_function("sample", args = c("x", "size"), incorrect_msg = "Remember, to take a random sample from a variable use the format: sample(dataset$variable, number) with the specified parameters.")

```

--- type:NormalExercise lang:r xp:100 skills:1 key:b86b269872
## Population Proportions

For this exercise, you are going to find the *population proportion* of children who developed an allergic reation to peanuts.

We will treat this data set as the entire population of interest.



*** =instructions
- Use the `table()` function to get an appropriate summary of the `allergic` variable in the `peanut_allergy` data set.
- Click the 'Submit Answer' button and look at the R output.
- Use R as a calculator to find the proportion of children who were allergic to peanuts.

*** =hint
The correct format to summarize a categorical variable is:

`table(dataset$variable)`.

For the last instruction, divide the number of children who were allergic by the total number of children.
*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/peanut_allergy.R")
```

*** =sample_code
```{r}
# Create a table of the `allergic` variable in the `peanut_allergy` dataset

# Find the proportion of children who were allergic


```

*** =solution
```{r}
# Create a table of the `allergic` variable in the `peanut_allergy` dataset
table(peanut_allergy$allergic)

# Find the proportion of children who were allergic

```

*** =sct
```{r}
test_function("table", args = "...", incorrect_msg = "Remember, the correct format for the table() function is: table(dataset$variable). Create a table with this format using the specified data set and variable.")

success_msg("Nice! Now divide the number of children who were allergic by the total number of children in the data set. This will give you the 'population' proportion of children with a peanut allergy.")
```

--- type:NormalExercise lang:r xp:100 skills:1 key:38ce97a2e8
## Sample Proportions

Most of the time we don't know what the *population proportion* is, but we can estimate this value with a random sample. 

In this exercise, you will create a random sample of 50 from the `allergic` variable in the dataset `peanut_allergy` and then compare the *sample proportion* of allergic children to the *population proportion* you found in the last exercise.
*** =instructions
- Use the `sample()` function to create a sample of 50 from the `allergic` variable, assign this to `my_sample`.
- Use the `table()` function on `my_sample`.
- Click 'Submit Answer' and look at the R output to find how many children were allergic in `my_sample`.
- Find the ***sample proportion*** of allergic children.
- How does this compare to the *population proportion*?
*** =hint
For the first instruction, use the format sample(dataset$variable, #).

For the last instruction, divide the number of children who were allergic by the total number of children in the sample.

*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/peanut_allergy.R")

```

*** =sample_code
```{r}
# Use the format sample(dataset$variable, #) to get a sample of 50 from the `allergic` variable
my_sample <- 

# Type table(my_sample) to see how many children were allergic in the sample



```

*** =solution
```{r}
# Use the format sample(dataset$variable, #) to get a sample of 50 from the `allergic` variable
my_sample <- sample(peanut_allergy$allergic, 50)

# Type table(my_sample) to see how many children were allergic
table(my_sample)



```

*** =sct
```{r}
test_object("my_sample", incorrect_msg = "Make sure you follow the format: sample(dataset$variable, number) with specified dataset, variable and number, then assign it to my_sample.")
test_function("sample", args = c("x", "size"), incorrect_msg = "Type table(my_sample) to get a numerical summary of my_sample.")
```

--- type:NormalExercise lang:r xp:100 skills:1 key:0e23913548
## Confidence Intervals for Population Proportion

Assume that the population proportion of children with peanut allergies is unknown so we obtained a random sample. 

Finding the sample proportion is okay but adding a margin of error gives us much more insight.

In this exercise, we are going to use R as a calculator to find a 95% confidence interval for the true proportion of children who are allergic to peanuts *(population proportion)*.

Below is the formula to construct a confidence interval for a population proportion.

$\hat{p} \pm z\ast \sqrt{\frac{\hat{p}(1-\hat{p})}{n}}$

*** =instructions
Suppose I sampled 50 of the children from `peanut_allergy` and found that 0.15 reported *yes* to having a peanut allergy. Use R as a calculator to find a 95% confidence interval for the population proportion based on this sample data (Use the formula in the lesson).

Note that the $z\ast$ critical value is 1.96 for a 95% confidence interval.

*** =hint
- Use the formula in the lesson with $\hat{p}$ = 0.15, and n = 50.
- Find 'upper bound' and 'lower bound' seperately.
- When multiplying two things together use an asterisk $\ast$. For example, if we want to multiply 4 and 8 type `4*8`; typing `4(8)` will result in an error.
*** =pre_exercise_code
```{r}


```

*** =sample_code
```{r}
#Lower confidence bound

#Upper confidence bound



```

*** =solution
```{r}
#Lower confidence bound
0.15 - 1.96 * sqrt(.15*.85/50)

#Upper confidence bound
0.15 + 1.96 * sqrt(.15*.85/50)

```

*** =sct
```{r}
test_output_contains("0.05102485", incorrect_msg = "Follow the order of operations from your high school algebra class 'PEMDAS' and remember, when you want to square something in R, use the sqrt() function. For the lower confidence bound, subtract the margin of error from the sample proportion.")

test_output_contains("0.2489751", incorrect_msg = "Follow the order of operations from your high school algebra class 'PEMDAS' and remember, when you want to square something in R, use the sqrt() function. For the upper confidence bound, add the margin of error to the sample proportion.")


```
