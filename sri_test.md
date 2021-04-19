Untitled
================

\#base Data

``` r
library(pacman)
p_load(COVID19, car, tidyverse, ggplot2, dplyr, leaps, readr)

#wdcovid<- covid19( 
  #country = NULL,
  #level = 1,
  #start = "2020-03-15",
  #end = "2021-03-15",
  #raw = TRUE,
  #vintage = FALSE,
  #verbose = TRUE,
  #cache = TRUE)

x <- covid19()
```

    ## We have invested a lot of time and effort in creating COVID-19 Data Hub, please cite the following when using it:
    ## 
    ##   Guidotti, E., Ardia, D., (2020), "COVID-19 Data Hub", Journal of Open
    ##   Source Software 5(51):2376, doi: 10.21105/joss.02376.
    ## 
    ## A BibTeX entry for LaTeX users is
    ## 
    ##   @Article{,
    ##     title = {COVID-19 Data Hub},
    ##     year = {2020},
    ##     doi = {10.21105/joss.02376},
    ##     author = {Emanuele Guidotti and David Ardia},
    ##     journal = {Journal of Open Source Software},
    ##     volume = {5},
    ##     number = {51},
    ##     pages = {2376},
    ##   }
    ## 
    ## To retrieve citation and metadata of the data sources see ?covid19cite. To hide this message use 'verbose = FALSE'.

``` r
covid19<- covid19(level = 1, start = "2020-03-15", end = "2021-03-15",)
wb <- c("gdp" = "NY.GDP.MKTP.CD", "hosp_beds" = "SH.MED.BEDS.ZS")
wbdcovid  <- covid19(wb = wb)
```

    ## We have invested a lot of time and effort in creating COVID-19 Data Hub, please cite the following when using it:
    ## 
    ##   Guidotti, E., Ardia, D., (2020), "COVID-19 Data Hub", Journal of Open
    ##   Source Software 5(51):2376, doi: 10.21105/joss.02376.
    ## 
    ## A BibTeX entry for LaTeX users is
    ## 
    ##   @Article{,
    ##     title = {COVID-19 Data Hub},
    ##     year = {2020},
    ##     doi = {10.21105/joss.02376},
    ##     author = {Emanuele Guidotti and David Ardia},
    ##     journal = {Journal of Open Source Software},
    ##     volume = {5},
    ##     number = {51},
    ##     pages = {2376},
    ##   }
    ## 
    ## To retrieve citation and metadata of the data sources see ?covid19cite. To hide this message use 'verbose = FALSE'.

``` r
wbdcovid
```

    ## # A tibble: 89,966 x 38
    ## # Groups:   id [199]
    ##    iso_alpha_3 id    date       vaccines tests confirmed recovered deaths  hosp
    ##    <chr>       <chr> <date>        <dbl> <int>     <int>     <int>  <int> <dbl>
    ##  1 AFG         AFG   2020-01-22       NA    NA        NA        NA     NA    NA
    ##  2 AFG         AFG   2020-01-23       NA    NA        NA        NA     NA    NA
    ##  3 AFG         AFG   2020-01-24       NA    NA        NA        NA     NA    NA
    ##  4 AFG         AFG   2020-01-25       NA    NA        NA        NA     NA    NA
    ##  5 AFG         AFG   2020-01-26       NA    NA        NA        NA     NA    NA
    ##  6 AFG         AFG   2020-01-27       NA    NA        NA        NA     NA    NA
    ##  7 AFG         AFG   2020-01-28       NA    NA        NA        NA     NA    NA
    ##  8 AFG         AFG   2020-01-29       NA    NA        NA        NA     NA    NA
    ##  9 AFG         AFG   2020-01-30       NA    NA        NA        NA     NA    NA
    ## 10 AFG         AFG   2020-01-31       NA    NA        NA        NA     NA    NA
    ## # … with 89,956 more rows, and 29 more variables: vent <int>, icu <int>,
    ## #   population <int>, school_closing <int>, workplace_closing <int>,
    ## #   cancel_events <int>, gatherings_restrictions <int>,
    ## #   transport_closing <int>, stay_home_restrictions <int>,
    ## #   internal_movement_restrictions <int>,
    ## #   international_movement_restrictions <int>, information_campaigns <int>,
    ## #   testing_policy <int>, contact_tracing <int>, stringency_index <dbl>,
    ## #   iso_alpha_2 <chr>, iso_numeric <int>, currency <chr>,
    ## #   administrative_area_level <int>, administrative_area_level_1 <chr>,
    ## #   administrative_area_level_2 <lgl>, administrative_area_level_3 <lgl>,
    ## #   latitude <dbl>, longitude <dbl>, key <lgl>, key_apple_mobility <chr>,
    ## #   key_google_mobility <chr>, gdp <dbl>, hosp_beds <dbl>
