---
title: 'tt: Employment and Earnings'
author: RWW
date: '2021-02-22'
slug: []
categories:
  - R
  - tidyTuesday
  - dataviz
tags:
  - R
  - tidyTuesday
  - R Markdown
---

As a continuation of the #DuBoisChallenge, this week's tidyTuesday presents employment by industry, sex, race, and occupation.  There is also some scraped data from the self-service tool that generates weekly and hourly earnings data from the CPS.  Let's see what we have.


```r
library(tidyverse)
```

```
## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.0 ──
```

```
## ✓ ggplot2 3.3.3     ✓ purrr   0.3.4
## ✓ tibble  3.0.6     ✓ dplyr   1.0.4
## ✓ tidyr   1.1.2     ✓ stringr 1.4.0
## ✓ readr   1.4.0     ✓ forcats 0.5.1
```

```
## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
## x dplyr::filter() masks stats::filter()
## x dplyr::lag()    masks stats::lag()
```

```r
library(fpp3)
```

```
## ── Attaching packages ──────────────────────────────────────────── fpp3 0.4.0 ──
```

```
## ✓ lubridate   1.7.9.2     ✓ feasts      0.1.7  
## ✓ tsibble     1.0.0       ✓ fable       0.3.0  
## ✓ tsibbledata 0.2.0
```

```
## ── Conflicts ───────────────────────────────────────────────── fpp3_conflicts ──
## x lubridate::date()    masks base::date()
## x dplyr::filter()      masks stats::filter()
## x tsibble::intersect() masks base::intersect()
## x tsibble::interval()  masks lubridate::interval()
## x dplyr::lag()         masks stats::lag()
## x tsibble::setdiff()   masks base::setdiff()
## x tsibble::union()     masks base::union()
```

```r
library(magrittr)
```

```
## 
## Attaching package: 'magrittr'
```

```
## The following object is masked from 'package:purrr':
## 
##     set_names
```

```
## The following object is masked from 'package:tidyr':
## 
##     extract
```

```r
employed <- readr::read_csv('https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2021/2021-02-23/employed.csv')
```

```
## 
## ── Column specification ────────────────────────────────────────────────────────
## cols(
##   industry = col_character(),
##   major_occupation = col_character(),
##   minor_occupation = col_character(),
##   race_gender = col_character(),
##   industry_total = col_double(),
##   employ_n = col_double(),
##   year = col_double()
## )
```

```r
earn <- readr::read_csv('https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2021/2021-02-23/earn.csv')
```

```
## 
## ── Column specification ────────────────────────────────────────────────────────
## cols(
##   sex = col_character(),
##   race = col_character(),
##   ethnic_origin = col_character(),
##   age = col_character(),
##   year = col_double(),
##   quarter = col_double(),
##   n_persons = col_double(),
##   median_weekly_earn = col_double()
## )
```

```r
employed %<>% as_tsibble(index=year, key=c(industry,major_occupation,minor_occupation,race_gender))
```


```r
employed %>% filter(race_gender=="TOTAL") %>% autoplot(employ_n) + guides(color=FALSE)
```

```
## Warning: Removed 132 row(s) containing missing values (geom_path).
```

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-2-1.png" width="672" />

To be continued....
