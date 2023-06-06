Activity 3 - MLR
================

``` r
library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.2 ──
    ## ✔ ggplot2 3.3.6     ✔ purrr   0.3.4
    ## ✔ tibble  3.1.8     ✔ dplyr   1.0.9
    ## ✔ tidyr   1.2.0     ✔ stringr 1.4.1
    ## ✔ readr   2.1.2     ✔ forcats 0.5.2
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
library(tidymodels)
```

    ## ── Attaching packages ────────────────────────────────────── tidymodels 1.0.0 ──
    ## ✔ broom        1.0.0     ✔ rsample      1.1.0
    ## ✔ dials        1.0.0     ✔ tune         1.0.0
    ## ✔ infer        1.0.4     ✔ workflows    1.0.0
    ## ✔ modeldata    1.0.0     ✔ workflowsets 1.0.0
    ## ✔ parsnip      1.0.1     ✔ yardstick    1.0.0
    ## ✔ recipes      1.0.1     
    ## ── Conflicts ───────────────────────────────────────── tidymodels_conflicts() ──
    ## ✖ scales::discard() masks purrr::discard()
    ## ✖ dplyr::filter()   masks stats::filter()
    ## ✖ recipes::fixed()  masks stringr::fixed()
    ## ✖ dplyr::lag()      masks stats::lag()
    ## ✖ yardstick::spec() masks readr::spec()
    ## ✖ recipes::step()   masks stats::step()
    ## • Use suppressPackageStartupMessages() to eliminate package startup messages

``` r
library(GGally)
```

    ## Registered S3 method overwritten by 'GGally':
    ##   method from   
    ##   +.gg   ggplot2

``` r
music_50s <- read.csv("1950[1].csv")
music_60s <- read.csv("1960[1].csv")
music_70s <- read.csv("1970[1].csv")
music_80s <- read.csv("1980[1].csv")
music_90s <- read.csv("1990[1].csv")
music_00s <- read.csv("2000[1].csv")
music_10s <- read.csv("2010[1].csv")
```

``` r
music <- rbind(music_50s, music_60s, music_70s, music_80s, music_90s, music_00s,
               music_10s)
```

``` r
  music %>% 
    select(pop, bpm, nrgy) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_bpm_nrgy-1.png)<!-- -->

``` r
  music %>% 
    select(pop, bpm, dnce) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_bpm_dnce-1.png)<!-- -->

``` r
  music %>% 
    select(pop, bpm, dB) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_bpm_dB-1.png)<!-- -->

``` r
  music %>% 
    select(pop, bpm, live) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_bpm_live-1.png)<!-- -->

``` r
  music %>% 
    select(pop, bpm, val) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_bpm_val-1.png)<!-- -->

``` r
  music %>% 
    select(pop, bpm, dur) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_bpm_dur-1.png)<!-- -->

``` r
  music %>% 
    select(pop, bpm, acous) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_bpm_acous-1.png)<!-- -->

``` r
  music %>% 
    select(pop, spch) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_bpm_spch-1.png)<!-- -->

``` r
  music %>% 
    select(pop, nrgy, dnce) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_nrgy_dnce-1.png)<!-- -->

``` r
  music %>% 
    select(pop, nrgy, dB) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_nrgy_dB-1.png)<!-- -->

``` r
  music %>% 
    select(pop, nrgy, live) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_nrgy_live-1.png)<!-- -->

``` r
  music %>% 
    select(pop, nrgy, val) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_nrgy_val-1.png)<!-- -->

``` r
  music %>% 
    select(pop, nrgy, dur) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_nrgy_dur-1.png)<!-- -->

``` r
  music %>% 
    select(pop, nrgy, acous) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_nrgy_acous-1.png)<!-- -->

``` r
  music %>% 
    select(pop, nrgy, spch) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_nrgy_spch-1.png)<!-- -->

``` r
  music %>% 
    select(pop, dnce, dB) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_dnce_dB-1.png)<!-- -->

``` r
  music %>% 
    select(pop, dnce, live) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_dnce_live-1.png)<!-- -->

``` r
  music %>% 
    select(pop, dnce, val) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_dnce_val-1.png)<!-- -->

``` r
  music %>% 
    select(pop, dnce, dur) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_dnce_dur-1.png)<!-- -->

``` r
  music %>% 
    select(pop, dnce, acous) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_dnce_acous-1.png)<!-- -->

``` r
  music %>% 
    select(pop, dnce, spch) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_dnce_spch-1.png)<!-- -->

``` r
  music %>% 
    select(pop, dB, live) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_dB_live-1.png)<!-- -->

``` r
  music %>% 
    select(pop, dB, val) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_dB_val-1.png)<!-- -->

``` r
  music %>% 
    select(pop, dB, dur) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_dB_dur-1.png)<!-- -->

``` r
  music %>% 
    select(pop, dB, acous) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_dB_acous-1.png)<!-- -->

``` r
  music %>% 
    select(pop, dB, spch) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_dB_spch-1.png)<!-- -->

``` r
  music %>% 
    select(pop, live, val ) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_live_val-1.png)<!-- -->

``` r
  music %>% 
    select(pop, live, dur) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_live_dur-1.png)<!-- -->

``` r
  music %>% 
    select(pop, live, acous) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_live_acous-1.png)<!-- -->

``` r
  music %>% 
    select(pop, live, spch) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_live_spch-1.png)<!-- -->

``` r
  music %>% 
    select(pop, val, dur) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_val_dur-1.png)<!-- -->

``` r
  music %>% 
    select(pop, val, acous) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_val_acous-1.png)<!-- -->

``` r
  music %>% 
    select(pop, val, spch) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_val_spch-1.png)<!-- -->

``` r
  music %>% 
    select(pop, dur, acous) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_dur_acous-1.png)<!-- -->

``` r
  music %>% 
    select(pop, dur, spch) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_dur_spch-1.png)<!-- -->

``` r
  music %>% 
    select(pop, acous, spch) %>% 
    ggpairs()
```

![](activity03_files/figure-gfm/exploring_variable_acous_spch-1.png)<!-- -->

``` r
  lm_spec <- linear_reg() %>%
  set_mode("regression") %>%
  set_engine("lm")

  lm_spec
```

    ## Linear Regression Model Specification (regression)
    ## 
    ## Computational engine: lm

``` r
  mlr_mod <- lm_spec %>% 
  fit(pop ~ nrgy + dB, data = music)

  tidy(mlr_mod)
```

    ## # A tibble: 3 × 5
    ##   term        estimate std.error statistic  p.value
    ##   <chr>          <dbl>     <dbl>     <dbl>    <dbl>
    ## 1 (Intercept)  73.0       3.33      21.9   1.24e-80
    ## 2 nrgy          0.0190    0.0321     0.593 5.53e- 1
    ## 3 dB            1.29      0.190      6.78  2.69e-11

![
\\hat{y} = 72.963 +  0.019 \\times nrgy + 1.29 \\times dB
](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%0A%5Chat%7By%7D%20%3D%2072.963%20%2B%20%200.019%20%5Ctimes%20nrgy%20%2B%201.29%20%5Ctimes%20dB%0A "
\hat{y} = 72.963 +  0.019 \times nrgy + 1.29 \times dB
")

``` r
music$top.genre <- gsub(".*aus.*|.*brit.*|.*canad.*|.*irish.*|.*italian.*|.*uk.*|.*euro.*|.*german.*|.*merseybeat.*|.*yodeling.*|.*chanson.*|.*belgian.*|.*celtic.*|.*latin.*|.*afro.*|.*bubblegum.*|.*trance.*","international",music$top.genre)
```

``` r
music$top.genre <- gsub(".*pop.*|.*adult standards.*|.*beach.*|.*hollywood.*|.*boy band.*","pop",music$top.genre)
```

``` r
music$top.genre <- gsub(".*rock.*|.*metal.*|.*mellow gold.*|.*punk.*|.*permanent wave.*","rock",music$top.genre)
```

``` r
music$top.genre <- gsub(".*hip-hop.*|.*hip hop.*|.*doo-wop.*|.*soul.*|.*blues.*|.*girl.*|.*bebop.*|.*boogaloo.*|.*jazz.*|.*disco.*|.*r&b.*|.*hi-nrg.*|.*funk.*|.*neo.*|.*house.*|.*big.*|.*rap.*|.*brostep.*|.*complextro.*|.*edm.*", "rock",music$top.genre)
```

``` r
music$top.genre <- gsub(".*country.*|.*folk.*|.*western.*|.*american.*","country",music$top.genre)
```

``` r
music$international <- ifelse(music$top.genre == 'international', 1, 0)
music$domestic <- ifelse(music$top.genre != 'international', 1, 0)
```

``` r
  # review any visual patterns
music%>% 
  select(pop, dB, nrgy, international) %>% 
  ggpairs()
```

![](activity03_files/figure-gfm/unnamed-chunk-7-1.png)<!-- -->

``` r
#fit the mlr model
lm_spec <- linear_reg() %>%
set_mode("regression") %>%
set_engine("lm")
```

``` r
mlr_mod2 <- lm_spec %>% 
  fit(pop ~ nrgy + dB + international, data = music)

tidy(mlr_mod2)
```

    ## # A tibble: 4 × 5
    ##   term          estimate std.error statistic  p.value
    ##   <chr>            <dbl>     <dbl>     <dbl>    <dbl>
    ## 1 (Intercept)    72.9       3.33      21.9   3.34e-80
    ## 2 nrgy            0.0212    0.0325     0.653 5.14e- 1
    ## 3 dB              1.28      0.191      6.72  3.80e-11
    ## 4 international  -0.650     1.40      -0.465 6.42e- 1

![
\\hat{y} = 72.877 +  0.021 \\times nrgy + 1.284 \\times dB - 0.65  (if  international)
](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%0A%5Chat%7By%7D%20%3D%2072.877%20%2B%20%200.021%20%5Ctimes%20nrgy%20%2B%201.284%20%5Ctimes%20dB%20-%200.65%20%20%28if%20%20international%29%0A "
\hat{y} = 72.877 +  0.021 \times nrgy + 1.284 \times dB - 0.65  (if  international)
")

``` r
  mlr_mod3<- lm_spec %>% 
  fit(pop ~ nrgy + dB + domestic, data = music)

  tidy(mlr_mod3)
```

    ## # A tibble: 4 × 5
    ##   term        estimate std.error statistic  p.value
    ##   <chr>          <dbl>     <dbl>     <dbl>    <dbl>
    ## 1 (Intercept)  72.2       3.69      19.6   8.68e-68
    ## 2 nrgy          0.0212    0.0325     0.653 5.14e- 1
    ## 3 dB            1.28      0.191      6.72  3.80e-11
    ## 4 domestic      0.650     1.40       0.465 6.42e- 1

![
\\hat{y} = 72.227 +  0.021 \\times nrgy + 1.284 \\times dB + 0.65  (if  domestic)
](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%0A%5Chat%7By%7D%20%3D%2072.227%20%2B%20%200.021%20%5Ctimes%20nrgy%20%2B%201.284%20%5Ctimes%20dB%20%2B%200.65%20%20%28if%20%20domestic%29%0A "
\hat{y} = 72.227 +  0.021 \times nrgy + 1.284 \times dB + 0.65  (if  domestic)
")
