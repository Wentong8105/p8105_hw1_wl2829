p8105\_hw1\_wl2829
================
Wentong
9/26/2021

## problem 1

### create dataframe

``` r
problem1_df <- tibble(
  vec_random = rnorm(10, mean = 0, sd = 1),
  vec_logic = vec_random > 0,
  vec_char = c("This","is","Wentong","Liu's","answer","for","homework","1","problem","1"),
  vec_factor = factor(c("good","good","good","medium","medium","medium","medium","bad","bad","bad"))
)
```

### take the mean of a variable in a dataframe

``` r
mean(pull(problem1_df,vec_random))        # mean works
```

    ## [1] 0.2365741

``` r
mean(pull(problem1_df,vec_logic))         # mean works
```

    ## [1] 0.5

``` r
mean(pull(problem1_df,vec_char))          # mean does not work
```

    ## Warning in mean.default(pull(problem1_df, vec_char)): argument is not numeric or
    ## logical: returning NA

    ## [1] NA

``` r
mean(pull(problem1_df,vec_factor))        # mean does not work
```

    ## Warning in mean.default(pull(problem1_df, vec_factor)): argument is not numeric
    ## or logical: returning NA

    ## [1] NA

### convert variables

``` r
as.numeric(pull(problem1_df,vec_logic))   # "TRUE"and"FALSE" -> "0"and"1"
as.numeric(pull(problem1_df,vec_char))    # cannot be converted to numbers
as.numeric(pull(problem1_df,vec_factor))  # "good","medium","bad" -> "2","3","1"
```

Conclusion: The logic and factor can be converted. The mean of the logic
vector works and it represents the tendency of true or false. On the
other hand, the mean of factor vector can not be calculated because it
is meaningless to some extent.

## Problem 2
