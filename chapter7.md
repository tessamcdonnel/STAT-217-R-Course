---
title       : Lab 6
description : Inference for Quantitative Data




--- type:NormalExercise lang:r xp:100 skills:1 key:fe4a8241d4
## Two Sample t-test


The two-sample t-test is used when we want to test whether the difference between groups in a categorical variable is statistically significant.

To perform a 2 sample t-test, we'll be using a dataset called `schooldays` which contains data on Australian children involved in a sociological study about factors that effect school attendence. 

- there are 5 variables in this data set: `race`, `sex`, `school`, `learner` and `absent`.
- there are 154 subjects 
- `schooldays` is already in your workspace

Suppose we are interested if the subjects were absent a different amount of times based on their race. 

We can begin by exploring the relationship between `absent` and `race`.

- `race` is a categorical variable with 2 levels (aboriginal and non-aboriginal)
- `absent` is a quantitative variable measuring the number of days absent from school
*** =instructions
- Type `library(mosaic)` to load the *mosaic* package into your workspace.
- Use the `favstats()` function to examine the distribution of `absent` by `race` in the `schooldays`.
- Use the `boxplot()` function to compare the groups.
- Click the 'Submit Answer' button and look at the R output. Do you think this difference is statistically significant?

*** =hint
- For the second instruction, use the format: `favstats(dataset$quant_var ~ dataset$categ_var)`.
- To make a boxplot, use the format: `boxplot(dataset$quant_var ~ dataset$categ_var)`.

*** =pre_exercise_code
```{r}

library(HSAUR)
```

*** =sample_code
```{r}
# Load the mosaic package 

# Examine the distribution of # absent days by race

# Create a boxplot of #absent days by race

```

*** =solution
```{r}
# Load the mosaic package 
library(mosaic)

# Examine the distribution of # absent days by race
favstats(schooldays$absent ~ schooldays$race)

# Create a boxplot of #absent days by race
boxplot(schooldays$absent ~ schooldays$race)
```

*** =sct
```{r}
test_student_typed("favstats(schooldays$absent ~ schooldays$race)", not_typed_msg = "Make sure you follow the format: favstats(dataset$quant_var ~ dataset$categ_var) with the correct data set (schooldays), quant_var (absent) and categ_var (race)")

test_student_typed("boxplot(schooldays$absent ~ schooldays$race)", not_typed_msg = "Make sure you follow the format: boxplot(dataset$quant_var ~ dataset$categ_var) with the correct data set (schooldays), quant_var (absent) and categ_var (race)")

success_msg("Good work! It looks like Aboriginal students were absent more days. Let's see if it is significant!")

```
--- type:NormalExercise lang:r xp:100 skills:1 key:79a37231a2
## Assumptions for a 2 sample t-test


Before testing a hypothesis with a 2 sample t-test, we need to make sure that our data meets these 2 assumptions:

* the observations are independent
* the quantitative variable is normally distributed (or sample sizes are greater than 30)


The data set `schooldays` is from a random sample so the observations can be treated as independent.

In this exercise, you will be checking the normality assumption for the `absent` variable in `schooldays`.

*The normality assumption is met if a histogram of the variable looks approximately symmetric and bell-shaped OR if the sample sizes are larger than 30*



*** =instructions
- Use the `hist()` function to make sure `absent` follows the *normality* assumption.
- Click the 'Submit Answer' button and look at the R output. Does this distribution look normal to you?


*** =hint
To create a histogram use the format: `hist(dataset$variable)`
*** =pre_exercise_code
```{r}
library(HSAUR)

```

*** =sample_code
```{r}
# Create a histogram of number of absent days


```

*** =solution
```{r}
# Create a histogram of number of absent days
hist(schooldays$absent)


```

*** =sct
```{r}
test_function("hist", args = "x", incorrect_msg = "Make sure you follow the format hist(dataset$variable) with the 'schooldays' dataset and 'absent' variable")

success_msg("Uh-oh, this distribution is very right skewed. Normally we wouldn't be able to perform a t-test on such skewed data but since our sample sizes are large, we can!")
```



--- type:NormalExercise lang:r xp:100 skills:1 key:0bbf6fec44
## 2 sample t-test with t.test()

We can use the same `t.test()` function from last week to perform a 2 sample t-test.

To do this, use the format:

`t.test(dataset$quant_var ~ dataset$categ_var, var.equal = FALSE)`

**Add a hypothesis in the plots panel**

*** =instructions
- Perform a t-test to test if the student's number of `absent` days is dependent on their `race`.
- Click 'Submit Answer' and look at the R output.

*** =hint

*** =pre_exercise_code
```{r}
library(HSAUR)
plot(-6:6, -6:6, type = "n", xlab="", ylab="", xaxt = 'n', yaxt = 'n')
text(0, 3, expression(paste("Ho:", mu [yes], "=", mu [no])), cex = 3)
text(0, -3, expression(paste("Ha:", mu [yes], "><", mu [no])), cex = 3)

```

*** =sample_code
```{r}
# Test whether number of absent days is dependent on race.


```

*** =solution
```{r}
# Test whether number of absent days is dependent on race.
t.test(schooldays$absent ~ schooldays$race, var.equal = FALSE)

```

*** =sct
```{r}
test_student_typed("t.test(schooldays$absent ~ schooldays$race, var.equal = FALSE)", not_typed_msg = "Make sure you follow the format from the lesson with the correct data set (schooldays), quant_var (absent) and categ_var (race)")
```

--- type:NormalExercise lang:r xp:100 skills:1 key:34994f646a
## Assumptions for Paired t-test
 
Suppose we want test whether there is a mean difference between 2 *dependent* sets of observations.

This is a paired t-test where each subject or unit is measured twice, resulting in 2 dependent measurements.

To perform a paired t-test, we'll be using a dataset called `anorexia` which contains weight change data on yound female anorexic patients. 

- there are 3 variables in this data set: `Treat`, `Prewt`, and `Postwt`.
- there are 72 subjects 
- `anorexia` is already in your workspace

We want to test whether the patients weights improved between their previous weight `Prewt` and post weight `Postwt`, regardless of their treatment group?
 
The pre-weight and post-weight of patients are not independent (because it is measuring the same person) so we have to conduct a **paired** t-test.
 
Before we conduct the test, we need to make sure our data follows these assumptions:

* independent observations
* difference in weights are normally distributed (or n>30)
 
The independence assumption is met because the *patients* are independent of one another.

In this exercise, you will be checking the normality assumption for the the *difference in weight* in the `anorexia` data set.


*Remember, the normality assumption is met if a histogram of the variable looks approximately symmetric and bell-shaped OR if the sample sizes are larger than 30*



*** =instructions
- Type `library(mosaic)` to load the *mosaic* package into your workspace.
- Copy and paste this code to create a new variable called `diffwt` that measures: `Postwt - Prewt`: `anorexia$diffwt <- anorexia$Postwt - anorexia$Prewt`.
- Use `favstats()` to explore your new variable `diffwt`.
- Use the `hist()` function to check if `diffwt` is normally distributed.
- Click the 'Submit Answer' button and check the output. Are the assumptions met?
*** =hint

*** =pre_exercise_code
```{r}
library(MASS)
library(mosaic)
```

*** =sample_code
```{r}
# Load the mosaic package 

# Create new variable called diffwt that that measures post-weight - pre-weight

# Explore the new variable diffwt

# Create a histogram of diffwt


```

*** =solution
```{r}
# Load the mosaic package 
library(mosaic)

# Create new variable called diffwt that that measures post-weight - pre-weight
anorexia$diffwt <- anorexia$Postwt - anorexia$Prewt

# Explore the new variable diffwt with the favstats() function
favstats(anorexia$diffwt)

# Create a histogram of diffwt
hist(anorexia$diffwt)

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
