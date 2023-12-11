STAT 184 FINAL JO X ERYN
================
Josiah Harrison
2023-12-04

library(ggplot2)

``` r
library(ggplot2)
```

``` r
# Research Question 1: Which ethnic groups have experienced most change from 2014 to 2020?

google2 <- read.csv("C:/Users/Owner/Desktop/R-STAT 184/STAT 184 FA23/FinalProject.csv")

google2
```

    ##    Year       Ethnicity Percent
    ## 1  2014           Asian    31.5
    ## 2  2014           Black     2.4
    ## 3  2014        Hispanic     4.5
    ## 4  2014 Native American     1.0
    ## 5  2014           White    64.5
    ## 6  2015           Asian    32.7
    ## 7  2015           Black     2.5
    ## 8  2015        Hispanic     4.9
    ## 9  2015 Native American     0.8
    ## 10 2015           White    62.9
    ## 11 2016           Asian    33.9
    ## 12 2016           Black     2.8
    ## 13 2016        Hispanic     5.2
    ## 14 2016 Native American     0.8
    ## 15 2016           White    61.0
    ## 16 2017           Asian    36.3
    ## 17 2017           Black     2.8
    ## 18 2017        Hispanic     5.2
    ## 19 2017 Native American     0.8
    ## 20 2017           White    58.5
    ## 21 2018           Asian    38.1
    ## 22 2018           Black     3.0
    ## 23 2018        Hispanic     5.3
    ## 24 2018 Native American     0.3
    ## 25 2018           White    56.6
    ## 26 2019           Asian    39.8
    ## 27 2019           Black     3.3
    ## 28 2019        Hispanic     5.7
    ## 29 2019 Native American     0.8
    ## 30 2019           White    54.4
    ## 31 2020           Asian    41.9
    ## 32 2020           Black     3.7
    ## 33 2020        Hispanic     5.9
    ## 34 2020 Native American     0.8
    ## 35 2020           White    51.7
    ## 36 2021           Asian    42.3
    ## 37 2021           Black     4.4
    ## 38 2021        Hispanic     6.4
    ## 39 2021 Native American     0.8
    ## 40 2021           White    50.4
    ## 41 2022           Asian    43.2
    ## 42 2022           Black     5.3
    ## 43 2022        Hispanic     6.9
    ## 44 2022 Native American     0.8
    ## 45 2022           White    48.3
    ## 46 2023           Asian    44.8
    ## 47 2023           Black     5.6
    ## 48 2023        Hispanic     7.3
    ## 49 2023 Native American     0.8
    ## 50 2023           White    46.2

``` r
library(ggplot2)

ggplot(google2, aes(x=Year, y = Percent, color = Ethnicity, group = Ethnicity)) +
  geom_line(size = 1) +
  ggtitle("Diversity Hires at Google Between 2014-2023") +
  xlab("Year") +
  ylab("Ethnicity") +
  theme_minimal() +
  xlim(2014, 2020)
```

    ## Warning: Using `size` aesthetic for lines was deprecated in ggplot2 3.4.0.
    ## ℹ Please use `linewidth` instead.

    ## Warning: Removed 15 rows containing missing values (`geom_line()`).

![](Title_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

``` r
ggplot(google2, aes(x = Year, y = Percent, color = Ethnicity, group = Ethnicity)) +
  geom_line(size = 1) +
  ggtitle("Diversity Hires at Google Between 2020-2023") +
  xlab("Year") +
  ylab("Ethnicity") +
  theme_minimal() +
  xlim(2020, 2023)
```

    ## Warning: Removed 30 rows containing missing values (`geom_line()`).

![](Title_files/figure-gfm/unnamed-chunk-2-2.png)<!-- -->

``` r
ggplot(google2, aes(x=Year, y = Percent, color = Ethnicity, group = Ethnicity)) +
         geom_line(size = 1) +
         ggtitle("Diversity Hires at Google Between 2014-2023") +
         xlab("Year") +
         ylab("Ethnicity") +
         theme_minimal() +
         #xlim(2014, 2023) +
         scale_x_continuous(breaks = c(2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021, 2022, 2023))
```

![](Title_files/figure-gfm/unnamed-chunk-2-3.png)<!-- -->

``` r
ggplot(data = google2, aes(x = Year, y = Percent, size = Percent, color = Ethnicity)) +
  geom_point(alpha = 0.7) +
  labs(title = "Bubble Chart of Year-wise Ethnic Group Retention Rates",
       x = "Year",
       y = "Retention Rate") 
```

![](Title_files/figure-gfm/unnamed-chunk-2-4.png)<!-- -->

``` r
# Research Question 2: Non-white vs White

library(ggplot2)

google3 <- read.csv("C:/Users/Owner/Desktop/R-STAT 184/STAT 184 FA23/FinalProject.csv")

google3
```

    ##    Year       Ethnicity Percent
    ## 1  2014           Asian    31.5
    ## 2  2014           Black     2.4
    ## 3  2014        Hispanic     4.5
    ## 4  2014 Native American     1.0
    ## 5  2014           White    64.5
    ## 6  2015           Asian    32.7
    ## 7  2015           Black     2.5
    ## 8  2015        Hispanic     4.9
    ## 9  2015 Native American     0.8
    ## 10 2015           White    62.9
    ## 11 2016           Asian    33.9
    ## 12 2016           Black     2.8
    ## 13 2016        Hispanic     5.2
    ## 14 2016 Native American     0.8
    ## 15 2016           White    61.0
    ## 16 2017           Asian    36.3
    ## 17 2017           Black     2.8
    ## 18 2017        Hispanic     5.2
    ## 19 2017 Native American     0.8
    ## 20 2017           White    58.5
    ## 21 2018           Asian    38.1
    ## 22 2018           Black     3.0
    ## 23 2018        Hispanic     5.3
    ## 24 2018 Native American     0.3
    ## 25 2018           White    56.6
    ## 26 2019           Asian    39.8
    ## 27 2019           Black     3.3
    ## 28 2019        Hispanic     5.7
    ## 29 2019 Native American     0.8
    ## 30 2019           White    54.4
    ## 31 2020           Asian    41.9
    ## 32 2020           Black     3.7
    ## 33 2020        Hispanic     5.9
    ## 34 2020 Native American     0.8
    ## 35 2020           White    51.7
    ## 36 2021           Asian    42.3
    ## 37 2021           Black     4.4
    ## 38 2021        Hispanic     6.4
    ## 39 2021 Native American     0.8
    ## 40 2021           White    50.4
    ## 41 2022           Asian    43.2
    ## 42 2022           Black     5.3
    ## 43 2022        Hispanic     6.9
    ## 44 2022 Native American     0.8
    ## 45 2022           White    48.3
    ## 46 2023           Asian    44.8
    ## 47 2023           Black     5.6
    ## 48 2023        Hispanic     7.3
    ## 49 2023 Native American     0.8
    ## 50 2023           White    46.2

``` r
ggplot(data = google3, aes(x = Year, y = Percent, fill = Ethnicity)) +
  geom_area() +
  labs(title = "Stacked Area Plot of Diversity Hires by Ethnicity at Google",
       x = "Year",
       y = "Retention Rate") +
  xlim(2014, 2023)
```

![](Title_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

``` r
ggplot(data = google3, aes(x = Year, y = Percent)) +
  geom_line() +
  facet_wrap(~Ethnicity) +
  labs(title = "Faceted Line Plot of Ethnic Group Retention Rates",
       x = "Year",
       y = "Retention Rate")
```

![](Title_files/figure-gfm/unnamed-chunk-3-2.png)<!-- -->
