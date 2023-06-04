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
    ## • Use tidymodels_prefer() to resolve common conflicts.

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
  fit(pop ~ bpm + nrgy + dnce + dB + live + val + dur + acous +spch,
      data = music)

  tidy(mlr_mod)
```

    ## # A tibble: 10 × 5
    ##    term        estimate std.error statistic  p.value
    ##    <chr>          <dbl>     <dbl>     <dbl>    <dbl>
    ##  1 (Intercept)  68.1      4.86       14.0   3.09e-39
    ##  2 bpm           0.0197   0.0181      1.09  2.78e- 1
    ##  3 nrgy         -0.0949   0.0373     -2.54  1.12e- 2
    ##  4 dnce          0.142    0.0365      3.89  1.10e- 4
    ##  5 dB            0.965    0.179       5.40  9.52e- 8
    ##  6 live         -0.0290   0.0311     -0.934 3.51e- 1
    ##  7 val          -0.113    0.0231     -4.89  1.26e- 6
    ##  8 dur           0.0403   0.00774     5.20  2.61e- 7
    ##  9 acous        -0.165    0.0217     -7.60  9.98e-14
    ## 10 spch          0.176    0.0734      2.40  1.68e- 2

![
\\hat{y} = 68.144 +  0.020 \\times bpm - 0.095 \\times nrgy + 0.142 \\times dnce + 0.965 \\times dB - 0.029 \\times live - 0.113 \\times val + 0.40 \\times dur - 0.165 \\times acous + 0.176 \\times spch
](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%0A%5Chat%7By%7D%20%3D%2068.144%20%2B%20%200.020%20%5Ctimes%20bpm%20-%200.095%20%5Ctimes%20nrgy%20%2B%200.142%20%5Ctimes%20dnce%20%2B%200.965%20%5Ctimes%20dB%20-%200.029%20%5Ctimes%20live%20-%200.113%20%5Ctimes%20val%20%2B%200.40%20%5Ctimes%20dur%20-%200.165%20%5Ctimes%20acous%20%2B%200.176%20%5Ctimes%20spch%0A "
\hat{y} = 68.144 +  0.020 \times bpm - 0.095 \times nrgy + 0.142 \times dnce + 0.965 \times dB - 0.029 \times live - 0.113 \times val + 0.40 \times dur - 0.165 \times acous + 0.176 \times spch
")
