---
title: "Gambling in America"
output:
  html_document:
    keep_md: yes
  'html_document : keep_md : yes': default
---

Welcome to the group project!


<<<<<<< HEAD
```r
library(fivethirtyeight)
library(tidyverse)
library(ggmosaic)
library(broom)
```
=======

Research Question: What factors increase a person's likelyhood to cheat? This comes from a survey about how people like their steak done however because of how the study was conducted, each variable can be treated as the response variable so we are treating the cheated variable as the response variable. It was collected through a random anonymous survey with various random questions. We hope to be able to predict some factors that would increase a person's chance at cheating.
>>>>>>> 944725faf56428e1497ce5605bf3b9393a4a95ba

Research Question: What factors increase a person's likelyhood to cheat? This comes from a survey about how people like their steak done however because of how the study was conducted, each variable can be treated as the response variable so we are treating the cheated variable as the response variable. It was collected through a random anonymous survey with various random questions. We hope to be able to predict some factors that would increase a person's chance at cheating.

```r
steak_survey %>% 
  ggplot()+
<<<<<<< HEAD
  geom_bar(aes(x=cheated, fill=smoke), position = "fill")
=======
  geom_bar(aes(x = cheated))
>>>>>>> 944725faf56428e1497ce5605bf3b9393a4a95ba
```

![](data_explore_files/figure-html/unnamed-chunk-2-1.png)<!-- -->

People who said they cheated also had a higher likelyhood to also smoke.


```r
steak_survey %>% 
  ggplot()+
<<<<<<< HEAD
  geom_bar(aes(x=cheated, fill=region), position = "fill")
=======
  geom_bar(aes(x=cheated, fill=smoke), position = "fill")
>>>>>>> 944725faf56428e1497ce5605bf3b9393a4a95ba
```

![](data_explore_files/figure-html/unnamed-chunk-3-1.png)<!-- -->

<<<<<<< HEAD
There was a statistically significant difference between the proportion of people who cheated and who didn't in the West North Central and Middle Atlantic showing these regions may have more cheaters whereas the Pacific had a smaller proportion of cheaters compared to non-cheaters.
=======
People who said they cheated also had a higher likelyhood to also smoke.
>>>>>>> 944725faf56428e1497ce5605bf3b9393a4a95ba


```r
steak_survey %>% 
  ggplot()+
<<<<<<< HEAD
  geom_bar(aes(x=cheated, fill=female), position = "fill")
=======
  geom_bar(aes(x=cheated, fill=region), position = "fill")
>>>>>>> 944725faf56428e1497ce5605bf3b9393a4a95ba
```

![](data_explore_files/figure-html/unnamed-chunk-4-1.png)<!-- -->

<<<<<<< HEAD
There was a larger proportion of females who did not cheat.


```r
risk_model <- lm(cheated ~ lottery_a + smoke + alcohol + gamble + skydiving + speed, data=steak_survey)
tidy(risk_model)
=======
There was a statistically significant difference between the proportion of people who cheated and who didn't in the West North Central and Middle Atlantic showing these regions may have more cheaters whereas the Pacific had a smaller proportion of cheaters compared to non-cheaters.


```r
steak_survey %>% 
  ggplot()+
  geom_bar(aes(x=cheated, fill=female), position = "fill")
>>>>>>> 944725faf56428e1497ce5605bf3b9393a4a95ba
```

```
## # A tibble: 7 x 5
##   term          estimate std.error statistic p.value
##   <chr>            <dbl>     <dbl>     <dbl>   <dbl>
## 1 (Intercept)    0.160      0.0583     2.74  0.00637
## 2 lottery_aTRUE -0.00870    0.0333    -0.262 0.794  
## 3 smokeTRUE      0.0549     0.0464     1.18  0.238  
## 4 alcoholTRUE    0.0219     0.0412     0.532 0.595  
## 5 gambleTRUE    -0.00758    0.0348    -0.218 0.828  
## 6 skydivingTRUE  0.0847     0.0653     1.30  0.195  
## 7 speedTRUE     -0.0147     0.0549    -0.268 0.788
```

<<<<<<< HEAD
We took factors that correlated to risk such as smoking and gambling to see if these factors had any correlation to cheating. Sadly, the p-value for all the variables are greater than .05 meaning they are statistically insignificant.


```r
age_model <- lm(cheated ~ age, data=steak_survey)
tidy(age_model)
```

```
## # A tibble: 4 x 5
##   term        estimate std.error statistic  p.value
##   <chr>          <dbl>     <dbl>     <dbl>    <dbl>
## 1 (Intercept)   0.170     0.0167    10.2   2.67e-22
## 2 age.L        -0.0110    0.0342    -0.321 7.48e- 1
## 3 age.Q        -0.0739    0.0333    -2.22  2.71e- 2
## 4 age.C         0.0579    0.0325     1.79  7.48e- 2
=======
There was a larger proportion of females who did not cheat.


```r
risk_model <- glm(gamble ~ alcohol, data=steak_survey ,family = binomial(link = "logit"))
tidy(risk_model)
```

```
## # A tibble: 2 x 5
##   term        estimate std.error statistic     p.value
##   <chr>          <dbl>     <dbl>     <dbl>       <dbl>
## 1 (Intercept)   -0.992     0.204     -4.87 0.00000113 
## 2 alcoholTRUE    1.15      0.226      5.09 0.000000364
>>>>>>> 944725faf56428e1497ce5605bf3b9393a4a95ba
```

This model examines whether a person's age had any factor on determining whether a person cheated. This model shows that the youngest and oldest age groups showed the highest level of cheating comapred to middle aged people. The coefficients represents the average increase and decrease in probability that a certain age group had to cheat compared to the youngest age group.

<<<<<<< HEAD
For the variables whose p-value were less than .05, I computed the confidence intervals for the age.Q and age.C coefficient. For the age.Q coefficient, the confidence interval is -0.07392683	+ 2*0.03334453 and -0.07392683 - 2*0.03334453 or -0.00723777 and -0.1406159. This confidence interval is quite large considering the scope of the model. The age.C coefficient shows similar results as the confidence interval is between 0.122859 and -0.00696507. Although, there may be some correlation within the data, the sample size of the study combined with the low reliability of the model coefficient allows us to conclude that there is essentially no concrete factors that increase a person's likelyhood to cheat.

## Next Steps

Our next steps will be to find, using all the data we have gathered, a conclusion to our research question. This will likely include an explanation on how very little, if anything at all, that we have looked at impacts cheating at a statistically significant level.

We will also do some outside research to see if there are factors not included in the data that do affect cheating. If there are, we may try to explain them and expand upon them.


=======
```r
risk_model <- glm(gamble ~ speed, data=steak_survey ,family = binomial(link = "logit"))
tidy(risk_model)
```

```
## # A tibble: 2 x 5
##   term        estimate std.error statistic p.value
##   <chr>          <dbl>     <dbl>     <dbl>   <dbl>
## 1 (Intercept)   -0.719     0.280     -2.57  0.0102
## 2 speedTRUE      0.707     0.294      2.40  0.0164
```

We took factors that correlated to risk such as smoking and gambling to see if these factors had any correlation to cheating. Sadly, the p-value for all the variables are greater than .05 meaning they are statistically insignificant.


```r
age_model <- glm(gamble ~ female, data=steak_survey, family = binomial(link = "logit"))
tidy(age_model)
```

```
## # A tibble: 2 x 5
##   term        estimate std.error statistic p.value
##   <chr>          <dbl>     <dbl>     <dbl>   <dbl>
## 1 (Intercept)    0.155     0.128      1.21 0.225  
## 2 femaleTRUE    -0.467     0.179     -2.62 0.00887
```

This model examines whether a person's age had any factor on determining whether a person cheated. This model shows that the youngest and oldest age groups showed the highest level of cheating comapred to middle aged people. The coefficients represents the average increase and decrease in probability that a certain age group had to cheat compared to the youngest age group.

For the variables whose p-value were less than .05, I computed the confidence intervals for the age.Q and age.C coefficient. For the age.Q coefficient, the confidence interval is -0.07392683	+ 2*0.03334453 and -0.07392683 - 2*0.03334453 or -0.00723777 and -0.1406159. This confidence interval is quite large considering the scope of the model. The age.C coefficient shows similar results as the confidence interval is between 0.122859 and -0.00696507. Although, there may be some correlation within the data, the sample size of the study combined with the low reliability of the model coefficient allows us to conclude that there is essentially no concrete factors that increase a person's likelyhood to cheat.

## Next Steps

Our next steps will be to find, using all the data we have gathered, a conclusion to our research question. This will likely include an explanation on how very little, if anything at all, that we have looked at impacts cheating at a statistically significant level.

We will also do some outside research to see if there are factors not included in the data that do affect cheating. If there are, we may try to explain them and expand upon them.


>>>>>>> 944725faf56428e1497ce5605bf3b9393a4a95ba








