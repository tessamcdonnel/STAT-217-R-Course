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
test_function("favstats", args = "x", incorrect_msg = "Make sure you follow the format favstats(dataset$variable) with the cdc dataset and 'age' variable")

test_function("hist", args = "x", incorrect_msg = "Make sure you follow the format hist(dataset$variable) with the cdc dataset and 'age' variable")
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
- Use the `t.test()` function to carry out a one sample t-test to determine if the population mean `age` differs from 40 on average and use a 95% confidence interval to estimate the population mean age.
- click 'Submit Answer' and look at the R output.

*** =hint
- follow format from lesson with `cdc$age` instead of dataset$variable and  40 instead of null_hyp
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
test_function("t.test", args = c("x", "mu"), incorrect_msg = "Make sure you substitute the correct dataset, variable and null hypothesis!")


```


--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:f14e01c77b
## Check for Understanding 1


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


--- type:NormalExercise lang:r xp:100 skills:1 key:eeccda0836
## One-sided Hypothesis Tests

Sometimes we a have a one-sided alternative hypothesis (For example, the hypothesis in the *plots* panel). 

The `t.test()` function can still do this, but we have to specify an additional argument.

To specify a one-sided alternative, use the format:

`t.test(x = dataset$variable, mu = null_hyp, alternative = "____")`


If our alternative hypothesis is *less than*, use:

`alternative = "less"`

If our alternative hypothesis is *greater than*, use:

`alternative = "greater"`




*** =instructions
Use the `t.test()` function to carry out a one sample t-test to determine if the population mean `age` is **less** than 40 on average.
*** =hint
- The code is the same as the last time with the added argument: `alternative = "less"`
*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/cdc.R")
plot(-6:6, -6:6, type = "n", xlab="", ylab="", xaxt = 'n', yaxt = 'n')
text(0, 3, expression(paste("Ho:", mu, "=40")), cex = 2)
text(0, -3, expression(paste("Ha:", mu, "<40")), cex = 2)
```

*** =sample_code
```{r}
# use the t.test() function to determine if the mean age is significantly greater than 40 


```

*** =solution
```{r}
# use the t.test() function to determine if the mean age is significantly greater than 40 

t.test(x = cdc$age, mu = 40, alternative = "less")

```

*** =sct
```{r}
test_function("t.test", args = c("x", "alternative", "mu"), incorrect_msg = "Everything is the same as the last exercise except for the added argument. The alternative argument should be equal to 'less'")

```



--- type:NormalExercise lang:r xp:100 skills:1 key:198408a028
## Specifying Confidence Levels

We can also change the confidence level by adding the argument: `conf.level = `. 

For example, if I want to test the hypothesis in the *Plots* panel and build a 99% confidence interval for the mean `age`, I would type:

`t.test(x = cdc$age, mu = 40, conf.level = 0.99)`


*** =instructions
Use the `t.test()` function to carry out a one sample t-test to determine if the population mean `age` **differs** from 40 on average and use a **90% confidence interval** to estimate the population mean age.
*** =hint
Make sure you specify the confidence level as a proportion. For example, to do a 80% confidence interval add `conf.level = 0.80`. This exercise is asking you to create a 90% confidence interval.
*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/cdc.R")
plot(-6:6, -6:6, type = "n", xlab="", ylab="", xaxt = 'n', yaxt = 'n')
text(0, 3, expression(paste("Ho: ", "mu ", "= 40")), cex = 2)
text(0, -3, expression("Ha: mu" != " 40"), cex = 2)

```

*** =sample_code
```{r}
# Carry out a t-test and find a 90% confidence interval

```

*** =solution
```{r}
# Carry out a t-test and find a 90% confidence interval
t.test(x = cdc$age, mu = 40, conf.level = 0.90)
```

*** =sct
```{r}
test_function("t.test", args = c("x", "mu", "conf.level"), incorrect_msg = "Have you set the conf.level equal to 0.90?")

```




--- type:NormalExercise lang:r xp:100 skills:1 key:5d2e26a906
## t.test() Practice
The `cdc` dataset has a variable called `wtdesire` which records the weight the subjects *wish* they were.

For this exercise, test the hypothesis in the plots panel with mu = mean of `wtdesire`.

*** =instructions
- Use the `t.test()` function to perform a t-test on `wtdesire` for the hypothesis in the *plots* panel and construct a 99% confidence interval.
*** =hint
- This is a one-sided test so `alternative="___"` should be called. 
- Since we want a 99% confidence interval, we need to specify `conf.level = 0.99`.
*** =pre_exercise_code
```{r}
plot(-6:6, -6:6, type = "n", xlab="", ylab="", xaxt = 'n', yaxt = 'n')
text(0, 3, expression(paste("Ho:", mu, "=150")), cex = 2)
text(0, -3, expression(paste("Ha:", mu, ">150")), cex = 2)
source("https://www.openintro.org/stat/data/cdc.R")

```

*** =sample_code
```{r}
# Use t.test to perform a t test on the hypothesis in the plots panel

```

*** =solution
```{r}
# Use t.test to perform a t test on the hypothesis in the plots panel
t.test(x = cdc$wtdesire, mu = 150, alternative = "greater", conf.level = 0.99)

```

*** =sct
```{r}
test_function("t.test", args = c("x", "mu", "alternative", "conf.level"), incorrect_msg = "Have you set the conf.level equal to 0.99 and alternative equal to 'greater'?")

```
--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:583cc22e56
## Check for Understanding 2

If I want to construct a 90% confidence interval on the hypothesis in the *plots* panel, what is the correct R command?
*** =instructions
- t.test(x = dataset$variable, alternative = "less", conf.level = 0.90)
- t.test(x = dataset$variable, mu = 5, alternative = "greater")
- t.test(x = dataset$variable, mu = 5, alternative = "less", conf.level = 0.90)
- t.test(x = dataset$variable, mu = 5, alternative = "less", conf.level = 90)

*** =hint
Remember, the default settings are to perform a 2-sided alternative hypothesis and to calculate a 95% confidence interval.

*** =pre_exercise_code
```{r}
plot(-6:6, -6:6, type = "n", xlab="", ylab="", xaxt = 'n', yaxt = 'n')
text(0, 3, expression(paste("Ho:", mu, "=5")), cex = 2)
text(0, -3, expression(paste("Ha:", mu, "<5")), cex = 2)


```

*** =sct
```{r}
msg_bad <- "That is not correct. Select the option that tests for a one-sided 'greater than' hypothesis and confidence level of 0.90"
msg_success <- "Exactly!"
test_mc(correct = 3, feedback_msgs = c(msg_bad, msg_bad, msg_success, msg_bad))

```


--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:45534c5588
## Check for Understanding 3

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




