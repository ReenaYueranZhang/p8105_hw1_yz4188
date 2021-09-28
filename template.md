P8105\_hw1\_yz4188 document
================
yueran zhang
09/28/2021

This is

# Problem 1

The purpose of this part is the solution for problem 1.

First we create a data frame comprised of **a random sample of size 10
and a logical vector indicating whether elements of the sample are
greater than 0** from a\_standard Normal distribution\_:

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
  la_df = tibble(
  norm_samp = rnorm(10, mean = 0), 
  norm_samp_pos = norm_samp > 0,
  )
```
