---
title       : Lab 6
description : Inference for Quantitative Data


--- type:NormalExercise lang:r xp:100 skills:1 key:fe4a8241d4
## Two Sample t-test


The two-sample t-test is used when we want to analyze a quantitative response variable in two groups.

To perform a 2 sample t-test, we'll be using a dataset called `schooldays` which contains data on Australian children involved in a sociological study about factors that effect school attendence. 

- there are 5 variables in this data set: `race`, `sex`, `school`, `learner` and `absent`.
- there are 154 subjects 
- `schooldays` is already in your workspace

Suppose we are interested in whether the students' number of absent days is dependent on their race. 

We can begin by exploring the relationship between `absent` and `race`.

- `race` is a categorical variable with 2 levels (aboriginal and non-aboriginal)
- `absent` is a quantitative variable measuring the number of days absent from school
*** =instructions
- Use the `boxplot()` function to compare the groups.
- Click the 'Submit Answer' button and look at the R output. Do you think this difference is statistically significant?

*** =hint
- To make a boxplot, use the format: `boxplot(dataset$quant_var ~ dataset$categ_var)`.

*** =pre_exercise_code
```{r}

library(HSAUR)
```

*** =sample_code
```{r}

# Create a boxplot of #absent days by race

```

*** =solution
```{r}

# Create a boxplot of #absent days by race
boxplot(schooldays$absent ~ schooldays$race)
```

*** =sct
```{r}

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

*The normality assumption is met if a histogram of the variable looks approximately symmetric and bell-shaped OR if the sample sizes are larger than 30.*



*** =instructions
- Type `library(mosaic)` to load the *mosaic* package into your workspace.
- Use the `favstats()` function to examine the distribution of `absent` by `race` and take note of the sample sizes.
- Use the `hist()` function to make sure `absent` follows the *normality* assumption.
- Click the 'Submit Answer' button and look at the R output. Does this distribution look normal to you?


*** =hint
For the second instruction, use the format: `favstats(dataset$quant_var ~ dataset$categ_var)`.

To create a histogram use the format: `hist(dataset$variable)`
*** =pre_exercise_code
```{r}
library(HSAUR)
library(mosaic)
```

*** =sample_code
```{r}
# Load the mosaic package 

# Examine the distribution of # absent days by race


# Create a histogram of number of absent days


```

*** =solution
```{r}
# Load the mosaic package 
library(mosaic)

# Examine the distribution of # absent days by race
favstats(schooldays$absent ~ schooldays$race)


# Create a histogram of number of absent days
hist(schooldays$absent)


```

*** =sct
```{r}

test_student_typed("favstats(schooldays$absent ~ schooldays$race)", not_typed_msg = "Make sure you follow the format: favstats(dataset$quant_var ~ dataset$categ_var) with the correct data set (schooldays), quant_var (absent) and categ_var (race)")

test_function("hist", args = "x", incorrect_msg = "Make sure you follow the format hist(dataset$variable) with the 'schooldays' dataset and 'absent' variable")

success_msg("Does this data follow the assumptions? Take a look at the R output because you will answer this question in the next exercise.")

```




--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:5a24579348
## Quick Check: t-test assumptions

Does the `absent` days variable from `schooldays` follow the normality assumption?

*** =instructions
- No, because the histogram is right-skewed and the sample sizes for each group are too small.
- Yes, the histogram is very right-skewed but the sample sizes are over 30. 
- No, because the sample sizes for each group are too small.
- Yes, the histogram looks approximately normal even though the sample sizes are small.
*** =hint

*** =pre_exercise_code
```{r}

```

*** =sct
```{r}
msg_bad <- "That is not correct. Go back to the last exercise and look at the histogram and sample sizes shown in the favstats() command"
msg_success <- "Exactly!"
test_mc(correct = 2, feedback_msgs = c(msg_bad, msg_success, msg_bad, msg_bad))

```
--- type:NormalExercise lang:r xp:100 skills:1 key:0bbf6fec44
## 2 sample t-test with t.test()

We can use the same `t.test()` function from last week to perform a 2 sample t-test.

To do this, use the format:

`t.test(dataset$quant_var ~ dataset$categ_var, var.equal = FALSE)`

In this exercise, you will test the hypothesis in the *Plots* panel and create a 95% confidence interval around the true average difference in absent days.

*** =instructions
- Perform use the `t.test()` function to test if the student's number of `absent` days is dependent on their `race`.
- Click 'Submit Answer' and look at the R output.

*** =hint

*** =pre_exercise_code
```{r}
library(HSAUR)
plot(-6:6, -6:6, type = "n", xlab="", ylab="", xaxt = 'n', yaxt = 'n', frame=F)
text(0, 3, expression(H[o]: mu[abor] == mu[not_abor]), cex = 3)
text(0, -3, expression(H[a]: mu[abor] != mu[not_abor]), cex = 3)
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



--- type:NormalExercise lang:r xp:100 skills:1 key:de76ba4b81
## Paired t-test

Suppose we want test whether there is a mean difference between 2 *dependent* sets of observations.

This is a paired t-test where each subject or unit is measured twice, resulting in 2 dependent measurements.

To perform a paired t-test, we'll be using a dataset called `anorexia` which contains weight change data on yound female anorexic patients. 

- there are 3 variables in this data set: `Treat`, `Prewt`, and `Postwt`.
- there are 72 subjects 
- `anorexia` is already in your workspace

The pre-weight and post-weight of patients are not independent (because it is measuring the same person) so we have to conduct a **paired** t-test.

We want to test whether the patients weights improved between their previous weight `Prewt` and post weight `Postwt`, regardless of their treatment group.

First we need to create a new variable `diffwt` that measures `Postwt - Prewt`.

*Note: Postwt and Prewt are measured in pounds*
*** =instructions
- Copy and paste this code to create `diffwt`: `anorexia$diffwt <- anorexia$Postwt - anorexia$Prewt`.

*** =hint

*** =pre_exercise_code
```{r}
library(MASS)
```

*** =sample_code
```{r}

# copy and paste code from instruction to create diffwt


```

*** =solution
```{r}

# copy and paste code from instruction to create diffwt
anorexia$diffwt <- anorexia$Postwt - anorexia$Prewt

```

*** =sct
```{r}

```
--- type:NormalExercise lang:r xp:100 skills:1 key:34994f646a
## Assumptions for Paired t-test
 
 
Before we conduct the paired t-test, we need to make sure our data follows these assumptions:

* independent observations
* difference in weights are normally distributed (or n>30)
 
The independence assumption is met because the *patients* are independent of one another.

In this exercise, you will be checking the normality assumption for the the `diffwt` variable in the `anorexia` data set.


*Remember, the normality assumption is met if a histogram of the variable looks approximately symmetric and bell-shaped OR if the sample sizes are larger than 30*


*** =instructions
- Type `library(mosaic)` to load the *mosaic* package into your workspace.
- Use `favstats()` to explore your new variable `diffwt`.
- Use the `hist()` function to check if `diffwt` is normally distributed.
- Click the 'Submit Answer' button and check the output. Are the assumptions met?
*** =hint
To create a histogram use the format: `hist(dataset$variable)`

Remember we are using the data set called `anorexia`.
*** =pre_exercise_code
```{r}
library(mosaic)
library(MASS)
anorexia$diffwt <- anorexia$Postwt - anorexia$Prewt

```

*** =sample_code
```{r}
# load the mosaic package 

# explore diffwt with the favstats() function

# Create a histogram of diffwt


```

*** =solution
```{r}
# load the mosaic package 
library(mosaic)

# explore diffwt with the favstats() function
favstats(anorexia$diffwt)

# Create a histogram of diffwt
hist(anorexia$diffwt)


```

*** =sct
```{r}

test_function("favstats", args = "x", incorrect_msg = "Make sure you follow the format favstats(dataset$variable) with the anorexia dataset and 'diffwt' variable")


test_function("hist", args = "x", incorrect_msg = "Make sure you create a histogram of the diffwt variable from the anorexia data set.")
```



--- type:NormalExercise lang:r xp:100 skills:1 key:a852975de3
## Paired tests using t.test()

We can also use the `t.test()` function to perform a paired sample t-test, but the format is a little diffferent.

Our hypothesis (in the *Plots* panel) it to test whether there is a significant difference between the weights.

To conduct a paired t-test, use the format:

`t.test(dataset$variable, mu = 0)`




*** =instructions
- Perform a paired t-test to test whether the mean difference in weight `diffwt` (Post weight - Pre weight) is equal to zero. 
- Click 'Submit Answer' and look at the R output. Is the difference between patients post weight and pre weight significant?

*** =hint
Follow the format in the lesson with `anorexia` as the dataset and `diffwt` as the variable.
*** =pre_exercise_code
```{r}
library(MASS)
plot(-6:6, -6:6, type = "n", xlab="", ylab="", xaxt = 'n', yaxt = 'n', frame=F)
text(0, 4, expression(H[o]: mu[d] == 0), cex = 2)
text(0, 1, expression(H[a]: mu[d] != 0), cex = 2)
text(0, -4, expression(mu[d] == mu[Post] - mu[pre]), cex = 2)
anorexia$diffwt <- anorexia$Postwt - anorexia$Prewt

```

*** =sample_code
```{r}
# use t.test() to conduct a paired t-test


```

*** =solution
```{r}
# use t.test() to conduct a paired t-test
t.test(anorexia$diffwt, mu = 0)


```

*** =sct
```{r}
test_function("t.test", args = c("x", "mu"), incorrect_msg = "Did you specify the null hypothesis as mu = 0?")

success_msg("Good job! Look at the R output for the t-test and take note of the p-value and 95% confidence interval.")
```




--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:9d5c6fc887
## Quick Check 1

The paired t-test from the last exercise gave us a p-value of 0.004 and a 95% confidence interval of (0.8878354 4.6399424).

At the alpha = 0.05 significance level, how would we conclude this test?

*** =instructions
- We would reject the null hypothesis that the average difference in weight between post weight and preweight is equal to zero.
- We would fail to reject the null hypothesis that the average difference in weight between post weight and preweight is equal to zero.
*** =hint

*** =pre_exercise_code
```{r}

```

*** =sct
```{r}
msg_bad <- "That is not correct. The p-value is less than alpha = 0.05 AND the confidence interval does not contain 0 so we would reject the null"
msg_success <- "Exactly!"
test_mc(correct = 1, feedback_msgs = c(msg_success, msg_bad))

```
--- type:NormalExercise lang:r xp:100 skills:1 key:5e7f284cfc
## ANOVA

We use ANOVA or Analysis of Variance when we want to compare a quantitative response variable in **more than** 2 groups.

The `anorexia` data set we've been working with has a categorical variable named `Treat` with 3 levels:

- `Cont` (control group, aka. no treatment)
- `CBT` (Cognitive Behavioural treatment)
- `FT` (Family Treatment)

Suppose we want to determine if the average patients post weights `Postwt` differs among the three categories of treatment `Treat`.

We can begin by exploring the relationship between treatment and post weights.

Note: The `Postwt` variable is measured in *pounds* and the higher the weight, the healthier the patient.
*** =instructions
- Use the `boxplot()` function to compare patients post weights `Postwt` by their treatment `Treat`.
- Click the 'Submit Answer' button and look at the R output. Do you think this difference is statistically significant?

*** =hint
- To make a boxplot, use the format: `boxplot(dataset$quant_var ~ dataset$categ_var)`.

*** =pre_exercise_code
```{r}
library(MASS)
```

*** =sample_code
```{r}

# Create boxplot to compare the groups


```

*** =solution
```{r}

# Create a boxplot to compare the groups
boxplot(anorexia$Postwt ~ anorexia$Treat)

```

*** =sct
```{r}

test_student_typed("boxplot(anorexia$Postwt ~ anorexia$Treat)", not_typed_msg = "Make sure you follow the format: boxplot(dataset$quant_var ~ dataset$categ_var) with the correct data set (anorexia), quant_var (Postwt) and categ_var (Treat)")

success_msg("Good work! It looks like the post-treatment weights were much higher in the family treatment (FT) group. Let's see if it is significant!")

```



--- type:NormalExercise lang:r xp:100 skills:1 key:8a95e5e62d
## Assumptions of ANOVA

Before testing a hypothesis with a 2 sample t-test, we need to make sure that our data meets these 2 assumptions:

* the observations are independent
* the quantitative variable is normally distributed (or sample sizes in each group are greater than 30)


The data set `anorexia` is from a random sample so the observations can be treated as independent.

In this exercise, you will be checking the normality assumption for the `Postwt` variable in `anorexia`.

*The normality assumption is met if a histogram of the variable looks approximately symmetric and bell-shaped OR if the sample size in each group is larger than 30*



*** =instructions
- Type `library(mosaic)` to load the *mosaic* package into your workspace.
- Use the `favstats()` function to examine the distribution of `Postwt` by `Treat` in the `anorexia` data set.
- Use the `hist()` function to check if `Postwt` is normally distributed.
- Click the 'Submit Answer' button and check the output. Are the assumptions met?


*** =hint
- For the second instruction, use the format: `favstats(dataset$quant_var ~ dataset$categ_var)`
- To create a histogram, use the format: `hist(dataset$variable)`.

*** =pre_exercise_code
```{r}
library(MASS)
library(mosaic)
```

*** =sample_code
```{r}
# load the mosaic package 

# explore relationship between treatment and post weights with favstats()

# Create a histogram of post-treatment weights

```

*** =solution
```{r}
# load the mosaic package 
library(mosaic)

# explore relationship between treatment and post weights with favstats()
favstats(anorexia$Postwt ~ anorexia$Treat)

# Create a histogram of post-treatment weights
hist(anorexia$Postwt)
```

*** =sct
```{r}
test_student_typed("favstats(anorexia$Postwt ~ anorexia$Treat)", not_typed_msg = "Make sure you follow the format: favstats(dataset$quant_var ~ dataset$categ_var) with the correct data set (anorexia), quant_var (Postwt) and categ_var (Treat)")

test_function("hist", args = "x", incorrect_msg = "Make sure you follow the format hist(dataset$variable) with the 'anorexia' dataset and 'Postwt' variable")

success_msg("We can see from the histogram that the post-treatment weights are a little skewed and the sample sizes in each group is less than 30 but for the purposes of this demonstration, we'll conclude that the assumptions are met.")
```





--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:5066cc4f99
## Quick Check: ANOVA

ANOVA is appropriate when we want to...

*** =instructions

- compare two population means
- test a single population mean
- examine a population mean of paired measurements
- compare more than two population means
*** =hint

*** =pre_exercise_code
```{r}

```



*** =sct
```{r}
msg_bad <- "That is not correct."
msg_success <- "Exactly!"
test_mc(correct = 4, feedback_msgs = c(msg_bad, msg_bad, msg_bad, msg_success))


```


--- type:NormalExercise lang:r xp:100 skills:1 key:9048bc1deb
## Using aov() function to test multiple means

To test if average post-treatment weights `Postwt` differs among the treatment categories, we use the `aov()` function.

Similar structure to the two sample t-test, we list the quantitative variable first, followed by the categorical. We're going to save these in an object so that we can get a summary of the results.

To do this, follow the format: 

`anova.results <- aov(dataset$quant_var ~ dataset$categ_var)`

`summary(anova.results)`

For this exercise, 
*** =instructions
- Use the format in the lesson to test if there is a difference in mean `Postwt` among the three `Treat` categories, name these results `anova.results`.
- Use the `summary()` function to examine `anova.results`.
- Click 'Submit Answer' and look ANOVA results.

*** =hint
- Follow the lesson format with correct dataset and variables.
*** =pre_exercise_code
```{r}
library(MASS)
```

*** =sample_code
```{r}
# Use aov() and summary() to carry out an ANOVA


```

*** =solution
```{r}
# Use aov() and summary() to carry out an ANOVA
anova.results <- aov(anorexia$Postwt ~ anorexia$Treat)
summary(anova.results)
```

*** =sct
```{r}
success_msg("Great! Now look at the p-value from this test. What is your conclusion?")
```









--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:dbcb0c5a29
## Quick Check 2

The results from the ANOVA have a p-value = 0.0044. At the alpha = 0.05 level of significance, what is our conclusion?

*** =instructions
- Reject the null and conclude all of the population means are different.
- Reject the null and conclude that at least one population mean differs from the others.
- Fail to reject the null and conclude all of the population means are different.
- Fail to reject the null and conclude that at least one population mean differs from the others.

*** =hint
Remember that our null hypothesis is that all of the population means are the same.
*** =pre_exercise_code
```{r}

```

*** =sct
```{r}
msg_bad <- "That is not correct. The p-value is less than alpha = 0.05 so we would reject the null BUT that only tells us that at least one population mean differs from the others."
msg_success <- "Exactly!"
test_mc(correct = 2, feedback_msgs = c(msg_bad, msg_success, msg_bad, msg_bad))

```


--- type:NormalExercise lang:r xp:100 skills:1 key:ccc0750e37
## Tukey's Pairwise Comparisons

The last exercise only tells us that *at least one* population mean differs from the others but we want to know exactly **which** pairs of means differ! 

To do this we can use use the `TukeyHSD()` function in the format:

`TukeyHSD(anova.results)`

`plot(TukeyHSD(anova.results))`

 
Note: `anova.results` is already in your workspace

*** =instructions
- Re-type the code in the lesson to see which population means are significantly different.
*** =hint

*** =pre_exercise_code
```{r}
library(MASS)
anova.results <- aov(anorexia$Postwt ~ anorexia$Treat)
```

*** =sample_code
```{r}

```

*** =solution
```{r}
TukeyHSD(anova.results)

plot(TukeyHSD(anova.results))
```

*** =sct
```{r}

```

--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:11685d799c
## Quick Check 3

Examining a histogram of a quantitative variable helps us to determine if a condition is satisfied for valid statistical inference by...

*** =instructions
- allowing us to evaluate if measurements are paired
- allowing us to evaluate if observations are independent
- allowing us to determine if the data follow an approximately normal distribution
- allowing us to determine if the sample size is large enough
*** =hint

*** =pre_exercise_code
```{r}

```

*** =sct
```{r}
msg_bad <- "That is not correct."
msg_success <- "Exactly!"
test_mc(correct = 3, feedback_msgs = c(msg_bad, msg_bad, msg_success, msg_bad))

```
