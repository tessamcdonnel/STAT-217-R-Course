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
