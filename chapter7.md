---
title       : Lab 6
description : Inference for Quantitative Data


--- type:NormalExercise lang:r xp:100 skills:1 key:79a37231a2
## Assumptions for a 2 sample t-test
#### maybe split this up into 2 slides: Intro to the data, then Assumptions

**find a data set for this!**

The two-sample t-test is used when we want to test whether the difference between groups in a categorical variable is statistically significant.

Before testing a hypothesis with a 2 sample t-test, we need to make sure that our data meets these 2 assumptions:

* the observations are independent
* the quantitative variable is normally distributed

This data is from a random sample so the observations can be treated as independent.

In this exercise, you will be checking the normality assumption for the `var` variable in `dataset`.

*The normality assumption is met if a histogram of the variable looks approximately symmetric and bell-shaped OR if the sample sizes are larger than 30*

Note: The *mosaic* package is already in your workspace.


*** =instructions
- Use the `favstats()` function to examine the distribution of `quantvar` by `categoricalvar` in the `dataset`.
- Use the `hist()` function to make sure `quantvar` follows the *normality* assumption.

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


--- type:NormalExercise lang:r xp:100 skills:1 key:0bbf6fec44
## 2 sample t-test with t.test()

We can use the same `t.test()` function from last week to perform a 2 sample t-test.

To do this, use the format:

`t.test(dataset$quant_var ~ dataset$categ_var, var.equal = FALSE)`

**Add a hypothesis in the plots panel**

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

--- type:NormalExercise lang:r xp:100 skills:1 key:34994f646a
## Assumptions for Paired t-test
 
 
- Use the `anorexia` data set from the mass package
- Explain what the difference between paired and non-paired tests
- talk about assumptions and how the data meet them
- create diff between pre and post weight

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



--- type:NormalExercise lang:r xp:100 skills:1 key:a852975de3
## Paired tests using t.test()

- introduce `paired = TRUE` argument to make it a paired t-test
- use the anorexia data
- add hypothesis in plots panel

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

--- type:NormalExercise lang:r xp:100 skills:1 key:5e7f284cfc
## Assumptions of ANOVA

- use when we want to compare more than 2 groups of a categorical variable
- Use anorexia data
- even though n < 30 we can assume the normality assumption is met

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

--- type:NormalExercise lang:r xp:100 skills:1 key:9048bc1deb
## Using aov() function to test multiple means


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
