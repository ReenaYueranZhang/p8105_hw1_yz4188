P8105\_hw1\_yz4188 document
================
yueran zhang
09/28/2021

This is

# Problem 1

The purpose of this part is the solution for problem 1.

\#First we create a data frame\*\* from a\_standard Normal
distribution\_:

``` r
library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.1 ──

    ## ✓ ggplot2 3.3.5     ✓ purrr   0.3.4
    ## ✓ tibble  3.1.4     ✓ dplyr   1.0.7
    ## ✓ tidyr   1.1.3     ✓ stringr 1.4.0
    ## ✓ readr   2.0.1     ✓ forcats 0.5.1

    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
  set.seed(123)
  df <- tibble( 
    X_1 = rnorm( 10, sd = 1),
    X_2 = X_1 > 0,
    X_3 = c("a", "b", "c", "d","e", "f", "g","h","i","j"),
    X_4 = factor(c("1", "2", "3", "2","1", "3", "2","1","3","1"))
  )
  
  mean_samp1 = mean(pull(df, X_1))
  mean_samp2 = mean(pull(df, X_2))
  mean_samp3 = mean(pull(df, X_3))
```

    ## Warning in mean.default(pull(df, X_3)): argument is not numeric or logical:
    ## returning NA

``` r
  mean_samp4 = mean(pull(df, X_4))
```

    ## Warning in mean.default(pull(df, X_4)): argument is not numeric or logical:
    ## returning NA
