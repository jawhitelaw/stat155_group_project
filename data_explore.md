---
title: "GitHub for collaboration"
output:
  html_document: 
    keep_md : yes
---

Welcome to the group project!


```r
library(fivethirtyeight)
library(tidyverse)
library(ggmosaic)
```


```r
steak_survey %>% 
  ggplot()+
  geom_bar(aes(x=steak_prep, fill=smoke), position = "fill")
```

![](data_explore_files/figure-html/unnamed-chunk-2-1.png)<!-- -->


```r
steak_survey %>% 
  ggplot()+
  geom_bar(aes(x=steak_prep, fill=region), position = "fill")
```

![](data_explore_files/figure-html/unnamed-chunk-3-1.png)<!-- -->


```r
steak_survey %>% 
  ggplot()+
  geom_bar(aes(x=steak_prep, fill=cheated), position = "fill")
```

![](data_explore_files/figure-html/unnamed-chunk-4-1.png)<!-- -->




```r
weather_check %>%
  ggplot() +
  geom_count(aes(x = ck_weather, y = hhold_income), color = "cornflowerblue")
```

![](data_explore_files/figure-html/unnamed-chunk-5-1.png)<!-- -->



```r
weather_check %>%
  ggplot() +
  geom_mosaic(aes(x = product(factor(age),ck_weather), fill = factor(age)))
```

![](data_explore_files/figure-html/unnamed-chunk-6-1.png)<!-- -->


```r
weather_check %>%
  ggplot() +
  geom_mosaic(aes(x = product(factor(hhold_income),ck_weather), fill = factor(hhold_income)))
```

![](data_explore_files/figure-html/unnamed-chunk-7-1.png)<!-- -->



```r
weather_check %>% 
  ggplot()+
  geom_bar(aes(x=age, fill=weather_source), position = "fill")
```

![](data_explore_files/figure-html/unnamed-chunk-8-1.png)<!-- -->







