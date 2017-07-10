---
title       : Lab 2
description : Using R to Explore Data Sets

--- type:NormalExercise lang:r xp:100 skills:1 key:f8b383874f
## Getting Started with Data

In this exercise, you will learn how to identify fundamental attributes of a data set.

One of R's built-in data sets is called `mtcars`. This data set is already in your workspace so if you type  `mtcars` into your R console, the entire data will come up in the output.

Sometimes the data can be very long so instead of viewing the entire thing, we can type:

- `head(dataset)` to get the first 6 entries or
- `tail(dataset)` to get the last 6 entries. 

If we want to know the variable (column) names in the data set, we can type `names(dataset)` into the console.

If we want to know the dimensions of a dataset (ie. how many variables and subjects) use the `dim(dataset)` function.

*** =instructions
- Use the `head()` function to get the first 6 entries of the mtcars data set
- Use `tail()` to get the last 6 entries.
- Find the variable names by using the `names()` function.
- Use `dim()` to find the dimensions of mtcars
- Click the 'Submit Answer' Button and take a look at the R output in the console.


*** =hint
The data set is named `mtcars` so substitute `mtcars` for `(dataset)`.

*** =pre_exercise_code
```{r}
mtcars
```

*** =sample_code
```{r}
#Use appropriate function to find first 6 entries of mtcars

#Use appropriate function to find last 6 entries of mtcars

#Use appropriate function to find the variables of mtcars

#Use appropriate function to find the dimension of mtcars
```

*** =solution
```{r}
#Use appropriate function to find first 6 entries of mtcars
head(mtcars)

#Use appropriate function to find last 6 entries of mtcars
tail(mtcars)

#Use appropriate function to find the variables of mtcars
names(mtcars)

#Use appropriate function to find the dimension of mtcars
dim(mtcars)
```

*** =sct
```{r}

test_function("head", args = "x")
success_msg("Nice job!")

test_function("tail", args = "x")
success_msg("Good work!")

test_function("names", args = "x")
success_msg("Good work!")

test_function("dim", args = "x")
success_msg("Good work!")
```




--- type:NormalExercise lang:r xp:100 skills:1 key:795745ad44
## Accessing Specific Variables  using $

In this exercise you will be learning how to access specific variables within a data set by using the format `dataset$variable`.

From the previous exercise, we saw that `mtcars` has a *miles per gallon* variable named `mpg`. If we want to look at this variable by itself, we can type `mtcars$mgp` into the R console; this will return a list of *miles per gallon* entries. 


*** =instructions
- The mtcars data set also has the variable *weight* named `wt`. Use `$` to access the `wt` variable from the mtcars data set.
*** =hint

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# Access wt from mtcars like we did for the mpg variable
```

*** =solution
```{r}
# Access wt from mtcars like we did for the mpg variable
mtcars$wt
```

*** =sct
```{r}
test_student_typed("mtcars$wt")
```

--- type:NormalExercise lang:r xp:100 skills:1 key:15bd840872
## Working with Variables **this needs work

We can also use arithetic operators on variables. 

For example, if I want to add two variables together, i would type `dataset$var1 + dataset$var2`. 

If I want to save this sum as a new variable, I would assign it to a name `dataset$newvar <- dataset$var1 + dataset$var2`.

In this exercise, we will be creating a new variable *density of car* named `density`. 

The mtcars data set is alrady in your work space. The variables you will need to access to create a *density* variable are *displacement* named `disp` and *weight* named `wt`.

For simplicity, we will let:

*density = weight/displacement*

*** =instructions
- Use the formula `dataset$density <- dataset$var1 / dataset$var2` to create a density variable.
- Use the `names()` function on `mtcars` to make sure that `density` was added to the variables.
*** =hint
substitute `mtcars` for dataset
*** =pre_exercise_code
```{r}
mtcars
```

*** =sample_code
```{r}
# Create *density* variable for mtcars
mtcars$density <- 

# Use names() to check if *density* was added
```

*** =solution
```{r}
# Create *density* variable for mtcars
mtcars$density <- mtcars$wt / mtcars$disp

# Use names() to check if *density* was added
names(mtcars)
```

*** =sct
```{r}
test_object("mtcars$density")

test_student_typed("names(mtcars)")
```





--- type:NormalExercise lang:r xp:100 skills:1 key:938ccd0b92
## Creating Logical Data

Recall in Lab 1 when we reviewed the different types of data.

*Logical* data only takes on two values (TRUE or FALSE) where `TRUE` has the value of 1 and `FALSE` has the value of 0.

We can create *logical* data with comparisons like greater than `>`, less than `<`, and inequallity `!=`

A logical expression using the *greater than* symbol should follow the format:

dataset$var1 > dataset$var2

This command will return a list of `TRUE` and `FALSE` values.
*** =instructions
- Find which cars in `mtcars` have greater `drat` than `wt`
- Use the sum() function to evaluate the total number of `TRUE` results
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
--- type:NormalExercise lang:r xp:100 skills:1 key:f759511088
## Using the summary() function

In this exercise, you will learn how to use the R built-in function `summary()` to obtain statistics of your data set. 

`summary(dataset)`: gives a few summary statistics of all variables in dataset


`summary(dataset$variable)`: gives a few summary statistics of a specific variable in dataset

The dataset we've been working with `mtcars` is already in your workspace.

*** =instructions
- Use the `summary()` function on the entire `mtcars` dataset.

*** =hint
substitute `mtcars` for dataset

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# Use summary() on mtcars to get summary statistics of the entire mtcars dataset
```

*** =solution
```{r}
# Use summary() on mtcars to get summary statistics of the entire mtcars dataset
summary(mtcars)

```

*** =sct
```{r}



```
--- type:NormalExercise lang:r xp:100 skills:1 key:59b987e2d7
## Using the sum() function

Another useful built-in function that R has is the `sum()` function. 

The `sum()` function adds what you put into the parenthesis.

For example, if I wanted to find the total *weight* of the mtcars, I would type `sum(mtcars$wt)`.

*** =instructions
- the dataset `mtcars` contains the variable `gear` which represents the number of forward gears. Use the `sum()` function to find the total number of gears.
*** =hint

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# Find total number of gears using sum() 
```

*** =solution
```{r}
# Find total number of gears using sum() 
sum(mtcars$gear)
```

*** =sct
```{r}
test_function("sum", args = "x")
```

--- type:NormalExercise lang:r xp:100 skills:1 key:6bc90b9c68
## Graphing Data: the Basics

Numeric summaries like the mean and standard deviation are helpful when trying to understand a dataset but a visual display can provide more insight. 

To create a basic plot in R, use the `plot()` function in the format:

`plot(x = dataset$var1 , y = dataset$var2)`

For this exercise, we are going to visualize the relationship between two variables in `mtcars`:

x = *weight* of car (wt) 

y = *miles per gallon* (mpg)



*** =instructions
- Use the `plot()` function to create a scatterplot of `wt` by `mpg`.
- After clicking 'Submit Answer', look at the plot in the output. Is there any pattern?


*** =hint

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
#type plot(x = dataset$var1 , y = dataset$var2) with x = mtcars$wt and y = mtcars$mpg
```

*** =solution
```{r}
# type plot(x = dataset$var1 , y = dataset$var2) with x = mtcars$wt and y = mtcars$mpg
plot(x = mtcars$wt, y = mtcars$mpg)
```

*** =sct
```{r}
test_function("plot", args = c("x", "y"))
success_msg("Good work! From the plot we can see that as weight increases, mpg decreases. This makes sense because bigger cars usually have less miles to the gallon.")



```


--- type:NormalExercise lang:r xp:100 skills:1 key:d0401021d4
## Adding axis labels to graphs 

In this exercise, you will learn how to clean up a graph by adding axis labels and a title.

Some arguements to specify in the `plot()` function:

- `xlab = "x"` : labels the x-axis "x"
- `ylab = "y"` : labels the y-axis "y"
- `main = "title"` : gives a title to the entire plot "title"

To add labels to a plot use the format:

`plot(x = dataset$var1 , y = dataset$var2, xlab = "x", ylab = "y", main = "title")`

Right now the plot of `mtcars$wt` vs. `mtcars$mpg` has ugly axis names. In this exercise, we will change the axis names so the plot looks less messy.

*** =instructions
- Create the plot from the last exercise `plot(x = mtcars$wt, y = mtcars$mpg)` but this time add axis labels. 

- The new x-axis label should be `"Weight"`, y-axis label should be `"Miles Per Gallon"` and the title should be `"Mtcars: Weight by MPG"`.

*** =hint
Make sure to wrap the labels in "" because they are words.
*** =pre_exercise_code
```{r}
mtcars
plot(x = mtcars$wt, y = mtcars$mpg)
```

*** =sample_code
```{r}
# Use plot(x = dataset$var1 , y = dataset$var2, xlab = "x", ylab = "y", main = "title") with specified labels
```

*** =solution
```{r}
# Use plot(x = dataset$var1 , y = dataset$var2, xlab = "x", ylab = "y", main = "title") with specified labels

plot(x = mtcars$wt , y = mtcars$mpg, xlab = "Weight", ylab = "Miles Per Gallon", main = "Mtcars: Weight by PMG")
```

*** =sct
```{r}
test_function("plot", args = c("x", "y", "xlab", "ylab", "main"))
```
