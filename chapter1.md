---
title       : Lab 1
description : Introduction to R and RStudio
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf

--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:10124e5c35
## Getting Started with R

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

msg_bad <- "That is not correct!"
msg_success <- "Exactly! R can do all of these things."
test_mc(correct = 4, feedback_msgs = c(msg_bad, msg_bad, msg_bad, msg_success))
```

--- type:NormalExercise lang:r xp:100 skills:1 key:dbdb4a1084
## R as a Calculator

In this exercise, we'll see how R can be used to perform simple arithmetic tasks.

Some arithmetic symbols you can use in R code include: + - / * sqrt() ^ pi.

For example, if I want to cube '4', I would type 4^3 into the console.

I can also assign the value '4' to 'x' by typing `x <- 4` into the console. Then I could get the cube of 'x' with `x^3`.

If I want to assign a list of numbers (ex. 1, 2, 3, 4) to `x` I can type `x <- c(1, 2, 3, 4)` into the console and `x^3` would produce a vector of 4 values `[1, 8, 27, 64]` 

*** =instructions
- Use R as a calculator to find the area of a circle whose radius is 7
- Create a vector `y` that is a list of whole numbers `1, 2, 3, 4, 5`  then use the `sqrt()` function to get the square root of those numbers.
- Create another vector `x` that takes on values `6, 7, 8, 9, 10`.
- Find `x*y`
- Find `x^2 + y^2`

*** =hint
- The area of a circle is: `Area = pi*radius^2`
- For the second and third instructions, you should use the `c()` function to create vectors x and y.


*** =pre_exercise_code
```{r}
# You can also prepare your dataset in a specific way in the pre exercise code
load(url("https://s3.amazonaws.com/assets.datacamp.com/course/teach/movies.RData"))
movie_selection <- Movies[Movies$Genre %in% c("action", "animated", "comedy"), c("Genre", "Rating", "Run")]

# Clean up the environment
rm(Movies)
```

*** =sample_code
```{r}
# Use R as a calculator to find the area of a circle (pi*r^2)

# Define y using the c() function, then get the square root of y.


# Define x

# Calculate x*y

# Calculate x^2 + y^2




```

*** =solution
```{r}
# Use R as a calculator to find the area of a circle (pi*r^2)
pi*7^2

# Create vector y using the c() function, then get the square root of y.
y <- c(1, 2, 3, 4, 5)
y^2

# Define vector x
x <- c(6, 7, 8, 9, 10)

# Calculate x*y
x*y

# Calculate x^2 + y^2
x^2 + y^2

```

*** =sct
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki


test_object("x")
test_object("y")
success_msg("Nice!")


test_error()

success_msg("Good work!")
```




--- type:NormalExercise lang:r xp:100 skills:1 key:4ea9b80fa0
## Generating Numbers

We can also use R to generate numbers and lists.

The `seq()` function generates a sequence of numbers. If I want a sequence of number 1 through 20, I can type `seq(1, 20)` into my console. Try this. We can also use the `by = ` arguement to get a different sequence. Type `seq(1:20, by = 0.5) and notice how the output has changed.

*** =instructions
- Use the `seq()` function to generate of list of numbers from -10 to 10, increasing by 1. Assign this vector to `x` using the `c()` function.
- Create another sequence of numbers -10 to 10 but this time, increment by 2. Assign this vector to `y` again using the `c()` function. 

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

In it's most basic form, the plot() function will generate a plot of the x and y values that have been passed through it. The result is a basic scatter plot, but we can make it look nicer by specifying more arguements such as color and point type.

You can use the help function ?plot 

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
