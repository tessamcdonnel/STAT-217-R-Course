---
title       : Lab 5
description : One-sample t-test





--- type:NormalExercise lang:r xp:100 skills:1 key:9c0a9256c3
## Inference on a single Mean

Before testing a hypothesis with a t-test, we need to make sure that a t-test is applicable.


*get a good data set with an exciting quantitative variable*
Use cdc$weight if worst comes to worst.
Examine distribution of that variable:
- mean
- sd
- histogram

Talk about assumptions to trust a t-test and decide if they are satisfied for this example (normality decided by histogram)
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
test_function("mean", args = "x")
test_function("sd", args = "x")
test_function("hist", args = "x")
```


--- type:NormalExercise lang:r xp:100 skills:1 key:52ad764c46
## Using the t.test() function

Explain how to use the t.test() function and what arguments can be passed through it

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





--- type:NormalExercise lang:r xp:100 skills:1 key:2a8c8123f8
## Factors that effect the test conclusion

- closeness of sample mean and alternative hypothesis
- one-sided, two-sided
- alpha

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



--- type:NormalExercise lang:r xp:100 skills:1 key:8012eaa048
## Finding probabilities with pt()


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
--- type:NormalExercise lang:r xp:100 skills:1 key:f3b03a4bf0
## Finding Critical Values with qt()


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




--- type:NormalExercise lang:r xp:100 skills:1 key:2575d7ec93
## Finding Probabilities with the pt() function


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










--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:f14e01c77b
## Quiz: 
#### t.test() default settings

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
test_mc(correct = 2, feedback_msgs = c(msg_bad, msg_bad, msg_bad, msg_success))

```

--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:45534c5588
## Quiz Cont...

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
test_mc(correct = 2, feedback_msgs = c(msg_bad, msg_bad, msg_bad, msg_success))

```
