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

Some arithmetic symbols you can use in R code include: + - / * sqrt() ^ pi

For example, if I want to cube '4', I would type 4^3 into the console.
I can also assign the value '4' to 'x' by typing `x <- 4` into the console. Then I could get the cube of 'x' with `x^3`.
If I want to assign a list of numbers (ex. 1, 2, 3, 4) to `x` I can type `x <- c(1, 2, 3, 4)` into the console and `x^3` would produce a vector of 4 values `[1, 8, 27, 64]` 

*** =instructions
- Find the area of a circle whose radius is 7
- Create a vector `y` that is a list of whole numbers 1-5 then use the `sqrt()` function to get the square root of those numbers.
- Create another vector `x` that takes on values 6,7,8,9,10.
- Find x*y
- Find `x^2 + y^2`

*** =hint
- The area of a circle is: Area = pi*radius^2
- For the second instruction, you should use `...[movie_selection$Rating >= 5, ]`.
- For the plot, use `plot(x = ..., y = ..., col = ...)`.

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
# Use R as a calculator to find the area of a circle 

# Define y using the c() function, then get the square root of y.


# Select movies that have a rating of 5 or higher: good_movies


# Plot Run (i.e. run time) on the x axis, Rating on the y axis, and set the color using Genre

```

*** =solution
```{r}
# movie_selection is available in your workspace

# Check out the structure of movie_selection
str(movie_selection)

# Select movies that have a rating of 5 or higher: good_movies
good_movies <- movie_selection[movie_selection$Rating >= 5, ]

# Plot Run (i.e. run time) on the x axis, Rating on the y axis, and set the color using Genre
plot(good_movies$Run, good_movies$Rating, col = good_movies$Genre)
```

*** =sct
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

test_function("str", args = "object",
              not_called_msg = "You didn't call `str()`!",
              incorrect_msg = "You didn't call `str(object = ...)` with the correct argument, `object`.")

test_object("good_movies")

test_function("plot", args = "x")
test_function("plot", args = "y")
test_function("plot", args = "col")

test_error()

success_msg("Good work!")
```
