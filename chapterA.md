---
title       : Lab 1
description : Introduction to R and RStudio


--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:10124e5c35
## What is R ?


What can R be used for?

*** =instructions
- Graphing data
- Analyzing data
- Calculations
- All of the above

*** =hint
R software can be used for all of these things.

*** =pre_exercise_code
```{r}
# The pre exercise code runs code to initialize the user's workspace.
# You can use it to load packages, initialize datasets and draw a plot in the viewer

```

*** =sct
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

msg_bad <- "That is not correct"
msg_success <- "Exactly! R can do all of these things."
test_mc(correct = 4, feedback_msgs = c(msg_bad, msg_bad, msg_bad, msg_success))
```




--- type:NormalExercise lang:r xp:100 skills:1 key:8902293ef6
## How to use DataCamp

The upper right portion of your screen is the script editor: this is where you will be typing your R code to answer the questions. When you press the 'Submit Answer' button, every line of code is interpreted and executed by R and you will get a message that says whether or not your code was correct. 

Below the script is the R Console: you can use this to execute R commands and test your R code for correctness before you submit it. 

The # symbol lets you comment on your code without R processing it.

*** =instructions 
This exercise is only meant to help you get set up with DataCamp so there is no coding task.
Just click 'Submit Answer' to continue to the next exercise.
*** =hint

*** =pre_exercise_code
```{r}
# This is were you will be writing your code
```

*** =sample_code
```{r}
# This is were you will be writing your code
```

*** =solution
```{r}
# This is were you will be writing your code
```

*** =sct
```{r}

```
--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:77ff5d2cfd
## Getting Started with R


The best way to learn R programming is to actually practice typing yourself. 
So, lets start coding!

Are you excited to dive into the exhilarating world of R Programming?!

*** =instructions
- Yes
- No

*** =hint
You should be very excited!
*** =pre_exercise_code
```{r}

```


*** =sct
```{r}
msg_bad <- "Well, hopefully it will grow on you!"
msg_success <- "Good answer!"
test_mc(correct = 1, feedback_msgs = c(msg_success, msg_bad))
```

--- type:NormalExercise lang:r xp:100 skills:1 key:dbdb4a1084
## Using R as a Calculator


In this exercise, we'll see how R can be used to perform simple arithmetic tasks.

Some arithmetic operators you can use in R code include:

Addition: `+`

Subtraction: `-` 

Division: `/` 

Multiplication: `*` 

Exponentiation: `^`

For example, if I want to cube '4', I would type `4^3` into the console.


*** =instructions
- In the script, type `4^3` to calculate four to the power of three.
- Click the 'Submit Answer' Button and take a look at the R output in the console (bottom right panel).
*** =hint
- Type your code in the upper right box


*** =pre_exercise_code
```{r}


```

*** =sample_code
```{r}

# Example of Addition
5 + 10

# Example of division and subtraction
(10 - 5) / 2

# Use R as a calculator to find four to the power of three.




```


*** =solution
```{r}

# Example of Addition
5 + 10

# Example of division and subtraction
(10 - 5) / 2

# Use R as a calculator to find four to the power of three
4^3



```

*** =sct
```{r}
test_output_contains("15", incorrect_msg = "Do not remove the line of R code that calculates the sum of 5 and 10. Instead, just do the last question")


test_output_contains("2.5", incorrect_msg = "Do not remove the line of R code that calculates (10 - 5) / 2. Instead, just do the last question")

test_output_contains("64", incorrect_msg = "Make sure to add a line of R code, that calculates 4 to the power of 3. Do not start the line with a `#`, otherwise, your R code will not be executed!")

success_msg("Awesome! See how the console shows the result of the R code you submitted? Now that you're familiar with the interface, let's get down to R business!")
```



--- type:NormalExercise lang:r xp:100 skills:1 key:b19e862406
## Using the sqrt() Function

Like any other calculator, R has the ability to take the square root of non-negative numbers.

We will be calculating the square root a lot in this class so knowing this R function is really handy.

If I want to take the square root of 9, I would type `sqrt(9)` and it would return 3.

*** =instructions
- In the script, use the `sqrt()` function to find the square root of 9659.
- In the script, use the `sqrt()` function and arithmetic operators (from last exercise) to evaluate the expression in the upper right hand *plots*. This evaluates to 3.16.
*** =hint
R uses PEMDAS order of operations like you would use in any math class.

*** =pre_exercise_code
```{r}
plot(-1:1, -1:1, type = "n", xlab="", ylab="", xaxt = 'n', yaxt = 'n')
text(0, 0, expression(frac((0.6 - 0.5), sqrt(0.25/1000))), cex = 4)

```

*** =sample_code
```{r}
# Find the square root of 9659 using sqrt()

# Evaluate the expression in the plots panel 

```

*** =solution
```{r}
# Find the square root of 9659 using sqrt()
sqrt(9659)

# Evaluate the expression in the plots panel 
(0.6-0.5) / sqrt(0.25/1000)
```

*** =sct
```{r}
test_function("sqrt", args = "x")

test_output_contains("(0.6-0.5) / sqrt(0.25/1000)", incorrect_msg = "That is incorrect. Type (0.6-0.5) / sqrt(0.25/1000) to evaluate the expression in the Plots panel.")

success_msg("Good work!")
```

--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:6f441f4fb9
## Basic Data Types in R

The four basic data types we will be working with in this course are:

Numeric: numbers with decimals like `3.1` or `22.0`

Integers: natural numbers like `-9` and `4`, integers are also numeric data.

Logical: boolean values (`TRUE` or `FALSE`)

Character: texts and words ("this is character data")


Note: all character data should be wrapped in "".

If I typed `70.0 + 28.9` into the console, the value that R would return would be what type of data?

*** =instructions
- numeric
- character
- logical
- integer

*** =hint

*** =pre_exercise_code
```{r}

```

*** =sct
```{r}
msg_bad <- "That is not correct, '70.0 + 28.9' does not result in a whole number so the data type must be 'numeric'"
msg_success <- "Exactly!"
test_mc(correct = 1, feedback_msgs = c(msg_success, msg_bad, msg_bad, msg_bad))
```
--- type:NormalExercise lang:r xp:100 skills:1 key:4ea9b80fa0


## Generating Numbers **will most likely delete this

We can also use R to generate numbers and lists.

The `seq()` function generates a sequence of numbers. If I want a sequence of number 1 through 20, I can type `seq(1, 20)` into my console. Try this.

We can also use the `by = ` arguement to get a different sequence. Type `seq(1:20, by = 0.5)` and notice how the output has changed.

*** =instructions
- Use the `seq()` function to generate of list of numbers from -10 to 10, increasing by 1. Assign this vector to `x`.
- Create another sequence of numbers -10 to 10 but this time, increment by 2. Assign this vector to `y`. 

*** =hint

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# Generate x = -10, -9, ..., 9, 10 using the seq() function


# Generate y = -10, -8, ..., 8, 10 using the seq() function with by = 2.
```

*** =solution
```{r}
# Generate x = -10, -9, ..., 9, 10 using the seq() function

x <- seq(-10, 10)

# Generate y = -10, -8, ..., 8, 10 using the seq() function with by = 2.

y <- seq(-10, 10, by = 2)
```

*** =sct
```{r}
test_object("x")
test_object("y")
success_msg("Nice!")


test_error()

success_msg("Good work!")
```

--- type:NormalExercise lang:r xp:100 skills:1 key:8c5519a279
## Variable Assignment


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
--- type:NormalExercise lang:r xp:100 skills:1 key:766b6a5af5


## Graphing data in R

In this exercise, you will practice using simple graphical functions in R to visualize data.

In it's most basic form, the `plot()` function will generate a scatterplot of the x and y values that have been passed through it. 

The format to make a basic scatterplot is:

`plot(x = dataset$var1 , y = dataset$var2)`

R has a built-in dataset called `women` which contains heights and weights of 15 women. 

This data set is already in your workspace so if you type  `women` into your R console, the entire data will come up in the output.

For this exercise, we are going to visualize the relationship between the two variables in `women`:

x = `height` 

y = `weight`

*** =instructions
- Use the `plot()` function to create a scatterplot of `height` by `weight`.
- After clicking 'Submit Answer', look at the plot in the output. Is there any pattern?
*** =hint
Follow the format in the lesson with `women` instead of `dataset`, `height` instead of `var1` and `weight` instead of `var2`
*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# Use plot() to create scatterplot of height by weight
```

*** =solution
```{r}
plot(x = women$height, y = women$weight)
```

*** =sct
```{r}
test_function("plot", args = c("x", "y"))
success_msg("Good work! From the plot we can see that as height increases, weight decreases.")
```
