P8105\_hw1\_yz4188 document
================
yueran zhang
09/28/2021

This is my homework!

# Problem 1

The purpose of this part is the solution for problem 1.

\#**First we create a data frame** from a\_standard Normal
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
  
#**Then we calculate mean of the data** 

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

``` r
#**Lastly we convert variables to numeric factor**  

as.numeric(pull(df, X_2))
```

    ##  [1] 0 0 1 1 1 1 1 0 0 0

``` r
as.numeric(pull(df, X_3))
```

    ## Warning: NAs introduced by coercion

    ##  [1] NA NA NA NA NA NA NA NA NA NA

``` r
as.numeric(pull(df, X_4))
```

    ##  [1] 1 2 3 2 1 3 2 1 3 1

# Problem 2

The purpose of this part is the solution for problem 2.

**Firstly we inport the data**

``` r
data("penguins", package = "palmerpenguins")
  names(penguins)
```

    ## [1] "species"           "island"            "bill_length_mm"   
    ## [4] "bill_depth_mm"     "flipper_length_mm" "body_mass_g"      
    ## [7] "sex"               "year"

``` r
  summary(penguins)
```

    ##       species          island    bill_length_mm  bill_depth_mm  
    ##  Adelie   :152   Biscoe   :168   Min.   :32.10   Min.   :13.10  
    ##  Chinstrap: 68   Dream    :124   1st Qu.:39.23   1st Qu.:15.60  
    ##  Gentoo   :124   Torgersen: 52   Median :44.45   Median :17.30  
    ##                                  Mean   :43.92   Mean   :17.15  
    ##                                  3rd Qu.:48.50   3rd Qu.:18.70  
    ##                                  Max.   :59.60   Max.   :21.50  
    ##                                  NA's   :2       NA's   :2      
    ##  flipper_length_mm  body_mass_g       sex           year     
    ##  Min.   :172.0     Min.   :2700   female:165   Min.   :2007  
    ##  1st Qu.:190.0     1st Qu.:3550   male  :168   1st Qu.:2007  
    ##  Median :197.0     Median :4050   NA's  : 11   Median :2008  
    ##  Mean   :200.9     Mean   :4202                Mean   :2008  
    ##  3rd Qu.:213.0     3rd Qu.:4750                3rd Qu.:2009  
    ##  Max.   :231.0     Max.   :6300                Max.   :2009  
    ##  NA's   :2         NA's   :2

``` r
  nrow(penguins)
```

    ## [1] 344

``` r
  ncol(penguins)
```

    ## [1] 8

``` r
  mean(pull(penguins,flipper_length_mm), na.rm = TRUE)
```

    ## [1] 200.9152

**Lastly we create a graph for the data**

``` r
ggplot(penguins,aes( x = bill_length_mm , y = flipper_length_mm)) + geom_point(aes(color = species))
```

    ## Warning: Removed 2 rows containing missing values (geom_point).

![](template_files/figure-gfm/scatterplot-1.png)<!-- -->

``` r
ggsave("scatterplot.pdf", height = 4, width = 6)
```

    ## Warning: Removed 2 rows containing missing values (geom_point).
