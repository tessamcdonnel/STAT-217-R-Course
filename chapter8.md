---
title       : Lab 7
description : Inference for Categorical Data



--- type:NormalExercise lang:r xp:100 skills:1 key:616c48f5cf
## One sample z-test

In this course, we will use the one sample *z*-test to test whether a population **proportion** differs from a specific value.

To perform a one sample z-test, we'll be using a data set called `nc` which contains data on the North Carolina birth records from 2004. 

- there are 13 variables in this data set but we will use 
- there are 1,000 subjects 
- `nc` is already in your workspace

This data set contains a categorical variable called `lowbirthweight` with 2 levels:

- `low` (low birthweight)
- `not low` (not low birthweight)

Let's begin by exploring the `lowbirthweight` variable in the `nc` data set.

*** =instructions
- Use the `table()` function to get a summary of the `lowbirthweight` variable.
- Copy and paste the code below to add row/column totals to the table:

`addmargins(table(nc$lowbirthweight))`

- Click the 'Submit Answer' button and then use R (or a hand calculator) to find the proportion of births that were classified as low birthweights.

*** =hint
Remember, to make a table use the format: `table(dataset$variable)`.

R doesn't recognize a comma as part of a number so make sure you type 111/1000 and NOT 111/1,000
*** =pre_exercise_code
```{r}
download.file("http://www.openintro.org/stat/data/nc.RData", destfile = "nc.RData")
load("nc.RData")

```

*** =sample_code
```{r}
# Type table(dataset$categ_var) with specified data set and variable to get a table summary


# Copy and paste addmargins(table(nc$lowbirthweight)) to get margin totals


# Click the 'Submit Answer' button and then use R as a calculator to find the proportion of births that were classified as low birthweights.


```

*** =solution
```{r}
# Type table(dataset$categ_var) with specified data set and variable to get a table summary

table(nc$lowbirthweight)

# Copy and paste addmargins(table(nc$lowbirthweight)) to get margin totals

addmargins(table(nc$lowbirthweight))

# Click the 'Submit Answer' button and then use R as a calculator to find the proportion of births that were classified as low birthweights.

111/1000

```

*** =sct
```{r}

test_function("table", args = "...", incorrect_msg = "Follow the format in the lesson with correct dataset (nc) and categ_var (lowbirthweight).")

test_student_typed("addmargins(table(nc$lowbirthweight))", not_typed_msg = "Don't forget to copy and paste the code from the 2nd instruction!")


test_output_contains("0.111", incorrect_msg = "R doesn't recognize a comma as part of a number so make sure you type 111/1000 and NOT 111/1,000")

success_msg("Note that the 'low' birthweight column is on the left. Use this table to find the proportion of low birthweights by dividing the number of low birthweights by the sum.")


```


--- type:NormalExercise lang:r xp:100 skills:1 key:5d43584cb1
## Using the prop.test() function

We can see that the proportion of babies with low birthweights from this data set is around 11%.

However, a previous study estimated the low birthweight rate to be 7%. In other words, 7% of all births in North Carolina are under weight. 

If we want to test whether the low birthrate of our population differs from 7%, we can use the `prop.test()` function with the format:

`prop.test(#yes, #total, p = null_hyp, correct = FALSE)`

* *#yes* = number of births classified as low birthweight
* *#total* = total number of births in the sample
* *p* = the proportion from our null hypothesis


In this exercise you will use the `prop.test()` function to perform a z-test to determine if the population proportion of `lowbirthweight` differs from 0.07. 

Remember, there were 111 babies with low birthweight and 1000 total births in the sample.

*** =instructions
Use the `prop.test()` function to perform a z-test to determine if the population proportion of `lowbirthweight` from the `nc` data set differs from 0.07 (or 7%).


*** =hint

Remember to set p = sample proportion (in this case `p = 0.07`).

*** =pre_exercise_code
```{r}
download.file("http://www.openintro.org/stat/data/nc.RData", destfile = "nc.RData")
load("nc.RData")

```

*** =sample_code
```{r}
# use the prop.test() function with the format from the lesson to test if the the population proportion differs from 0.07.



```

*** =solution
```{r}
# use the prop.test() function with the format from the lesson to test if the the population proportion differs from 0.07.
prop.test(111, 1000, p = 0.07, correct = FALSE)


```

*** =sct
```{r}
test_function("prop.test", args = c("x", "n", "p", "correct"))
success_msg("Great! Now look at the R output. The p-value is almost zero so we can reject the null hypothesis and conclude the proportion of low birthweights is significantly different than 0.07")


```

--- type:NormalExercise lang:r xp:100 skills:1 key:b187ce8175
## Two Sample z-test

The `nc` data set also contains a categorical variable called `habit` with 2 levels:

- the mother is a smoker (`smoker`)
- the mother is not a smoker (`nonsmoker`)

Suppose we want to test whether low birthweight rates vary depending on the mothers smoking habits.

Let's begin by obtaining a table of `lowbirthweight` by `habit`.

To create this contingency table, use the `table()` function with the format:

`table(dataset$var1, dataset$var2)`


*** =instructions
- Create a table of `lowbirthweight` and `habit` from the `nc` data set where:

* var1 = `lowbirthweight`
* var2 = `habit`

- Copy and paste the code below to add row/column totals to the table:

`addmargins(table(nc$lowbirthweight, nc$habit))`

- Click the 'Submit Answer' button and then use R (or a hand calculator) to find the proportion of low birthweight births in the `smoker` category **AND** the proportion of low birthweights in the `nonsmoker` category.


*** =hint

*** =pre_exercise_code
```{r}
download.file("http://www.openintro.org/stat/data/nc.RData", destfile = "nc.RData")
load("nc.RData")

```

*** =sample_code
```{r}
# Create a table of low birthweights and smoking habits using the table() function


# Copy and paste the code from the second instruction




# Use table to find low birthweight proportions of smoking mothers and nonsmoking mothers


```

*** =solution
```{r}
# Create a table of low birthweights and smoking habits using the table() function
table(nc$lowbirthweight, nc$habit)


# Copy and paste the code from the second instruction
addmargins(table(nc$lowbirthweight, nc$habit))


# Use table to find low birthweight proportions of smoking mothers and nonsmoking mothers



```

*** =sct
```{r}

```
