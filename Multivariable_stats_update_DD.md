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
```


Explore Hapto_BS.Month and Month of sampling and warm (months 7, 8, 9) vs cooler months (months: 10, 11, 12, and 6) for effect on Hapto.Log
```{r , echo=FALSE}

# recall the month of sampling variable associated with Hapto.log:
Hapto_BS.Month <- lm(Hapto.Log ~ BS.Month, hp9)
summary(Hapto_BS.Month)

plot(allEffects(Hapto_BS.Month))
coefplot2(Hapto_BS.Month)

# we have generated a
#binary month variable for warm (=1) vs cooler months (=0)
#table(hp9$BS.Month_warm)
#  0   1 
#401 311

Hapto_BS.Month2 <- lm(Hapto.Log ~ BS.Month_warm, hp9)
summary(Hapto_BS.Month2)

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
Anova(Hapto.Log_10, type = "III")
```
Now we run a test to see which variable is the least significant

Analysis of Deviance Table (Type III Wald chisquare tests)

```{r , echo=FALSE}
Anova(Hapto.Log_10, type = "III")



```



Backward step elimination leads to the final model:
```{r , echo=FALSE}


Anova(Hapto.Log_11, type = "III")


```

After doing this 11 times we have a final model where all of our p-values are significant:

                     
                     
```{r , echo=FALSE}



Hapto.Log_11 <- lmer(Hapto.Log ~  MS.Milk.Yield    +
                    MS.Protein + MS.Lactose + MS.S.Cell.Count.Log +
                     Hfr.or.Cow + BS.Month_warm  +
                    CE.Stom.Tension01  + CE.Stom.Fullness01 +
                     CE.Lame + BS.NEFA.0.7     + (1|CowID:Farm.No), data = hp9)
summary(Hapto.Log_11)
coefplot2(Hapto.Log_11)

#plot(Hapto.Log_11)
#??Anova
Anova(Hapto.Log_11, type = "III")

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

#Response: Hapto0.35

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
coefplot2(Hapto0.35_10)
#plot(allEffects(Hapto0.35_10))

plot(Hapto0.35_10)
#??Anova
Anova(Hapto0.35_10, type = "III")
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


