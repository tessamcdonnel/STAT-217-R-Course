---
title       : Lab 5
description : One-sample t-test


--- type:NormalExercise lang:r xp:100 skills:1 key:9c0a9256c3
## Assumptions of the t-test

Before testing a hypothesis with a t-test, we need to make sure that our data meets these 4 assumptions:

* the variable we're testing is quantitative
* the observations are independent
* the variable is normally distributed
* no extreme outliers

We'll be using the same dataset from the last lab `cdc`. This data is from a random sample so the observations can be treated as independent.

In this exercise, you will be checking the normality assumption for the `age` variable in `cdc`.

*The normality assumption is met if a histogram of the variable looks approximately symmetric and bell-shaped.*

Note: The *mosaic* package is already in your workspace.

*** =instructions
- Use the `favstats()` function to examine the distribution of `age`.
- Use the `hist()` function to make sure `age` follows the *normality* assumption.
*** =hint
For the first instruction, use the format `favstats(dataset$variable)`.

To create a histogram, use `hist(dataset$variable)`.



*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/cdc.R")
library(mosaic)
```

*** =sample_code
```{r}
# Find the summary statistics of age using the favstats() function

# Check for normallity using the hist() function


```

*** =solution
```{r}
# Find the summary statistics of `variable` using the favstats() function
favstats(cdc$age)

# Check for normallity using the hist() function
hist(cdc$age)

```



*** =sct
```{r}
test_function("favstats", args = "x")
test_function("hist", args = "x")
```


--- type:NormalExercise lang:r xp:100 skills:1 key:52ad764c46
## Using the t.test() function

Suppose we want to:

* perform a t-test to determine if the population mean `age` differs from 40, and, 
* build a 95% confidence interval to estimate the true mean `age`. 

We can do this in one step with the `t.test()` function in R.

The default settings are to perform a 2-sided alternative hypothesis and to calculate a 95% confidence interval.

So, to carry out a one sample t-test for a 2-sided alternative and a 95% confidence interval, use the format:

`t.test(x = dataset$variable, mu = null_hyp)`



*** =instructions
- Use the `t.test()` function to carry out a one sample t-test to determine if the population mean `variable` differs from `null` on average and use a 95% confidence interval to estimate the population mean.
- click 'Submit Answer' and look at the R output.

*** =hint
- follow format from lesson with cdc$age instead of dataset$variable and  `40` instead of null_hyp
*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/cdc.R")

```

*** =sample_code
```{r}
# Perform a t-test using the t.test() function 



```

*** =solution
```{r}
# Perform a t-test using the t.test() function 
t.test(x = cdc$age, mu = 40)

```

*** =sct
```{r}
test_function("t.test", args = c("x", "mu"))


```




--- type:NormalExercise lang:r xp:100 skills:1 key:eeccda0836
## One-sided Hypothesis Tests

Sometimes we a have a one-sided alternative hypothesis (For example, the alternative is less than the null hypothesis). 

The `t.test()` function can still do this, but we have to specify additional arguments.

To specify a one-sided alternative, use the format:

`t.test(x = dataset$variable, mu = null_hyp, alternative = "")`


If our alternative hypothesis is *less than*, use:
`alternative = "less"`

If our alternative hypothesis is *greater than*, use:
`alternative = "greater"`




*** =instructions
Use the `t.test()` function to carry out a one sample t-test to determine if the population mean `variable` is **greater than** the null on average.
*** =hint
- The code is the same as the last time with the added argument: `alternative = "greater"`
*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/cdc.R")

```

*** =sample_code
```{r}
# use the t.test to perform a one-sided greater than test


```

*** =solution
```{r}
# use the t.test to perform a one-sided greater than test

t.test(x = cdc$height, mu = 70, alternative = "greater")

```

*** =sct
```{r}
test_function("t.test", args = c("x", "alternative", "mu"))

```



--- type:NormalExercise lang:r xp:100 skills:1 key:198408a028
## Specifying Confidence Levels

We can also change the confidence level by adding the argument: `conf.level = `. 

For example, if I want a 99% confidence interval for the mean `var`, I would type:

`t.test(x = cdc$height, mu = 70, conf.level = 0.99)`


*** =instructions
Use the `t.test()` function to carry out a one sample t-test to determine if the population mean `variable` **differs** from null on average and use a 90% confidence interval to estimate the population mean.
*** =hint

*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/cdc.R")

```

*** =sample_code
```{r}
# Carry out a t-test and find a 99% confidence interval

```

*** =solution
```{r}
# Carry out a t-test and find a 99% confidence interval
t.test(x = cdc$height, mu = 70, conf.level = 0.90)
```

*** =sct
```{r}
test_function("t.test", args = c("x", "mu", "conf.level"))

```



--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:583cc22e56
## Check for Understanding

If I want to construct a 95% confidence interval on the hypothesis in the *plots* panel, what is the correct R command?
*** =instructions

*** =hint

*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/cdc.R")
plot(-6:6, -6:6, type = "n", xlab="", ylab="", xaxt = 'n', yaxt = 'n')
text(0, 3, expression(paste("Ho:", mu, "=5")), cex = 3)
text(0, -3, expression(paste("Ha:", mu, ">5")), cex = 3)



```

*** =sct
```{r}

```
--- type:NormalExercise lang:r xp:100 skills:1 key:2a8c8123f8
## Factors that effect the test conclusion

`t.test(x = dataset$variable, mu = null_hyp, alternative = alt_hyp, conf.level = %conf)`

- closeness of sample mean and alternative hypothesis
- one-sided, two-sided
- alpha

*** =instructions

*** =hint

*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/cdc.R")

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





--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:f14e01c77b
## Check for Understanding


The default settings for a t.test function (eg. `t.test(evals$cls_perc_eval,mu=80`) ) are to  perform a _________ alternative hypothesis and to calculate a ______ confidence interval.

*** =instructions
- two-sided, 90%
- two-sided, 95%
- one-sided, 95%
- one-sided, 90%
*** =hint

*** =pre_exercise_code
```{r}

```

*** =sct
```{r}

msg_bad <- "That is not correct"
msg_success <- "Exactly!"
test_mc(correct = 2, feedback_msgs = c(msg_bad, msg_success, msg_bad, msg_bad))

```

--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:45534c5588


#### t.test() arguments

Which argument should we specify in the t.test function to do a one sided Ha in a one sample t-test?



*** =instructions
- conf.level
- lower.tail
- upper.tail
- alternative 
*** =hint

*** =pre_exercise_code
```{r}

```

*** =sct
```{r}
msg_bad <- "That is not correct"
msg_success <- "Exactly!"
test_mc(correct = 4, feedback_msgs = c(msg_bad, msg_bad, msg_bad, msg_success))

```




