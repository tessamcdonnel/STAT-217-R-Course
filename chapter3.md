---
title       : Lab 3
description : Summarizing and Visualizing Data

--- type:NormalExercise lang:r xp:100 skills:1 key:fe98ce0ad3
## Using the srt() function to reveal Variable Types

If we want to know the *types of variables* in our data set, we can type the command `str(dataset)` into the R Console.

This will return all of the variable names as well as their type (i.e. numeric, factor, integer). 

*Categorical* variables will be will be `factor` variable types.

*Quantitative* variables will be `numeric` and `integer` variable types.

For this lab, we will use a dataset called `cdc` which contains data on the health of people in the United States.

- there are 9 variables in the data set
- there are 20,000 subjects
- this data set is already in your workspace so if you type `cdc` into your console, the data will come up in the output

*** =instructions

- Use the `str()` function to find the variable types of the `cdc` data set.
- Click the 'Submit Answer' Button and take a look at the R output in the console.
*** =hint
Follow the format str(dataset) with `cdc` instead of `dataset`.
*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/cdc.R")

```

*** =sample_code
```{r}
# Find the variable types of cdc


```

*** =solution
```{r}
# Find the variable types of cdc
str(cdc)


```



*** =sct
```{r}
test_function("str", args = "object", incorrect_msg = "Make sure you follow the format str(dataset) with the correct data set!")
```


--- type:NormalExercise lang:r xp:100 skills:1 key:53e494b387
## Changing Variable Types

You may have noticed from the previous exercise that the `smoke100` variable is coded as numeric, but this is incorrect.

`smoke100` only takes on two values *(1 = respondent has smoked at least 100 cigarettes in their life, 0 = otherwise)*. 

R thinks that the `smoke100` variable is 'numeric' but really it should be coded as 'factor' because it is a **categorical variable**. 

In this exercise we are going to recode the `smoke100` variable from a numeric to a factor variable type.


*** =instructions
- Copy this code to your R script: `cdc$smoke100 <- factor(cdc$smoke100, labels = c("no smoke", "yes smoke"))`
- Use the `str()` function on `cdc` 
- Click the 'Submit Answer' Button and take a look at the R output in the console. Make sure the `smoke100` variable was correctly recoded to a factor variable
*** =hint

*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/cdc.R")

```

*** =sample_code
```{r}
# Type the code from the 'Instructions' box to change the *smoke100* variable to a factor variable

# Use the str() function on cdc


```

*** =solution
```{r}
# Type the code from the 'Instructions' box to change the *smoke100* variable to a factor variable
cdc$smoke100 <- factor(cdc$smoke100, labels = c("no smoke", "yes smoke"))

# Use the str() function on cdc
str(cdc)
```

*** =sct
```{r}

test_function("str", args = "object", incorrect_msg = "Make sure you follow the format str(dataset) with the correct data set!")
```

--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:ee655438c8
## Quick Review of Variable Types

Is a `factor` coded variable an example of a *quantitative* variable or a *categorical* variable?

*** =instructions
- Quantitative
- Categorical
*** =hint

*** =pre_exercise_code
```{r}

```

*** =sct
```{r}
msg_bad <- "That's incorrect. A factor variable is a categorical variable!"
msg_success <- "Good answer!"

test_mc(correct = 2, feedback_msgs = c(msg_bad, msg_success))
```

--- type:NormalExercise lang:r xp:100 skills:1 key:b715998152
## Summarizing Quantitative Variables

In this exercise, you will practice using the `favstats()` function from the *mosaic* package in R. This function will return the `min`, `max`, `mean`, `sd` and a few other numerical summaries of a quantitative variable.

To use the `favstats()` function, use the format:
`favstats(dataset$quant_var)`


The data set we've been working with (`cdc`) is already in your workspace.


*** =instructions
- Type `library(mosaic)` to load the *mosaic* package into your workspace.
- Find summary statistics of the `weight` variable in the `cdc` data set using the `favstats()` function.
- Find summary statistics of the `height` variable in `cdc` using the `favstats()` function.
- Find summary statistics of the `age` variable in `cdc` using the `favstats()` function.

*** =hint
Follow the format in the lesson substituting `cdc` for dataset and specified variable for quant_var.

*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/cdc.R")
library(mosaic)
```

*** =sample_code
```{r}
# Load the mosaic package 


# Use the favstats() function to explore weight in the cdc data set 


# Use the favstats() function to explore height in the cdc data set 


# Use the favstats() function to explore age in the cdc data set 


```

*** =solution
```{r}
# Load the mosaic package 
library(mosaic)

# Use the favstats() function to explore weight in the cdc data set 
favstats(cdc$weight)

# Use the favstats() function to explore height in the cdc data set 
favstats(cdc$height)

# Use the favstats() function to explore age in the cdc data set 
favstats(cdc$age)


```

*** =sct
```{r}
test_function("favstats", args = "x", index = 1, incorrect_msg = "Follow the format in the lesson with correct dataset and variable!")

test_function("favstats", args = "x", index = 2, incorrect_msg = "Follow the format in the lesson with correct dataset and variable!")

test_function("favstats", args = "x", index = 3, incorrect_msg = "Follow the format in the lesson with correct dataset and variable!")


```




--- type:NormalExercise lang:r xp:100 skills:1 key:c7db7fdc55
## Summarizing categorical Variables

To summarize categorical variables, we can use the `table()` function to see the frequency of occurences at each level of the categorical variable.

To create a table, use the format:

`table(dataset$categ_var)`

*** =instructions
- summarize the `smoke100` variable in the `cdc` data set using the `table()` function.
- Click the 'Submit Answer' Button and take a look at the R output in the console.
*** =hint
Use the format from the lesson with `cdc` instead of dataset, and `smoke100` instead of categ_var.
*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/cdc.R")
cdc$smoke100 <- factor(cdc$smoke100, labels = c("no smoke", "yes smoke"))

```

*** =sample_code
```{r}
# Type table(dataset$categ_var) with specified data set and variable to get a table summary


```

*** =solution
```{r}
# Type table(dataset$categ_var) with specified data set and variable to get a table summary
table(cdc$smoke100)
```

*** =sct
```{r}
test_function("table", args = "...")

```



--- type:NormalExercise lang:r xp:100 skills:1 key:9fc43281cb
## Contingency Tables

A contingency table is used to summarize the relationship betweeen categorical variables. 

In this exercise we will create a contingency table by cross-classifying two variables using the `table()` function with the format:

`table(dataset$var1, dataset$var2)`

Note: The variable listed first (var1) will go along the rows and the variable listed second (var2) will go along the columns.

Note: The variable `genhlth` is a categorical variable indicating general health.

*** =instructions
- Create a contingency table with variables `genhlth` and `smoke100` from the `cdc` data set.
*** =hint
Use the format from the lesson with `cdc` instead of dataset, `genhlth` instead of var1, and `smoke100` instead of var2

*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/cdc.R")
cdc$smoke100 <- factor(cdc$smoke100, labels = c("no smoke", "yes smoke"))

```

*** =sample_code
```{r}
# Create contingency table with variables `genhlth` and `smoke100`


```

*** =solution
```{r}
# Create contingency table with variables `genhlth` and `smoke100`
table(cdc$genhlth, cdc$smoke100)


```

*** =sct
```{r}
test_function("table", args = "...", incorrect_msg = "Use the format from the lesson with `cdc` instead of dataset, `genhlth` instead of var1, and `smoke100` instead of var2")
```
--- type:NormalExercise lang:r xp:100 skills:1 key:9a4fea2da0
## Visualizing Quantitative Data in R
The two main visualizations of quantitative data are:

*Histogram* - represents the distribution of quantitative data

- use `hist(dataset$variable)` to create a histogram

*Boxplot* - used to visualize the variation of quantitative data

- use `boxplot(dataset$variable)` to create a boxplot

*** =instructions
- Create a histogram of the `weight` variable from the `cdc` data set using the `hist()` function.
- Click the 'Submit Answer' Button and take a look at the R output in the console.
*** =hint

*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/cdc.R")

```

*** =sample_code
```{r}
# Create Histogram of weight variable with hist() function


```

*** =solution
```{r}
# Create Histogram of weight variable with hist() function

hist(cdc$weight)
```

*** =sct
```{r}
test_function("hist", args = "x", incorrect_msg = "Follow the format: hist(dataset$variable) with specified dataset and variable.")
```


--- type:NormalExercise lang:r xp:100 skills:1 key:b65646dd8a
## Visualizing Categorical Data in R

The most common way to visualize categorical variables is by creating a *barplot*.

To do this in R, use the format:

`barplot(table(dataset$categ_var))`

*** =instructions
- Create a barplot of the categorical variable `smoke100` from the `cdc` data set.
- Click the 'Submit Answer' Button and take a look at the R output in the console.
*** =hint

*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/cdc.R")
cdc$smoke100 <- factor(cdc$smoke100, labels = c("no smoke", "yes smoke"))

```

*** =sample_code
```{r}
# Create barplot of the smoke100 variable in cdc data set



```

*** =solution
```{r}
# Create barplot of the smoke100 variable in cdc dataset

barplot(table(cdc$smoke100))
```

*** =sct
```{r}
test_student_typed("barplot(table(cdc$smoke100))", not_typed_msg = "Make sure you follow the format in the lesson with 'cdc' instead of 'dataset' and 'smoke100' instead of 'categ_var'")
```



--- type:NormalExercise lang:r xp:100 skills:1 key:c6f71ca0bd
## Visualizing Relationships between 2 Quantitative Variables

If we have two quantitative variables, we can visualize their relationship with the `plot()` function. 

The format to make a basic scatterplot is:

`plot(x = dataset$var1 , y = dataset$var2)`


For this exercise, we are going to visualize the relationship between `weight` and `height` in the `cdc` data set:

x = `weight` 

y = `height`

*** =instructions
- Use the `plot()` function to create a scatterplot of `weight` and `height`.
- After clicking 'Submit Answer', look at the plot in the output. Is there any pattern?
*** =hint

*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/cdc.R")

```

*** =sample_code
```{r}
# Use plot() to create scatterplot of weight and height


```

*** =solution
```{r}
# Use plot() to create scatterplot of weight and height

plot(x = cdc$weight, y = cdc$height)
```

*** =sct
```{r}
test_function("plot", args = c("x", "y"), incorrect_msg = "Remember to follow the format in the lesson with the specified data set and variables")

```



--- type:NormalExercise lang:r xp:100 skills:1 key:fca8885b03
## Visualizing Quantitative Variables by Groups

Sometimes we want to compare a quantitative variable across the different groups of a categorical variable. 

To do this, we can use the `boxplot()` function of the format:

`boxplot(dataset$quant_var ~ dataset$categ_var)`

This will produce side by side boxplots.

*** =instructions

Create side-by-side boxplots to compare the `weight` of respondents in the `cdc` data set by whether or not they are/were a smoker `smoke100`.



*** =hint
Use format in the lesson with `weight` = `quant_var`, `cdc` = `dataset`, `smoke100` = `categ_var`
*** =pre_exercise_code
```{r}
source("https://www.openintro.org/stat/data/cdc.R")
cdc$smoke100 <- factor(cdc$smoke100, labels = c("no smoke", "yes smoke"))


```

*** =sample_code
```{r}
# Create side-by-side boxplots with quant_var = weight and categ_var = smoke100
```

*** =solution
```{r}
# Create side-by-side boxplots with quant_var = weight and categ_var = smoke100

boxplot(cdc$weight ~ cdc$smoke100)
```

*** =sct
```{r}
test_student_typed("boxplot(cdc$weight ~ cdc$smoke100)")


```
