# Multivariable Statistics Update 10_6_2019

-----------

## Table of Contents

[Preparing Our Data](#preparing-our-data) 

[Creating A Baseline Model For Hapto.Log](#creating-a-baseline-model-for-hapto-log)

[Creating A Linear Regression Model for Hapto.Log By Removing One Variable At A Time](#creating-a-linear-regression-model-for-hapto-log-by-removing-one-variable-at-a-time)

[Creating A Baseline Model For Hapto0.35](#creating-a-baseline-model-for-hapto-035)

[Creating A Logistic Regression Model For Hapto0.35 By Removing One Variable At A Time](#creating-a-logistic-regression-model-for-hapto-035-by-removing-one-variable-at-a-time)

[k-means clustering](#k-means-clustering)

# Preparing Our Data
First we have to set our working directory and load in our dataset
```r
setwd("/Volumes/DODO12/Metalarm2019/MK_hapto_data/MS_hapto_project_UU/MSmink_reports_Rcode_hapto/MCS_report_UU2019")

load(file="MS_hp9_Log.RData")
```

Then let's access any packages we will be needing for the Multivariate Statistics 
(DD: I attach more libraries than strictly needed to have everything at hand, well organized MCS hates that....sorry Momo...)




```{r , echo=FALSE}
## if needed, there is  R code 
## to install several packages at once...

#install.packages("lmtest")
#install.packages("lmerTest")
#install.packages("psych")
#install.packages("lsmeans")

library(lme4)
library(nlme)
library(lmerTest)
library(lmtest)
library(lsmeans)
library(car)

#library(doBy)
#library(ggplot2)
#require(devtools)
#library(effects)
library(multcomp)
library(lattice)
library(psych)


#library(bnlearn)
library(rgl)
#library(scatterplot3d)
library(epitools)
library(Epi)
library(epiR)

#library(car)
#library(lme4)
library(fields)
library(MASS)
library(ggplot2)
library(corrgram)
library(boot)
#library(nlme)
library(reshape)
library(sandwich)
library(msm)
#library(gclus)
#library(cluster)
library(DataCombine)
library(plyr)
library(dplyr)
library(reshape2)
#library(sandwich)
#library(msm)
library(gclus)
library(cluster)
library(gmodels)
library(plotrix)

library(party)
#library(effects)
library(rpart)
library(lattice)
#library(RColorBrewer)
library(tidyr)
library(tidyverse)
library(tidyquant)
library(effects)
library(coefplot2)
#library(lodown)
#library(survey)
#library(srvyr)
#library(caret)
#library(DMwR)

#library(psych) 

#library(lattice)
library(data.table)
library(knitr)




##################################################################
#install.packages("MVPARTwrap")
library(vegan)
library(cluster)
library(ggplot2)
library(psych)#

library(devtools)
#install_github("vqv/ggbiplot")
library(ggbiplot)

#install_github("cran/mvpart")

#install.packages("agricolae")
library(agricolae)
library(multcomp)
library(epiR)

library(rgl)
library(ade4)
library(gclus)
library(RColorBrewer)
library(labdsv)
#library(mvpart) #
#library(MVPARTwrap) #
library(gridExtra)
library(reshape)
library(scales)
library(devtools)

library(car)
library(lme4)
library(lmerTest)

```

Now we are ready to begin creating our models.
# recall contents of data object hp9:

```{r , echo=FALSE}
glimpse(hp9)


Observations: 712
Variables: 72
# CowID                  <fct> 276000941090648, 276000951311013, 276000951311013, 276000947406879, 276000944234103, 2760…
# Cow.Birth.Date         <date> 2007-10-19, 2016-05-31, 2016-05-31, 2012-08-14, 2010-03-13, 2007-10-19, 2013-05-21, 2011…
# Farm.Name              <fct> Stadler, Stadler, Stadler, Stadler, Stadler, Stadler, Stadler, Stadler, Stadler, Stadler,…
# Farm.No                <fct> 14184137142, 14184137142, 14184137142, 14184137142, 14184137142, 14184137142, 14184137142…
# Cow.Breed              <fct> 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 0…
# Cow.Exit.Date          <date> NA, NA, NA, NA, NA, NA, NA, NA, 2018-09-10, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, …
# BS.DATE                <date> 2018-11-06, 2018-07-24, 2018-08-07, 2018-12-11, 2018-12-04, 2018-11-13, 2018-08-07, 2018…
$ BS.Month               <fct> 11-2018, 07-2018, 08-2018, 12-2018, 12-2018, 11-2018, 08-2018, 12-2018, 09-2018, 09-2018,…
$ BS.MS.Date.Difference  <dbl> 1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 1, 1, 0, 1, 1, 1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 1,…
$ BS.DIM                 <dbl> 21, 15, 29, 16, 16, 28, 11, 22, 6, 13, 13, 10, 17, 15, 20, 28, 10, 17, 16, 23, 19, 26, 25…
$ Hapto.Result           <dbl> 597.50, 280.00, 741.50, 280.00, 1903.50, 11584.50, 3850.00, 280.00, 12764.00, 4791.00, 38…
$ Hapto.Log              <dbl> 6.392754, 5.634790, 6.608675, 5.634790, 7.551450, 9.357423, 8.255828, 5.634790, 9.454384,…
$ Hapto.0.1              <fct> 0, 0, 0, 0, 1, 1, 1, 0, 1, 1, 0, 1, 1, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 1, 1, 1,…
$ Hapto0.35              <fct> 0, 0, 0, 0, 0, 1, 1, 0, 1, 1, 0, 1, 1, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 1, 0, 1,…
$ Hapto.HML              <fct> 0, 0, 0, 0, 0, 1, 0, 0, 1, 1, 0, 0, 2, 0, 0, 0, 0, 0, 0, 0, 2, 0, 0, 0, 0, 0, 0, 2, 0, 1,…
$ Hapto.HL               <fct> 1, 1, 1, 1, 1, NA, 1, 1, NA, NA, 1, 1, 3, 1, 1, 1, 1, 1, 1, 1, 3, 1, 1, 1, 1, 1, 1, 3, 1,…
$ BS.NEFA                <dbl> 0.23, 0.68, 0.48, 0.32, 0.33, 0.22, 0.50, 0.47, 0.63, 0.83, 2.08, 0.36, 0.55, 0.32, 0.50,…
$ BS.BHBA                <dbl> 1.35, 1.49, 1.78, 1.46, 1.26, 0.98, 0.71, 1.28, 1.32, 0.76, 1.40, 0.61, 0.78, 0.66, 1.80,…
$ MS.Date.Taken          <date> 2018-11-05, 2018-07-23, 2018-08-07, 2018-12-10, 2018-12-03, 2018-11-12, 2018-08-07, 2018…
$ MS.Time.Taken          <chr> "06:42:00", "12:00:00", "12:00:00", "01:04:00", "10:29:00", "17:30:00", "00:00:00", "08:1…
$ Calving.Date           <date> 2018-10-16, 2018-07-09, 2018-07-09, 2018-11-25, 2018-11-18, 2018-10-16, 2018-07-27, 2018…
$ Calving.No             <dbl> 9, 1, 1, 5, 7, 9, 4, 6, 2, 5, 1, 1, 1, 6, 1, 1, 2, 2, 1, 7, 1, 1, 1, 4, 4, 4, 1, 6, 1, 5,…
$ Hfr.or.Cow             <fct> cow, hfr, hfr, cow, cow, cow, cow, cow, cow, cow, hfr, hfr, hfr, cow, hfr, hfr, cow, cow,…
$ MS.DIM                 <dbl> 20, 14, 29, 15, 15, 27, 11, 21, 5, 12, 12, 9, 17, 14, 19, 27, 9, 17, 15, 22, 18, 26, 24, …
$ MS.Date.Analyzed       <date> 2018-11-07, 2018-07-26, 2018-08-08, 2018-12-13, 2018-12-10, 2018-11-15, 2018-08-08, 2018…
$ Milk.Yield             <dbl> 39.9, 23.3, NA, 41.6, 30.4, 41.6, NA, 40.8, 36.8, 34.6, 21.7, NA, 23.7, 37.8, 19.1, 29.0,…
$ MS.Milk.Yield          <dbl> 21.2, 23.3, 14.9, 20.7, 11.9, 17.0, 12.5, 11.4, 36.8, 12.8, 10.9, 19.7, 10.9, 9.8, 8.1, 1…
$ MS.Fat                 <dbl> 4.32, 4.70, 4.21, 6.12, 5.04, 5.61, 3.82, 4.00, 5.70, 4.44, 7.02, 9.14, 3.61, 5.07, 5.70,…
$ MS.Protein             <dbl> 2.79, 3.05, 2.85, 3.42, 2.89, 2.76, 3.30, 3.70, 2.86, 3.37, 3.32, 3.08, 2.99, 3.59, 3.05,…
$ MS.S.Cell.Count        <dbl> 16, 298, 231, 21, 10, 21, 19, 10, 249, 66, 103, 241, 41, 19, 538, 249, 49, 47, 31, 10, 10…
$ MS.Lactose             <dbl> 4.73, 4.86, 4.97, 4.82, 4.81, 4.80, 4.83, 4.81, 4.82, 4.85, 4.71, 4.61, 5.05, 4.82, 4.71,…
$ MS.Urea                <dbl> 24.4, 52.2, 26.0, 28.1, 20.0, 30.0, 16.5, 32.0, 36.6, 18.1, 37.6, 32.4, 21.7, 26.6, 32.2,…
$ MS.pH                  <dbl> 6.64, 6.65, 6.68, 6.66, 6.66, 6.64, 6.70, 6.67, 6.67, 6.62, 6.47, 6.46, 6.69, 6.64, 6.57,…
$ MS.Acetone             <dbl> 10, 140, 140, 170, 120, 60, 90, NA, 270, 60, 350, 240, 150, 20, 220, 80, 50, NA, 110, 50,…
$ MS.BHBA                <dbl> 20, 90, 90, 170, 90, 70, 50, 10, 170, 40, 190, 90, 80, 40, 140, 60, 110, 110, 80, 70, 110…
$ MS.NEFA                <dbl> 6.30, 9.90, 8.00, 4.90, 4.00, 5.20, 6.60, 3.20, 7.80, 6.20, 1.01, 1.18, NA, 1.39, 7.80, 3…
$ MS.NSFA                <dbl> 14.2, 19.6, 15.9, 22.9, 19.9, 20.1, 15.7, 11.6, 25.0, 15.4, 32.9, 31.9, 11.9, 15.1, 25.7,…
$ MS.MFA                 <dbl> 1.142, 1.653, 1.319, 1.878, 1.657, 1.641, 1.288, 0.873, 2.056, 1.247, 2.890, 2.703, NA, 1…
$ MS.PFA                 <dbl> 0.144, 0.194, 0.137, 0.207, 0.182, 0.193, 0.124, 0.137, 0.209, 0.164, 0.288, 0.303, NA, 0…
$ MS.SFA                 <dbl> 2.653, 2.569, 2.435, 3.726, 2.868, 3.375, 2.090, 2.640, 3.147, 2.689, 3.635, 5.865, NA, 3…
$ MS.Palmeic             <dbl> 1.172, 1.094, 1.115, 1.422, 1.235, 1.410, 0.885, 1.076, 1.190, 0.924, 1.445, 2.525, NA, 1…
$ MS.Stearine            <dbl> 0.471, 0.653, 0.534, 0.735, 0.637, 0.636, 0.437, 0.368, 0.742, 0.517, 0.947, 1.021, NA, 0…
$ MS.Oleic               <dbl> 1.061, 1.596, 1.199, 1.802, 1.534, 1.582, 1.199, 0.805, 2.001, 1.169, 2.755, 2.582, NA, 1…
$ CE.Date                <date> 2018-11-06, 2018-07-24, 2018-08-07, 2018-12-11, 2018-12-04, 2018-11-13, 2018-08-07, 2018…
$ CE.Temp                <dbl> 38.2, 38.7, 38.4, 38.2, 38.5, 38.0, 38.1, 38.9, 38.2, 38.8, 39.0, 38.3, 38.7, 38.9, 39.1,…
$ CE.Environ.Temp        <dbl> 8.0, 19.3, 22.4, 3.9, 11.9, 6.0, 22.4, 3.9, 16.3, 17.8, 11.1, 20.0, 17.0, 12.1, 4.3, 4.3,…
$ CE.Fat.Level           <dbl> 12, 19, 12, 16, 13, 12, 19, 20, 17, 35, 27, 24, 23, 24, 21, 21, 13, 20, 16, 10, 20, 19, 1…
$ CE.Skin.Dehydration    <fct> phy, phy, phy, phy, phy, phy, phy, phy, phy, phy, phy, phy, phy, phy, phy, phy, phy, phy,…
$ CE.Stom.Tension        <fct> phy, phy, phy, phy, phy, phy, phy, phy, phy, phy, phy, phy, phy, phy, phy, phy, phy, phy,…
$ CE.Stom.Layering       <fct> 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1,…
$ CE.Stom.Fluid.Movement <fct> obb, obb, obb, obb, obb, obb, obb, obb, obb, obb, obb, obb, obb, NA, obb, obb, obb, obb, …
$ CE.Stom.Ping           <fct> obb, obb, obb, obb, obb, obb, obb, obb, obb, obb, obb, obb, obb, obb, obb, obb, obb, obb,…
$ CE.Stom.Fullness       <fct> norm, abnorm, abnorm, abnorm, abnorm, norm, norm, norm, norm, abnorm, abnorm, abnorm, nor…
$ CE.Stom.Noise.Freq     <fct> NA, NA, NA, NA, NA, NA, NA, NA, bis_2, NA, NA, NA, NA, NA, NA, phy, NA, NA, NA, NA, phy, …
$ CE.Waste.Consistency   <fct> norm, norm, norm, norm, norm, norm, norm, norm, thick, norm, norm, norm, norm, norm, norm…
$ CE.Waste.Digestion     <fct> maess, gut, gut, maess, gut, maess, gut, gut, gut, gut, gut, gut, gut, gut, gut, gut, gut…
$ CE.Locomotion.Score    <fct> 3, 1, 1, 2, 1, 3, 2, 2, 3, 2, 1, 1, 2, 1, 2, 2, 3, 2, 2, 2, 4, 2, 1, 2, 1, 1, 1, 3, 1, 2,…
$ CE.Lame                <fct> 1, 0, 0, 0, 0, 1, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 1, 0, 0,…
$ BS.NEFA.Log            <dbl> -1.4696760, -0.3856625, -0.7339692, -1.1394343, -1.1086626, -1.5141277, -0.6931472, -0.75…
$ BS.BHBA.Log            <dbl> 0.30010459, 0.39877612, 0.57661336, 0.37843644, 0.23111172, -0.02020271, -0.34249031, 0.2…
$ MS.S.Cell.Count.Log    <dbl> 2.772589, 5.697093, 5.442418, 3.044522, 2.302585, 3.044522, 2.944439, 2.302585, 5.517453,…
$ MS.BHBA.Log            <dbl> 2.995732, 4.499810, 4.499810, 5.135798, 4.499810, 4.248495, 3.912023, 2.302585, 5.135798,…
$ MS.Acetone.Log         <dbl> 2.302585, 4.941642, 4.941642, 5.135798, 4.787492, 4.094345, 4.499810, NA, 5.598422, 4.094…
$ BS.NEFA.0.7            <fct> 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 1, 0, 0, 1, 0, 0, 1, 0, 1,…
$ BS.BHBA.1.2            <fct> 1, 1, 1, 1, 1, 0, 0, 1, 1, 0, 1, 0, 0, 0, 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0,…
$ Hapto0.35.2            <fct> 0, 0, 0, 0, 0, 1, 1, 0, 1, 1, 0, 1, 1, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 1, 0, 1,…
$ BS.Month2              <fct> 11-2018, 07-2018, 08-2018, 12-2018, 12-2018, 11-2018, 08-2018, 12-2018, 09-2018, 09-2018,…
$ BS.Month_warm          <fct> 0, 1, 1, 0, 0, 0, 1, 0, 1, 1, 0, 1, 1, 0, 0, 0, 1, 1, 1, 0, 1, 1, 1, 1, 1, 1, 0, 0, 1, 1,…
$ CE.Stom.Fullness01     <fct> 0, 1, 1, 1, 1, 0, 0, 0, 0, 1, 1, 1, 0, 0, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 0, 1, 0, 1, 1,…
$ CE.Stom.Tension01      <fct> 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,…
$ clusterHapto5          <int> 1, 2, 2, 4, 2, 1, 3, 4, 1, 3, 3, 3, 2, 4, 4, 2, 4, 4, 2, 2, 1, 2, 2, 2, 3, 3, 4, 1, 2, 3,…
$ clusterHapto           <int> 2, 2, 2, 3, 2, 1, 2, 3, 1, 2, 2, 2, 2, 3, 3, 2, 3, 3, 2, 2, 1, 2, 2, 2, 2, 3, 3, 1, 2, 2,…
```


Explore Hapto_BS.Month and Month of sampling and warm (months 7, 8, 9) vs cooler months (months: 10, 11, 12, and 6) for effect on Hapto.Log
```{r , echo=FALSE}

# recall the month of sampling variable associated with Hapto.log:
Hapto_BS.Month <- lm(Hapto.Log ~ BS.Month, hp9)
summary(Hapto_BS.Month)

#Coefficients:
#                Estimate Std. Error t value Pr(>|t|)    
#(Intercept)       6.3227     0.3127  20.219  < 2e-16 ***
#BS.Month07-2018   1.3364     0.4050   3.300  0.00102 ** 
#BS.Month08-2018   1.8506     0.3805   4.863 1.43e-06 ***
#BS.Month09-2018   1.6428     0.4106   4.001 6.97e-05 ***
#BS.Month10-2018   0.8946     0.3778   2.368  0.01816 *  
#BS.Month11-2018   0.6158     0.3787   1.626  0.10439    
#BS.Month12-2018   0.4510     0.4372   1.032  0.30264    




plot(allEffects(Hapto_BS.Month))
coefplot2(Hapto_BS.Month)


# we have generated a
#binary month variable for warm (=1) vs cooler months (=0)
#table(hp9$BS.Month_warm)
#  0   1 
#401 311

Hapto_BS.Month2 <- lm(Hapto.Log ~ BS.Month_warm, hp9)
summary(Hapto_BS.Month2)

#Coefficients:
#               Estimate Std. Error t value Pr(>|t|)    
#(Intercept)      6.9099     0.1242  55.624  < 2e-16 ***
#BS.Month_warm1   1.0515     0.1880   5.594 3.16e-08 ***
#---
#Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1



plot(allEffects(Hapto_BS.Month2))
#coefplot2(Hapto_BS.Month2)

```

# Now towards the full model for Hapto.log, but first:

# Creating A Baseline Model For Hapto.Log

First we want to create a baseline model with no additional variables besides the variables that can counter-act the nesting effects, in this case CowID and Farm.No

baselineLM <- lmer(Hapto.Log ~ 1 + (1|CowID:Farm.No), data = hp9)

```{r , echo=FALSE}
baselineLM <- lmer(Hapto.Log ~ 1 + (1|CowID:Farm.No), data = hp9)

plot(baselineLM)
```

<img src="https://user-images.githubusercontent.com/52465712/62807608-5ccb7880-babb-11e9-998e-eb729681624e.png" width="300">


# Creating A Linear Regression Model for Hapto.Log By Removing One Variable At A Time
# Creating a Linear Regression Model For Hapto.Log using backward step elimination (removing one variable at a time based on highest P-value)

Now we take our baseline model for Hapto.Log and add all the variables that had a p-value below 0.1 in the bi-variate analysis and didn't have a correlation above 0.7.

Start:  full model for linear regression
Note: deleted Milk.Yield, because too many missing values (325 mv)

The full model equation is:

note: the random effect for farm and CowID corrects for repeated sampling per farm and CowID


```{r , echo=FALSE}


#deleted Milk.Yield, because too many missing values (325 mv)

Hapto.Log_10 <- lmer(Hapto.Log ~  MS.Milk.Yield + MS.NEFA + MS.DIM + MS.Fat +
                    MS.Protein + MS.Lactose + MS.Acetone.Log + MS.Urea + MS.S.Cell.Count.Log +
                    MS.pH + CE.Environ.Temp + Hfr.or.Cow + BS.Month_warm + CE.Skin.Dehydration +
                    CE.Stom.Tension01 + CE.Stom.Layering + CE.Stom.Fullness01 + CE.Stom.Noise.Freq +
                    CE.Waste.Consistency + CE.Lame + BS.NEFA.0.7 + BS.BHBA + BS.NEFA.0.7*BS.BHBA + MS.Milk.Yield*BS.BHBA + Cow.Breed + (1|CowID:Farm.No), data = hp9)
#summary(Hapto.Log_10)
#??Anova
#Anova(Hapto.Log_10, type = "III")
```
Now we run a test to see which variable is the least significant

Analysis of Deviance Table (Type III Wald chisquare tests)

```{r , echo=FALSE}
Anova(Hapto.Log_10, type = "III")


#MS.NEFA                0.4721  1  0.4920337    
#MS.DIM                 0.5416  1  0.4617607    
#MS.Fat                 1.4057  1  0.2357791    
#MS.Protein            10.5874  1  0.0011386 ** 
#MS.Lactose             2.9903  1  0.0837655 .  
#MS.Acetone.Log         0.3383  1  0.5608100    
#MS.Urea                2.8482  1  0.0914773 .  
#MS.S.Cell.Count.Log   16.0056  1  6.316e-05 ***
#MS.pH                  0.0006  1  0.9798728    
#CE.Environ.Temp        0.0992  1  0.7527752    
#Hfr.or.Cow             3.1194  1  0.0773656 .  
#BS.Month_warm          2.2656  1  0.1322752    
#CE.Skin.Dehydration    0.3119  1  0.5765167    
#CE.Stom.Tension01      1.3232  1  0.2500136    
#CE.Stom.Layering       0.1856  1  0.6665866    
#CE.Stom.Fullness01     0.3702  1  0.5429081    
#CE.Stom.Noise.Freq     2.0099  2  0.3660696    
#CE.Waste.Consistency   1.4452  3  0.6949762    
#CE.Lame               11.6515  1  0.0006415 ***
#BS.NEFA.0.7            0.4927  1  0.4827087    
#BS.BHBA                2.3703  1  0.1236604    
#Cow.Breed              0.5619  1  0.4535058    
#BS.NEFA.0.7:BS.BHBA    0.0239  1  0.8770401    
#MS.Milk.Yield:BS.BHBA  0.3536  1  0.5520542    
#---
#Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

```



Backward step elimination leads to the final model:

After doing this 11 times we have a final model where all of our p-values are significant:

                     
                     
```{r , echo=FALSE}



Hapto.Log_11 <- lmer(Hapto.Log ~  MS.Milk.Yield    +
                    MS.Protein + MS.Lactose + MS.S.Cell.Count.Log +
                     Hfr.or.Cow + BS.Month_warm  +
                    CE.Stom.Tension01  + CE.Stom.Fullness01 +
                     CE.Lame + BS.NEFA.0.7     + (1|CowID:Farm.No), data = hp9)
summary(Hapto.Log_11)

#Linear mixed model fit by REML. t-tests use Satterthwaite's method ['lmerModLmerTest']
#Formula: Hapto.Log ~ MS.Milk.Yield + MS.Protein + MS.Lactose + MS.S.Cell.Count.Log +  
#    Hfr.or.Cow + BS.Month_warm + CE.Stom.Tension01 + CE.Stom.Fullness01 +      CE.Lame + BS.NEFA.0.7 + (1 | CowID:Farm.No)
 #  Data: hp9

#REML criterion at convergence: 3133.7

#Scaled residuals: 
#    Min      1Q  Median      3Q     Max 
#-1.7468 -0.5993 -0.2304  0.4390  3.2446 

#Random effects:
# Groups        Name        Variance Std.Dev.
# CowID:Farm.No (Intercept) 0.6406   0.8004  
# Residual                  4.1093   2.0271  
# Number of obs: 712, groups:  CowID:Farm.No, 423


# Fixed effects:
#                     Estimate Std. Error        df t value Pr(>|t|)    
#(Intercept)          12.16543    2.90897 579.30000   4.182 3.34e-05 ***
#MS.Milk.Yield        -0.03940    0.01437 655.30000  -2.741  0.00629 ** 
#MS.Protein           -0.62638    0.28879 638.50000  -2.169  0.03045 *  
#MS.Lactose           -1.01367    0.49800 576.20000  -2.035  0.04226 *  
#MS.S.Cell.Count.Log   0.48289    0.06990 561.00000   6.908 1.33e-11 ***
#Hfr.or.Cowhfr         0.81732    0.20284 396.10000   4.029 6.71e-05 ***
#BS.Month_warm1        0.93144    0.17766 469.40000   5.243 2.40e-07 ***
#CE.Stom.Tension011    0.99395    0.32674 696.70000   3.042  0.00244 ** 
#CE.Stom.Fullness011  -0.58044    0.17424 699.90000  -3.331  0.00091 ***
#CE.Lame1              1.23968    0.26958 646.90000   4.599 5.12e-06 ***
#BS.NEFA.0.71          1.02456    0.22097 663.70000   4.637 4.27e-06 ***
#---
#Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1


coefplot2(Hapto.Log_11)

#plot(Hapto.Log_11)
#??Anova
#Anova(Hapto.Log_11, type = "III")

```


So the variables in our final model are: 
MS.Milk.Yield, MS.Protein, MS.Lactose, MS.S.Cell.Count.Log, Hfr.or.Cow, BS.Month_warm, CE.Stom.Tension01, CE.Stom.Fullness01, CE.Lame, and BS.NEFA.0.7.



And here is our model plotted
```{r , echo=FALSE}
plot(Hapto.Log_11)
```

<img src="https://user-images.githubusercontent.com/52465712/62807606-5b01b500-babb-11e9-9acc-095169cec723.png" width="300">

Note: there is at least one linear pattern left in the residual over fitted plot. Compared to the baseline model, we extracted significant amounts of variance from the data,
but there is still at least one statsitically significant linear association unexplored for which we seem to not have the correct predictor variable in the model.



# Creating A Logistic Regression Model For Hapto0.35 By Removing One Variable At A Time
# Repeat multiple variable analysis as logitic regression model
# Logistic regression model for Hapto0.35 as outcome variable

--------
# Creating a Baseline Model for Hapto 0.35 
and residual over fitted plot

baselineLM2 <- glmer(Hapto0.35 ~ 1 + (1|CowID:Farm.No), data = hp9, family = binomial(link=logit))


First we want to create a baseline model with no additional variables besides the variables that can counter-act the nesting effects, in this case CowID and Farm.No
```{r , echo=FALSE}
baselineLM2 <- glmer(Hapto0.35 ~ 1 + (1|CowID:Farm.No), data = hp9, family = binomial(link=logit))

plot(baselineLM2)
```

<img src="https://user-images.githubusercontent.com/52465712/63232326-702dc080-c1ec-11e9-880d-ab18d6c9835d.png" width="300">


-----------
# Creating A Logistic Regression Model For Hapto0.35 By Removing One Variable At A Time

Now we take our baseline model for Hapto.0.35 and add all the variables that had a p-value below 0.1 in the bi-variate analysis and didn't have a correlation above 0.7.
note: such a model is too complex for this data set and does not converge, therefore, we use the final variables from the linear regression and add the interaction terms
for BS.NEFA.0.7*BS.BHBA + MS.Milk.Yield*BS.BHBA
we even tried BREED again to start the full model, just in case...
The full model equation is: 

               

```{r , echo=FALSE}
Hapto0.35_1 <- glmer(data = hp9, Hapto0.35 ~ MS.Milk.Yield    +
                    MS.Protein + MS.Lactose + MS.S.Cell.Count.Log +
                     Hfr.or.Cow + BS.Month_warm  +
                    CE.Stom.Tension01  + CE.Stom.Fullness01 +
                     CE.Lame + BS.NEFA.0.7 + BS.BHBA + BS.NEFA.0.7*BS.BHBA + MS.Milk.Yield*BS.BHBA + Cow.Breed + (1|CowID:Farm.No), family = binomial(link = logit))


```

Now we run a test to see which variable is the least significant
```{r , echo=FALSE}
Anova(Hapto0.35_1, type = "III")

#Analysis of Deviance Table (Type III Wald chisquare tests)

#Response: Hapto0.35
#                        Chisq Df Pr(>Chisq)    
#(Intercept)            3.1087  1  0.0778769 .  
#MS.Milk.Yield          3.8832  1  0.0487702 *  
#MS.Protein             4.7692  1  0.0289725 *  
#MS.Lactose             4.9091  1  0.0267151 *  
#MS.S.Cell.Count.Log   28.9220  1  7.535e-08 ***
#Hfr.or.Cow            13.0386  1  0.0003051 ***
#BS.Month_warm         17.2175  1  3.333e-05 ***
#CE.Stom.Tension01      1.9694  1  0.1605159    
#CE.Stom.Fullness01     5.6488  1  0.0174669 *  
#CE.Lame               19.5448  1  9.827e-06 ***
#BS.NEFA.0.7            3.2664  1  0.0707146 .  
#BS.BHBA                2.6291  1  0.1049209    
#Cow.Breed              0.0276  1  0.8680106    
#BS.NEFA.0.7:BS.BHBA    0.1927  1  0.6606496    
#MS.Milk.Yield:BS.BHBA  1.5816  1  0.2085366    
#---
#Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1



```



need to use backward step elimiination to generate final model:

Backward step elimination results in the final model where all of the p-values are <0.05, except for MS.Milk.Yield (p<0.11) :
final model equation is:


                     
```{r , echo=FALSE}

Hapto0.35_10 <- glmer(data = hp9, Hapto0.35 ~ MS.Milk.Yield  +
                    MS.Protein + MS.Lactose  + MS.S.Cell.Count.Log +
                    Hfr.or.Cow + BS.Month_warm  +
                     CE.Stom.Fullness01 + CE.Lame + BS.NEFA.0.7 + BS.BHBA.Log   + (1|CowID:Farm.No), family = binomial(link = logit))

summary(Hapto0.35_10)

#                     Estimate Std. Error        df t value Pr(>|t|)    
#(Intercept)          5.75753    3.35422   1.717 0.086070 .  
#MS.Milk.Yield       -0.02844    0.01778  -1.600 0.109666    
#MS.Protein          -0.81294    0.35211  -2.309 0.020958 *  
#MS.Lactose          -1.35465    0.56911  -2.380 0.017299 *  
#MS.S.Cell.Count.Log  0.42946    0.07857   5.466 4.60e-08 ***
#Hfr.or.Cowhfr        0.79757    0.22130   3.604 0.000313 ***
#BS.Month_warm1       0.78677    0.19851   3.963 7.39e-05 ***
#CE.Stom.Fullness011 -0.48396    0.20598  -2.350 0.018797 *  
#CE.Lame1             1.28389    0.27720   4.632 3.63e-06 ***
#BS.NEFA.0.71         0.91805    0.23945   3.834 0.000126 ***
#BS.BHBA.Log         -0.50264    0.21676  -2.319 0.020401 *  
#---
#Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1


coefplot2(Hapto0.35_10)
#plot(allEffects(Hapto0.35_10))

plot(Hapto0.35_10)

#Anova(Hapto0.35_10, type = "III")


```

The final variables in the logistic regression model are:
MS.Milk.Yield, MS.Protein, MS.Lactose, MS.S.Cell.Count.Log, Hfr.or.Cow, BS.Month_warm, CE.Stom.Fullness01, CE.Lame, BS.NEFA.0.7, BS.BHBA.Log.  

And here is our model plotted
```r
plot(Hapto0.35_10)
```

<img src="https://user-images.githubusercontent.com/52465712/63232283-06151b80-c1ec-11e9-9ff1-a1cb374b11d2.png" width="300">

# the downward trend in the residual over fitted plot is a commonly seen pattern implying that not all variance in the data set has been extracted by the model.

# This concludes the multiple variable regression analysis.



# k-means clustering to re-evaluate the cut-off value for Haptoglobin will follow
# k-means-clustering

# this R code is too complex to show here, right now. Discuss outcomes first.
