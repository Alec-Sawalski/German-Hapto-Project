# Bi-Variate Statistics

--------------
## Table of Contents  

[Bi-Variate Statistics - Comparing Numeric Variables to Hapto.Log](#bi-variate-statistics---comparing-numerical-variables-to-hapto-log) 

[Bi-Variate Statistics - Comparing Factor Variables to Hapto.Log](#bi-variate-statistics---comparing-factor-variables-to-hapto-log) 

[Bi-Variate Statistics - Comparing Numeric Variables to Hapto0.35](#bi-variate-statistics---comparing-hapto-035-to-numeric-variables) 

[Bi-Variate Statistics - Comparing Factor Variables to Hapto0.35](#bi-variate-statistics---comparing-hapto-035-to-factor-variables) 


------------------
## Bi Variate Statistics - Comparing Numerical Variables to Hapto Log

Now we will test the associations between Hapto.Log and factor variables with Linear Regression Tests

For running all our linear regression tests below:
H0: beta1 = 0 (no association/no slope between the two variables)
Ha: beta1 notequal 0 (some association/slope between the two variables)
a = 0.05

Our p-value represents the probability of getting a beta1 that matches the one found in our study, purely by chance. 
If this p-value is below 0.05, this is statistically significant and provides convincing evidence against H0.
So we reject H0. There is an association/slope between the two variables
If this p-value is above 0.05, this is not statistically significant and does not provide convincing evidence against H0.
So we fail to reject H0. There is no convincing evidence that there is an association/slope between the two variables.




#### Log.Hapto ~ BS.NEFA.Log - Testing how the NEFA levels in the blood sample affected the cow's hapto level
```r

#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)   8.2155     0.1557  52.765  < 2e-16 ***
#  BS.NEFA.Log   0.7664     0.1135   6.751 3.06e-11 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically significant
- As a cow's blood nefa levels increase so does that cow's hapto levels.

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815985-fcce7300-a198-11e9-8a96-8bcd867b35bc.png" width="300">


#### Log.Hapto ~ BS.BHBA.Log - Testing how the BHBA levels in the blood sample affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)  7.38029    0.10503   70.27   <2e-16 ***
#  BS.BHBA.Log  0.04902    0.19583    0.25    0.802    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60816039-196aab00-a199-11e9-878e-c727aa8395b7.png" width="300">


#### Log.Hapto ~ BS.DIM - Testing how the days in milk at the blood sample affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)  8.38587    0.30745  27.276  < 2e-16 ***
#  BS.DIM      -0.05206    0.01498  -3.475 0.000542 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- As the days in milk increase the blood sample is likely to yield less hapto amounts.

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815851-c7298a00-a198-11e9-8afd-908e4b5ac483.png" width="300">


#### Log.Hapto ~ BS.MS.Date.Difference - Testing how the difference in the number of days between the milk and blood sample affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)             7.4825     0.1301  57.505   <2e-16 ***
#  BS.MS.Date.Difference  -0.2042     0.1600  -1.277    0.202    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815908-dc9eb400-a198-11e9-9593-86b44574586d.png" width="300">


#### Log.Hapto ~ Calving No. - Testing how the the number of calves the cow has had affected the cow's hapto level
```r
#Coefficients:
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)  7.46820    0.17354  43.035   <2e-16 ***
#  Calving.No  -0.03252    0.04767  -0.682    0.495    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60816005-0952cb80-a199-11e9-80aa-9ad069452fe3.png" width="300">


#### Log.Hapto ~ Milk.Yield - Testing how the average milk yield affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept) 10.10279    0.53993  18.711  < 2e-16 ***
#  Milk.Yield  -0.08538    0.01632  -5.231 2.77e-07 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- As the average milk yield of the cow increases the hapto level of that cow decreases.

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815676-6bf79780-a198-11e9-842a-2b0c8501baa1.png" width="300">


#### Log.Hapto ~ MS.Milk.Yield - Testing how the milk yield of the milk sample affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)    8.15504    0.25193  32.370  < 2e-16 ***
#  MS.Milk.Yield -0.05268    0.01566  -3.365 0.000807 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- As the amount of milk in the milk sample taken increases the hapto level is expected to decrease.

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815766-9ba69f80-a198-11e9-9764-e24d8f95c82b.png" width="300">


#### Log.Hapto ~ MS.NEFA - Testing how the NEFA levels in the milk sample affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)  6.96337    0.21669  32.135   <2e-16 ***
#  MS.NEFA      0.07617    0.03855   1.976   0.0487 *  
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- As the cow's milk nefa levels increase so does that cow's hapto levels.

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815441-f2f84000-a197-11e9-8e86-f1a6b1d1f779.png" width="300">


#### Log.Hapto ~ MS.BHBA.Log - Testing how the BHBA levels of the milk sample affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)   4.9451     0.5766   8.576  < 2e-16 ***
#  MS.BHBA.Log   0.6116     0.1390   4.400 1.28e-05 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- As a cow's milk bhba levels increase so does that cow's hapto levels

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815780-a4977100-a198-11e9-8357-13f56f53d9ec.png" width="300">


#### Log.Hapto ~ MS.DIM - Testing how days in milk before the milk sample affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)  8.33032    0.30081  27.693  < 2e-16 ***
#  MS.DIM      -0.05066    0.01505  -3.365 0.000805 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- As a cow's days in milk increases the hapto levels are expected to decrease.

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815731-89c4fc80-a198-11e9-94d3-bf92a4659ccd.png" width="300">


#### Log.Hapto ~ MS.Fat - Testing how the fat content of the milk sample affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)  5.28572    0.39337  13.437  < 2e-16 ***
#  MS.Fat       0.46403    0.08511   5.452 6.87e-08 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- As a cow's fat level increases the hapto level is also expected to increase.

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815753-947f9180-a198-11e9-833b-796042ed194d.png" width="300">


#### Log.Hapto ~ MS.Protein - Testing how the protein content of the milk sample affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)  10.5779     0.9853  10.736  < 2e-16 ***
#  MS.Protein   -0.9772     0.2987  -3.272  0.00112 ** 
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- As a cow's milk protein levels increase the cow's hapto levels are expected to decrease.

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815537-28049280-a198-11e9-8cb2-48ea3187982d.png" width="300">


#### Log.Hapto ~ MS.Lactose - Testing how the lactose content of the milk sample affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)  16.5239     2.3679   6.978 6.87e-12 ***
#  MS.Lactose   -1.8963     0.4901  -3.869 0.000119 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- As a cow's milk lactose levels increase the cow's hapto levels are expected to decrease.

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815834-bbd65e80-a198-11e9-8574-2e47227b45b5.png" width="300">


#### Log.Hapto ~ MS.Acetone.Log - Testing how the acetone content of the milk sample affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)      4.5150     0.5523   8.174 2.30e-15 ***
#  MS.Acetone.Log   0.6873     0.1209   5.686 2.18e-08 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- As a cow's milk acetone levels increase the hapto level is also expected to increase.

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815703-7b76e080-a198-11e9-8e6b-6a5e2e727b93.png" width="300">


#### Log.Hapto ~ MS.Urea - Testing how the urea content of the milk sample affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)  6.77381    0.31938  21.209   <2e-16 ***
#  MS.Urea      0.02386    0.01222   1.953   0.0513 .  
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815652-61d59900-a198-11e9-8c45-9cc3f276a7c4.png" width="300">


#### Log.Hapto ~ MS.S.Cell.Count.Log - Testing how the somatic cell count of the milk sample affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)          4.92404    0.30561   16.11  < 2e-16 ***
#  MS.S.Cell.Count.Log  0.58484    0.06979    8.38 2.83e-16 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- As a cow's scc increases the hapto level of that cow is also expected to increase.

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815587-41a5da00-a198-11e9-9d81-635aaf04cc36.png" width="300">


#### Log.Hapto ~ MS.pH - Testing how pH of the milk sample affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)   38.698      7.436   5.204 2.55e-07 ***
#  MS.pH         -4.721      1.120  -4.214 2.84e-05 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- As the pH of a cow's milk increases the hapto level is expected to decrease.

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815528-1fac5780-a198-11e9-8d34-047d42a1aae0.png" width="300">


#### Log.Hapto ~ MS.SFA - Testing how the short fatty acid content of the milk sample affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)   6.3732     0.5602  11.376   <2e-16 ***
#  MS.SFA        0.4213     0.2074   2.032   0.0428 *  
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- As a cow's saturated fatty acid level increases it is also expected that the hapto level increases.

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815560-33f05480-a198-11e9-8553-bc60b3d03cc1.png" width="300">


#### Log.Hapto ~ MS.PFA - Testing how the poly-saturated fatty acid content of the milk sample affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)   4.7533     0.4361  10.899  < 2e-16 ***
#  MS.PFA       17.2946     2.6549   6.514 2.09e-10 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- As a cow's polysaturated fatty acid levels increase the hapto level is also expected to increase.

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815492-0c998780-a198-11e9-951f-1aebc51071bb.png" width="300">


#### Log.Hapto ~ MS.MFA - Testing how the lactose content of the milk sample affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)   4.9967     0.3349  14.920  < 2e-16 ***
#  MS.MFA        1.8097     0.2280   7.938 1.89e-14 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- As a cows monosaturated fatty acid level increases it is expected that the hapto levels also increase.

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815810-afea9c80-a198-11e9-9f7c-36ed8bd8fb75.png" width="300">


#### Log.Hapto ~ MS.NSFA - Testing how the non-saturate fatt acid content of the milk sample affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)  5.03439    0.26833  18.762   <2e-16 ***
#  MS.NSFA      0.14278    0.01546   9.236   <2e-16 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- As a cows non-saturated fatty acid levels increase it is also expected that the hapto levels increase.

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815621-55514080-a198-11e9-8c29-abcc982a75c6.png" width="300">


#### Log.Hapto ~ MS.Palmeic - Testing how the palmeic fatty acid content of the milk sample affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)   7.2497     0.6110  11.865   <2e-16 ***
#  MS.Palmeic    0.2081     0.5355   0.389    0.698    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815513-17541c80-a198-11e9-9857-f81ea83d870f.png" width="300">


#### Log.Hapto ~ MS.Stearine - Testing how the stearine fatty acid content of the milk sample affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)   4.8960     0.3915  12.506  < 2e-16 ***
#  MS.Stearine   4.9753     0.7165   6.944 1.46e-11 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- As a cow's stearic acid level increases it is also expected that the hapto level increases.

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815608-4d919c00-a198-11e9-984e-f264da2c4413.png" width="300">


#### Log.Hapto ~ MS.Oleic - Testing how the oleic fatty acid content of the milk sample affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)   5.2203     0.3118  16.742  < 2e-16 ***
#  MS.Oleic      1.7764     0.2264   7.848 3.56e-14 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- As a cow's oleic acid level increases, it is expected that the hapto level also increases.

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815465-00152f00-a198-11e9-8a1f-37a1a9c7dce8.png" width="300">


#### Log.Hapto ~ CE.Fat.Level - Testing how the fat level of the rear of the cow affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)   7.09011    0.25001   28.36   <2e-16 ***
#  CE.Fat.Level  0.01839    0.01393    1.32    0.187    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815953-f0e2b100-a198-11e9-825e-c25081180fd6.png" width="300">


#### Log.Hapto ~ CE.Temp - Testing how the inner body temperature of the cow during the clinical evaluation affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)  
#(Intercept)  5.32666    2.15033   2.477   0.0135 *
#  CE.Temp      0.05314    0.05566   0.955   0.3400  
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815884-d27cb580-a198-11e9-8c7f-93966aafbbbe.png" width="300">


#### Log.Hapto ~ CE.Environ.Temp - Testing how the environmental temperature during the clinical evaluation affected the cow's hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)      6.15061    0.27054   22.73  < 2e-16 ***
#  CE.Environ.Temp  0.07566    0.01520    4.98 8.12e-07 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- As the environmental temperature increases, it is expected that the hapto levels of a cow also increases.

Scatterplot:
<img src="https://user-images.githubusercontent.com/52465712/60815934-e6c0b280-a198-11e9-8930-5362f7657ac1.png" width="300">


### Results
So there were 20 statistically significant variables (BS.NEFA.Log, BS.DIM, Milk.Yield, MS.Milk.Yield, MS.NEFA, MS.BHBA.Log, MS.DIM, MS.Fat, MS.Protein, MS.Lactose, MS.Acetone.Log, MS.S.Cell.Count.Log, MS.pH, MS.SFA, MS.PFA, MS.MFA, MS.NSFA, MS.Stearine, MS.Oleic, and CE.Environ.Temp). 
These will be the variables we continue using in our analysis. 



-------------
## Bi Variate Statistics - Comparing Factor Variables to Hapto Log

Now we will test the associations between Hapto.Log and factor variables using a Linear Regression Test

For running all our t-tests below:
H0: beta1 = 0 (no association/no slope between the two variables)
Ha: beta1 notequal 0 (some association/slope between the two variables)
a = 0.05

Our p-value represents the probability of getting a beta1 that matches the one found in our study, purely by chance. 
If this p-value is below 0.05, this is statistically significant and provides convincing evidence against H0.
So we reject H0. There is an association/slope between the two variables
If this p-value is above 0.05, this is not statistically significant and does not provide convincing evidence against H0.
So we fail to reject H0. There is no convincing evidence that there is an association/slope between the two variables.



#### Hapto ~ Cow.Breed - Seeing how the breed of the cow affects the cow's hapto levels
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)   7.4918     0.1214  61.728   <2e-16 ***
#  Cow.Breed02  -0.3174     0.1953  -1.625    0.105    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- If the cow is a Braunvieh, they are less likely to have a high hapto level than a Simental cow.

Box plots:
<img src="https://user-images.githubusercontent.com/52465712/60895872-aa0ebd00-a265-11e9-9864-aa1f2e09de05.png" width="300">



#### Hapto ~ Hfr.or.Cow - Seeing if the how is a heifer or a cow has any impact on the cow's haptoglobin levels
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)     7.1145     0.1117  63.686  < 2e-16 ***
#  Hfr.or.Cowhfr   0.8763     0.2072   4.229 2.65e-05 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- If this cow is a heifer, they are more likely to have a high hapto level than a cow. 

Box plots:
<img src="https://user-images.githubusercontent.com/52465712/60895866-a9762680-a265-11e9-9e11-1a6b444779f8.png" width="300">



#### Hapto ~ BS.Month_warm - Seeing if the month the blood sample was taken in has any ties with the cow's hapto levels
```r
#  Estimate Std. Error t value Pr(>|t|)    
#  (Intercept)      6.9099     0.1242  55.624  < 2e-16 ***
#  BS.Month_warm1   1.0515     0.1880   5.594 3.16e-08 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#Residual standard error: 2.488 on 710 degrees of freedom
#Multiple R-squared:  0.04222,	Adjusted R-squared:  0.04087 
#F-statistic:  31.3 on 1 and 710 DF,  p-value: 3.162e-08
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant

Box plots:
<img src="https://user-images.githubusercontent.com/52465712/60895865-a9762680-a265-11e9-8d6f-f15fb2dd5067.png" width="300">



#### Hapto ~ CE.Skin.Dehydration - Seeing if the skin dehydration has ties with the cow's hapto levels
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)             7.32021    0.09729  75.245  < 2e-16 ***
#  CE.Skin.Dehydrationred  1.69190    0.50479   3.352 0.000846 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- If this cow's hydration is reduced, they are more likely to have high hapto levels than a cow with normal hydration. 

Box plots:
<img src="https://user-images.githubusercontent.com/52465712/60895874-aa0ebd00-a265-11e9-8986-4af9eab1abcb.png" width="300">



#### Hapto ~ CE.Stom.Tension - Seeing if the tension in the cow's stomach has any ties with the cow's hapto levels
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)           7.32130    0.09959  73.511   <2e-16 ***
#CE.Stom.Tension.2erh  0.88354    0.37238   2.373   0.0179 *  
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- If this cow has an abnormal stomach tension, they are more likely to have a higher hapto level than a cow with normal stomach tension.

Box plots:
<img src="https://user-images.githubusercontent.com/52465712/60895863-a8dd9000-a265-11e9-8e22-ee476fda997c.png" width="300">



#### Hapto ~ CE.Stom.Layering - Seeing if the layering of the rumen has any ties to the hapto level of the cow
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)          7.35571    0.09764  75.337   <2e-16 ***
#CE.Stom.Layering.20  1.07024    0.57681   1.855    0.064 .  
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- If the cow has abnormal rumen layering they are more likely to have high hapto levels compared to cows with normal rumen layering.

Box plots:
<img src="https://user-images.githubusercontent.com/52465712/60895861-a8dd9000-a265-11e9-881c-a952c25f6946.png" width="300">



#### Hapto ~ CE.Stom.Fluid.Movement - Seeing if the movement of fluids in the cow's stomach has anything to do with their hapto levels
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)               7.41613    0.09813  75.574   <2e-16 ***
#  CE.Stom.Fluid.Movementre -0.75366    0.50845  -1.482    0.139    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant 

Box plots:
<img src="https://user-images.githubusercontent.com/52465712/60895858-a8dd9000-a265-11e9-8ee9-2dc82510c357.png" width="300">



#### Hapto ~ CE.Stom.Ping - Seeing if the ping of the stomach has any ties to the cow's hapto levels
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)     7.39146    0.09641  76.666   <2e-16 ***
#  CE.Stom.Pingre -1.47176    1.27540  -1.154    0.249    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant

Box plots:
<img src="https://user-images.githubusercontent.com/52465712/60895854-a844f980-a265-11e9-9eb5-4d4f72899735.png" width="300">



#### Hapto ~ CE.Stom.Fullness - Seeing if the fullness of the cow's stomach has any impact on the cow's hapto levels
```r
#Estimate Std. Error t value Pr(>|t|)    
#(Intercept)                7.8907     0.1454  54.252  < 2e-16 ***
#CE.Stom.Fullness.2abnorm  -0.8937     0.1913  -4.671 3.59e-06 ***
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- If a cow has abnormal stomach fullness, they are less likely to have high hapto levels compared to a cow with normal stomach fullness.

Box plots:
<img src="https://user-images.githubusercontent.com/52465712/68155999-7d676b00-ff10-11e9-9bc5-65878455fb2e.png" width="300">



#### Hapto ~ CE.Stom.Noise.Freq - Seeing if the activity in the stomach has any impact on the cow's hapto levels
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)                  7.3635     0.2351  31.320  < 2e-16 ***
#CE.Stom.Noise.Freq.2bis_2    1.5794     0.4588   3.443 0.000688 ***
#CE.Stom.Noise.Freq.2groe_3  -0.4506     0.6047  -0.745 0.456985    
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- If a cow has an underactive stomach, they are more likely to have a high hapto level compared to a cow with a normally active stomach. 

Box plots:
<img src="https://user-images.githubusercontent.com/52465712/60895859-a8dd9000-a265-11e9-9755-785a8b92aa03.png" width="300">



#### Hapto ~ CE.Waste.Consistency - Seeing if the consistency of the waste has any ties to the cow's hapto levels
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)                   7.2889     0.1109  65.738   <2e-16 ***
#CE.Waste.Consistency.2thick   0.5338     0.2382   2.241   0.0253 *  
#CE.Waste.Consistency.2thin   -0.4367     0.5407  -0.808   0.4195    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- If a cow has thick waste, they are more likely to have high hapto levels then a cow with normal waste consistency. 

Box plots:
<img src="https://user-images.githubusercontent.com/52465712/68156004-7e000180-ff10-11e9-8118-3e69da504c13.png" width="300">



#### Hapto ~ CE.Waste.Digestion - Seeing if the amount of food left undigested has any impact on the cow's hapto levels
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)               7.3686     0.1106  66.626   <2e-16 ***
#  CE.Waste.Digestionmaess   0.0285     0.2262   0.126    0.900    
#CE.Waste.Digestionschl   -1.2319     1.2683  -0.971    0.332    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant

Box plots:
<img src="https://user-images.githubusercontent.com/52465712/60895854-a844f980-a265-11e9-9eb5-4d4f72899735.png" width="300">



#### Hapto ~ CE.Locomotion.Score - Seeing if the locomotion score of the cow has anything to do with the hapto levels
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)            6.9914     0.1239  56.445  < 2e-16 ***
#CE.Locomotion.Score2   0.3794     0.2009   1.889 0.059349 .  
#CE.Locomotion.Score3   1.1675     0.3359   3.475 0.000543 ***
#CE.Locomotion.Score4   3.7103     0.5262   7.052 4.34e-12 ***
#CE.Locomotion.Score5   7.0240     1.7006   4.130 4.07e-05 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- Cows with higher locomotion scores are much more likely to have high hapto levels compared to cows with lower locomotion scores.

Box plots:
<img src="https://user-images.githubusercontent.com/52465712/60895868-a9762680-a265-11e9-86c1-69f3e08a6b74.png" width="300">



#### Hapto ~ CE.Lame - Seeing if lameness has any ties to a cow's hapto levels
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)  7.15746    0.09864  72.561  < 2e-16 ***
#  CE.Lame1     1.81656    0.28891   6.288 5.63e-10 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- If a cow is lame, they are much more likely to have a high hapto level compared to cows who are not lame.

Box plots:
<img src="https://user-images.githubusercontent.com/52465712/60895878-aaa75380-a265-11e9-95ef-b019c095c6db.png" width="300">



#### Hapto ~ BS.BHBA.1.2 - Seeing if what is classified as a high BHBA content in the blood has any ties with a high hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)    7.3192     0.1058  69.164   <2e-16 ***
#  BS.BHBA.1.21   0.2618     0.2421   1.081     0.28    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- A cow with a high blood BHBA level is slightly more likely to have a high hapto level compared to a cow with a low BHBA level.

Box plots:
<img src="https://user-images.githubusercontent.com/52465712/60895867-a9762680-a265-11e9-9d49-99a8d3a38f43.png" width="300">



#### Hapto ~ BS.NEFA.0.7 - Seeing if what is classified as a high NEFA content in the blood has any ties with a high hapto level
```r
#  Estimate Std. Error t value Pr(>|t|)    
#(Intercept)    7.0436     0.1026  68.621  < 2e-16 ***
#  BS.NEFA.0.71   1.6558     0.2315   7.153 2.12e-12 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- Cows with high blood NEFA levels are more likely to have high hapto levels compared to cows with low blood NEFA levels.

Box plots:
<img src="https://user-images.githubusercontent.com/52465712/60895864-a9762680-a265-11e9-9035-f25a909ffd09.png" width="300">



### Results
We found that, of the 17 factor variables tested, 13 of them were statistically significant including:
Cow.Breed, Hfr.or.Cow, BS.Month, CE.Skin.Dehydration, CE.Stom.Tension, CE.Stom.Fullness, CE.Stom.Layering, CE.Fluid.Movement, CE.Stom.Noise.Freq, CE.Waste.Consistency, CE.Locomotion.Score, CE.Lame, and BS.NEFA.0.7



----------
## Bi Variate Statistics - Comparing Hapto 035 to Numeric Variables

Now we will test the associations between Hapto.0.35 (A factor variable) and numeric variables using a Logistic Regression Test

For running all our t-tests below:
H0: beta1 = 0 (no association between the two variables)
Ha: beta1 notequal 0 (some association between the two variables)
a = 0.05

Our p-value represents the probability of getting a beta1 that matches the one found in our study, purely by chance. 
If this p-value is below 0.05, this is statistically significant and provides convincing evidence against H0.
So we reject H0. There is an association between the two variables
If this p-value is above 0.05, this is not statistically significant and does not provide convincing evidence against H0.
So we fail to reject H0. There is no convincing evidence that there is an association between the two variables.

Now we can begin.


#### Hapto.0.35 ~ BS.NEFA.Log - NEFA levels in the blood compared to high or low hapto levels (cutoff: 0.35)
```
#  Estimate Std. Error z value Pr(>|z|)    
#(Intercept)  -0.4378     0.1376  -3.182  0.00146 ** 
#  BS.NEFA.Log   0.6193     0.1157   5.350 8.78e-08 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                   OR     2.5 %    97.5 %
#(Intercept) 0.6454757 0.4919859 0.8441787
#BS.NEFA.Log 1.8575366 1.4860151 2.3404392
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.1.4860 & 0.2.3404
- The Odds Ratio is: 0.18575

<img src="https://user-images.githubusercontent.com/52465712/61130223-8098a000-a4b6-11e9-91f8-eba1d3754249.png" width="300">


#### Hapto.0.35 ~ BS.BHBA.Log - BHBA levels in the blood compared to high or low hapto levels (cutoff: 0.35)
```r
#  Estimate Std. Error z value Pr(>|z|)    
#(Intercept) -1.061895   0.094577   -11.23   <2e-16 ***
#  BS.BHBA.Log -0.001738   0.176337    -0.01    0.992    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1\

#                   OR     2.5 %    97.5 %
#(Intercept) 0.3457999 0.2862890 0.4149646
#BS.BHBA.Log 0.9982637 0.7035294 1.4061745
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.7035 & 1.4062
- The Odds Ratio is: 0.9983

<img src="https://user-images.githubusercontent.com/52465712/61130233-81c9cd00-a4b6-11e9-972b-f985c10d1340.png" width="300">


#### Hapto.0.35 ~ BS.DIM - Days post-calving the blood sample was taken compared to high or low hapto levels (cutoff: 0.35)
```r
#  Estimate Std. Error z value Pr(>|z|)  
#(Intercept)  -0.40466    0.27374   -1.478    0.139  
#BS.DIM       -0.03422    0.01377   -2.485    0.013 *
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                   OR     2.5 %    97.5 %
#(Intercept) 0.6672056 0.3886545 1.1380648
#BS.DIM      0.9663636 0.9404433 0.9926635
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.9404 & 0.9927
- The Odds Ratio is: 0.9663

<img src="https://user-images.githubusercontent.com/52465712/61130241-82626380-a4b6-11e9-8242-98b36e282662.png" width="300">


#### Hapto.0.35 ~ BS.MS.Date.Difference - the difference in days between sample dates compared to high or low hapto levels (cutoff: 0.35)
```r
#  Estimate Std. Error z value Pr(>|z|)    
#(Intercept)            -1.01028    0.11554   -8.744   <2e-16 ***
#  BS.MS.Date.Difference  -0.09369    0.14367   -0.652    0.514    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                            OR     2.5 %   97.5 %
#(Intercept)           0.3641180 0.2889730 0.4548415
#BS.MS.Date.Difference 0.9105638 0.6873579 1.2081055
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.6874 & 1.2081
- The Odds Ratio is: 0.9106

<img src="https://user-images.githubusercontent.com/52465712/61130220-8098a000-a4b6-11e9-80c9-b3d3432941d5.png" width="300">


#### Hapto.0.35 ~ Calving.No - number of calves compared to high or low hapto levels (cutoff: 0.35)
```r
#  Estimate Std. Error z value Pr(>|z|)    
#(Intercept)  -0.99972    0.15607   -6.406  1.5e-10 ***
#  Calving.No   -0.02043    0.04341   -0.471    0.638    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                  OR    2.5 %   97.5 %
#(Intercept) 0.3679830 0.2702100 0.4984969
#Calving.No  0.9797738 0.8984664 1.0654847
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.8985 & 1.0655
- The Odds Ratio is: 0.9798

<img src="https://user-images.githubusercontent.com/52465712/61130219-80000980-a4b6-11e9-88bc-07acf3c221ac.png" width="300">


#### Hapto.0.35 ~ Milk.Yield - average milk yield per day compared to high or low hapto levels (cutoff: 0.35)
```r
#  Estimate Std. Error z value Pr(>|z|)    
#(Intercept) 1.18615    0.51308  2.312   0.0208 *  
#  Milk.Yield   -0.07213    0.01639   -4.400 1.08e-05 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                   OR     2.5 %    97.5 %
#(Intercept) 3.2744407 1.2108479 9.1013198
#Milk.Yield  0.9304146 0.9002311 0.9601403
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.9002 & 0.9601
- The Odds Ratio is: 0.9304

<img src="https://user-images.githubusercontent.com/52465712/61130231-81313680-a4b6-11e9-81ce-62d853d836e6.png" width="300">


#### Hapto.0.35 ~ MS.Milk.Yield - amount of milk in the sample compared to high or low hapto levels (cutoff: 0.35)
```r
#  Estimate Std. Error z value Pr(>|z|)  
#(Intercept)    -0.49620    0.24104   -2.059   0.0395 *
#  MS.Milk.Yield  -0.03880    0.01582   -2.453   0.0142 *
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                    OR   2.5 %   97.5 %
#(Intercept)   0.6088385 0.3814140 0.9823860
#MS.Milk.Yield 0.9619475 0.9316132 0.9913059
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.9316 & 0.9913
- The Odds Ratio is: 0.9619

<img src="https://user-images.githubusercontent.com/52465712/61130232-81c9cd00-a4b6-11e9-9b48-7afe31732d12.png" width="300">


#### Hapto.0.35 ~ MS.NEFA - NEFA levels in the milk compared to high or low hapto levels (cutoff: 0.35)
```r
#  Estimate Std. Error z value Pr(>|z|)    
#(Intercept)  -1.31895    0.20355   -6.480 9.18e-11 ***
#  MS.NEFA     0.05084    0.03516  1.446    0.148    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                   OR     2.5 %   97.5 %
#(Intercept) 0.2674149 0.1776848 0.3951421
#MS.NEFA     1.0521516 0.9822447 1.1276385
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.9822 & 1.1276
- The Odds Ratio is: 1.0522

<img src="https://user-images.githubusercontent.com/52465712/61130212-80000980-a4b6-11e9-9a9c-916c65c65164.png" width="300">


#### Hapto.0.35 ~ MS.BHBA.Log - BHBA levels in the milk compared to high or low hapto levels (cutoff: 0.35)
```r
#  Estimate Std. Error z value Pr(>|z|)    
#(Intercept)   -2.8126     0.5496   -5.117  3.1e-07 ***
#  MS.BHBA.Log  0.4384     0.1293  3.392 0.000695 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                    OR     2.5 %     97.5 %
#(Intercept) 0.06004586 0.01993678 0.1725241
#MS.BHBA.Log 1.55025210 1.20745885 2.0058778
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 1.2075 & 2.0059
- The Odds Ratio is: 1.5503

<img src="https://user-images.githubusercontent.com/52465712/61130221-8098a000-a4b6-11e9-8092-881d9dda32d2.png" width="300">


#### Hapto.0.35 ~ MS.DIM - Days post-calving when the milk sample was taken compared to high or low hapto levels (cutoff: 0.35)
```r
#  Estimate Std. Error z value Pr(>|z|)  
#(Intercept)  -0.43426    0.26755   -1.623   0.1046  
#MS.DIM       -0.03363    0.01382   -2.434   0.0149 *
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                   OR     2.5 %   97.5 %
#(Intercept) 0.6477451 0.381882 1.0913907
#MS.DIM      0.9669286 0.940907 0.9933415
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.9409 & 0.9933
- The Odds Ratio is: 0.9669

<img src="https://user-images.githubusercontent.com/52465712/61130228-81313680-a4b6-11e9-8f50-b503429581e8.png" width="300">


#### Hapto.0.35 ~ MS.Fat - Percentage of fat in the milk compared to high or low hapto levels (cutoff: 0.35)
```r
#  Estimate Std. Error z value Pr(>|z|)    
#(Intercept)  -2.52045    0.37107   -6.792 1.10e-11 ***
#  MS.Fat      0.31890    0.07763  4.108 3.99e-05 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                    OR     2.5 %     97.5 %
#(Intercept) 0.08042312 0.03834077 0.164724
#MS.Fat      1.37561484 1.18291985 1.605050
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 1.1829 & 1.6051
- The Odds Ratio is: 1.3756

<img src="https://user-images.githubusercontent.com/52465712/61130234-81c9cd00-a4b6-11e9-962e-ade2e642569a.png" width="300">


#### Hapto.0.35 ~ MS.Protein - Percentage of protein in the milk compared to high or low hapto levels (cutoff: 0.35)
```r
#  Estimate Std. Error z value Pr(>|z|)   
#(Intercept)  1.6740     0.9501  1.762  0.07808 . 
#MS.Protein    -0.8382     0.2916   -2.874  0.00405 **
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                   OR      2.5 %   97.5 %
#(Intercept) 5.3332337 0.8468409 35.0861435
#MS.Protein  0.4324916 0.2420357  0.7591196
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.2420 & 0.7591
- The Odds Ratio is: 0.4325

<img src="https://user-images.githubusercontent.com/52465712/61130230-81313680-a4b6-11e9-89f7-d8b2ffa69f88.png" width="300">


#### Hapto.0.35 ~ MS.Lactose - Percentage of lactose in the milk compared to high or low hapto levels (cutoff: 0.35)
```r
#  Estimate Std. Error z value Pr(>|z|)    
#(Intercept)  6.6448     2.2116  3.005 0.002660 ** 
#  MS.Lactose    -1.6002     0.4598   -3.480 0.000501 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                     OR        2.5 %      97.5 %
#(Intercept) 768.7424885 11.08935380 6.422169e+04
#MS.Lactose    0.2018549  0.08036853 4.868175e-01
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.0804 & 0.4868
- The Odds Ratio is: 0.2019

<img src="https://user-images.githubusercontent.com/52465712/61130242-82626380-a4b6-11e9-9eed-c22462f60619.png" width="300">


#### Hapto.0.35 ~ MS.Acetone.Log - Amount of acetone in the milk compared to high or low hapto levels (cutoff: 0.35)
```r
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)      -3.0531     0.5197   -5.875 4.23e-09 ***
#  MS.Acetone.Log  0.4734     0.1101  4.299 1.72e-05 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                     OR     2.5 %     97.5 %
#(Intercept)    0.04721372 0.01656692 0.1275612
#MS.Acetone.Log 1.60549727 1.29884114 2.0020198
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 1.2988 & 2.0020
- The Odds Ratio is: 1.6055

<img src="https://user-images.githubusercontent.com/52465712/61130229-81313680-a4b6-11e9-856f-8000c24a1e85.png" width="300">


#### Hapto.0.35 ~ MS.Urea - Amount of urea in the milk compared to high or low hapto levels (cutoff: 0.35)
```r
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)  -1.42228    0.28615   -4.970 6.68e-07 ***
#  MS.Urea     0.01434    0.01077  1.332    0.183    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                   OR     2.5 %   97.5 %
#(Intercept) 0.2411626 0.1371110 0.4222059
#MS.Urea     1.0144453 0.9930349 1.0360047
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.9930 & 1.0360
- The Odds Ratio is: 1.0144

<img src="https://user-images.githubusercontent.com/52465712/61130245-82fafa00-a4b6-11e9-98bc-a70222be8f68.png" width="300">


#### Hapto.0.35 ~ MS.S.Cell.Count.Log - Somatic cell count compared to high or low hapto levels (cutoff: 0.35)
```r

#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)          -2.99243    0.31308   -9.558  < 2e-16 ***
#  MS.S.Cell.Count.Log 0.44440    0.06696  6.636 3.22e-11 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                            OR      2.5 %     97.5 %
#(Intercept)         0.05016554 0.02680467 0.09160078
#MS.S.Cell.Count.Log 1.55955294 1.36984475 1.78177319
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 1.3698 & 1.7818
- The Odds Ratio is: 1.5596

<img src="https://user-images.githubusercontent.com/52465712/61130225-81313680-a4b6-11e9-8fc9-6bd89005ae64.png" width="300">


#### Hapto.0.35 ~ MS.pH - pH of the milk sample compared to high or low hapto levels (cutoff: 0.35)
```r

#Estimate Std. Error z value Pr(>|z|)    
#(Intercept) 22.4242     6.6257  3.384 0.000713 ***
#  MS.pH         -3.5419     0.9997   -3.543 0.000396 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                      OR        2.5 %       97.5 %
#(Intercept) 5.479273e+09 1.481019e+04 3.212239e+15
#MS.pH       2.895822e-02 3.901792e-03 2.003116e-01
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.0039 & 0.2003
- The Odds Ratio is: 0.02896

<img src="https://user-images.githubusercontent.com/52465712/61130222-8098a000-a4b6-11e9-8b3c-1fe31b442bab.png" width="300">


#### Hapto.0.35 ~ MS.SFA - Amount of short fatty acids in the milk compared to high or low hapto levels (cutoff: 0.35)
```r
#  Estimate Std. Error z value Pr(>|z|)    
#(Intercept)   -1.7704     0.4847   -3.653 0.000259 ***
#  MS.SFA       0.3058     0.1763  1.735 0.082697 .  
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                   OR     2.5 %    97.5 %
#(Intercept) 0.1702587 0.0647622 0.4361112
#MS.SFA      1.3577666 0.9612558 1.9244626
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.9613 & 1.9245
- The Odds Ratio is: 1.3578

<img src="https://user-images.githubusercontent.com/52465712/61130236-81c9cd00-a4b6-11e9-967f-45f02753039e.png" width="300">


#### Hapto.0.35 ~ MS.MFA - Amount of monosaturated fatty acids in the milk compared to high or low hapto levels (cutoff: 0.35)
```r
#  Estimate Std. Error z value Pr(>|z|)    
#(Intercept)   -2.6461     0.3370   -7.852 4.09e-15 ***
#  MS.MFA       1.1806     0.2162  5.460 4.75e-08 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                    OR     2.5 %    97.5 %
#(Intercept) 0.07092569 0.03590746 0.1349421
#MS.MFA      3.25645585 2.15104166 5.0336875
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 2.1510 & 5.0337
- The Odds Ratio is: 3.2565

<img src="https://user-images.githubusercontent.com/52465712/61130214-80000980-a4b6-11e9-8f80-d6a98ca990ee.png" width="300">


#### Hapto.0.35 ~ MS.PFA - Amount of polysaturated fatty acids in the milk compared to high or low hapto levels (cutoff: 0.35)
```r
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)   -2.9620     0.4357   -6.798 1.06e-11 ***
#  MS.PFA      12.3103     2.5248  4.876 1.08e-06 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                      OR        2.5 %       97.5 %
#(Intercept) 5.171614e-02    0.0214376 1.187319e-01
#MS.PFA      2.219794e+05 1741.8656141 3.562008e+07
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 1,741.8656 & 35,620,080
- The Odds Ratio is: 221,979.4

<img src="https://user-images.githubusercontent.com/52465712/61130237-82626380-a4b6-11e9-9c85-b677c92565fb.png" width="300">


#### Hapto.0.35 ~ MS.NSFA - Amount of non-saturated fatty acids in the milk compared to high or low hapto levels (cutoff: 0.35)
```r
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)  -2.68943    0.27485   -9.785  < 2e-16 ***
#  MS.NSFA     0.09567    0.01486  6.440  1.2e-10 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                    OR     2.5 %     97.5 %
#(Intercept) 0.06791959 0.03915963 0.1151907
#MS.NSFA     1.10039071 1.06925170 1.1335033
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 1.0693 & 1.1335
- The Odds Ratio is: 1.1004

<img src="https://user-images.githubusercontent.com/52465712/61130213-80000980-a4b6-11e9-8ca3-d5d5389bc7ed.png" width="300">


#### Hapto.0.35 ~ MS.Palmeic - Amount of palmeic acids in the milk compared to high or low hapto levels (cutoff: 0.35)
```r
#Estimate Std. Error z value Pr(>|z|)  
#(Intercept)   -1.1447     0.5184   -2.208   0.0272 *
#  MS.Palmeic   0.1668     0.4525  0.369   0.7124  
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                   OR     2.5 %   97.5 %
#(Intercept) 0.3183283 0.1152371 0.8867087
#MS.Palmeic  1.1815712 0.4784222 2.8454994
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.4784 & 2.8455
- The Odds Ratio is: 1.1816

<img src="https://user-images.githubusercontent.com/52465712/61130238-82626380-a4b6-11e9-93c7-490be57f4573.png" width="300">


#### Hapto.0.35 ~ MS.Stearine - Amount of stearine acids in the milk compared to high or low hapto levels (cutoff: 0.35)
```r
#  Estimate Std. Error z value Pr(>|z|)    
#(Intercept)   -2.7452     0.3849   -7.132 9.89e-13 ***
#  MS.Stearine  3.3217     0.6662  4.986 6.17e-07 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                     OR       2.5 %     97.5 %
#(Intercept)  0.06423435 0.02956922   0.1341302
#MS.Stearine 27.70780379 7.67363342 105.2979239
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 7.6736 & 105.2979
- The Odds Ratio is: 27.7078

<img src="https://user-images.githubusercontent.com/52465712/61130215-80000980-a4b6-11e9-8689-75fc1142eeae.png" width="300">


#### Hapto.0.35 ~ MS.Oleic - Amount of oleic acids in the milk compared to high or low hapto levels (cutoff: 0.35)
```r
#  Estimate Std. Error z value Pr(>|z|)    
#(Intercept)   -2.5019     0.3151   -7.940 2.02e-15 ***
#  MS.Oleic     1.1605     0.2147  5.406 6.44e-08 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                   OR     2.5 %     97.5 %
#(Intercept) 0.08192889 0.04334827 0.1494627
#MS.Oleic    3.19145413 2.11413103 4.9170623
 ```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 2.1141 & 4.9171
- The Odds Ratio is: 3.1915

<img src="https://user-images.githubusercontent.com/52465712/61130235-81c9cd00-a4b6-11e9-9c40-55c27085615c.png" width="300">



#### Hapto.0.35 ~ CE.Fat.Level - Amount of fat on the back of the cow compared to high or low hapto levels (cutoff: 0.35)
```r
#  Estimate Std. Error z value Pr(>|z|)    
#(Intercept)   -1.33316    0.22396   -5.953 2.64e-09 ***
#  CE.Fat.Level 0.01772    0.01219  1.454    0.146    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                   OR     2.5 %     97.5 %
#(Intercept)  0.2636433 0.1692158 0.4076237
#CE.Fat.Level 1.0178788 0.9936573 1.0424079
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.9937 & 1.0424
- The Odds Ratio is: 1.0179

<img src="https://user-images.githubusercontent.com/52465712/61130243-82626380-a4b6-11e9-88d4-439ad49164ce.png" width="300">



#### Hapto.0.35 ~ CE.Temp - Inner body temperature of the cow during the evaluation compared to high or low hapto levels (cutoff: 0.35)
```r
#  Estimate Std. Error z value Pr(>|z|)
#(Intercept)  -2.46870    1.76722   -1.397    0.162
#CE.Temp     0.03656    0.04571  0.800    0.424

#                  OR     2.5 %     97.5 %
#(Intercept) 0.08469462 0.0004760498 3.870504
#CE.Temp     1.03723649 0.9394731507 1.186344
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.9395 & 1.1863
- The Odds Ratio is: 1.0372

<img src="https://user-images.githubusercontent.com/52465712/61130218-80000980-a4b6-11e9-80e6-7c8c4e79ae1d.png" width="300">



#### Hapto.0.35 ~ CE.Environ.Temp - Environmental temperature during the evaluation compared to high or low hapto levels (cutoff: 0.35)
```r
#  Estimate Std. Error z value Pr(>|z|)    
#(Intercept)      -2.02214    0.26844   -7.533 4.96e-14 ***
#  CE.Environ.Temp 0.05774    0.01430  4.036 5.43e-05 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                       OR     2.5 %     97.5 %
#(Intercept)     0.1323718 0.07720828 0.2214486
#CE.Environ.Temp 1.0594356 1.03044057 1.0899464
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 1.0304 & 1.0899
- The Odds Ratio is: 1.0594

<img src="https://user-images.githubusercontent.com/52465712/61130240-82626380-a4b6-11e9-89af-56c612b4845b.png" width="300">



### Results
We found that, of the 27 numerical variables tested, 19 of them were statistically significant including: BS.NEFA.Log, BS.DIM,  Milk.Yield, MS.Milk.Yield, MS.BHBA.Log, MS.DIM, MS.Fat, MS.Protein, MS.Lactose, MS.Acetone.Log, MS.S.Cell.Count.Log, MS.pH, MS.PFA, MS.MFA, MS.SFA, MS.NSFA, MS.Stearine, MS.Oleic, and CE.Environ.Temp.



-----------
# Bi Variate Statistics - Comparing Hapto 035 to Factor Variables


Now we will test the associations between Hapto.0.35 (A factor variable) and other factor variables  using a Logistic Regression Test
For running all our t-tests below: 
H0: beta1 = 0 (no association between the two variables) 
Ha: beta1 notequal 0 (some association between the two variables) 
a = 0.05

Our p-value represents the probability of getting a beta1 that matches the one found in our study, purely by chance. 
If this p-value is below 0.05, this is statistically significant and provides convincing evidence against H0. 
So we reject H0. There is an association between the two variables 
If this p-value is above 0.05, this is not statistically significant and does not provide convincing evidence against H0. 
So we fail to reject H0. There is no convincing evidence that there is an association between the two variables.




#### Hapto.0.35 ~ Cow.Breed - Cow breed compared to high or low hapto levels (cutoff: 0.35)
```r
#            Estimate Std. Error z value Pr(>|z|)    
#(Intercept)  -0.9372     0.1064  -8.811   <2e-16 ***
#  Cow.Breed02  -0.3391     0.1806  -1.877   0.0605 .
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                   OR     2.5 %    97.5 %
#(Intercept) 0.3917197 0.3169320 0.4810913
#Cow.Breed02 0.7124220 0.4977921 1.0115687
```
- We find that, at a significance level of 0.05, this association is: Almost Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.4978 & 1.0116
- The Odds Ratio is: 0.7124
- If a cow is a Braunvieh it is less likely to have a high hapto level than a simental cow. 


2x2 table
```r
#     1   0
#01 123 314
#02 60  215
```
Proportion Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/61131821-71b3ec80-a4ba-11e9-8de4-8e9120dacb21.png" width="300">



#### Hapto.0.35 ~ Hfr.or.Cow - Seeing whether being a heifer or a cow has any ties to high or low hapto levels (cutoff: 0.35)
```r
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)    -1.2668     0.1075 -11.789  < 2e-16 ***
#Hfr.or.Cowhfr   0.6382     0.1812   3.522 0.000429 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                     OR     2.5 %    97.5 %
#(Intercept)   0.2817259 0.2272278 0.3464052
#Hfr.or.Cowhfr 1.8930931 1.3249412 2.6981392
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 1.3249 & 2.6981
- The Odds Ratio is: 1.8931
- If a cow is a heifer, that cow is more likely to have a high hapto level than a cow who is not a heifer.


2x2 table
```r
#      1   0
#hfr 72  135
#cow 111 394
```
Proportion Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/61131824-724c8300-a4ba-11e9-927b-ac94f1385da7.png" width="300">



#### Hapto.0.35 ~ BS.Month_warm - Seeing whether the month where the blood sample was taken has any ties to high or low hapto levels (cutoff: 0.35)
```r
##Coefficients:
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)     -1.4531     0.1274 -11.404  < 2e-16 ***
#  BS.Month_warm1   0.8078     0.1746   4.627 3.71e-06 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#(Dispersion parameter for binomial family taken to be 1)

#Null deviance: 811.57  on 711  degrees of freedom
#Residual deviance: 789.77  on 710  degrees of freedom
#AIC: 793.77

#Number of Fisher Scoring iterations: 4

#                      OR     2.5 %    97.5 %
#(Intercept)    0.2338462 0.1809271 0.2983565
#BS.Month_warm1 2.2429696 1.5957803 3.1660030
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- If the blood sample was taken during a warm month (July, August, or September) the cow the sample was taken from is more likely to have a high hapto value compared to during the cold months (June, October, November, or December).


2x2 table
```r
#      1   0
#  0  76 325
#  1 107 204
```
Proportion Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/65378092-a04c0180-dc79-11e9-8fa8-e2208e76bf31.png" width="300">



#### Hapto.0.35 ~ CE.Skin.Dehydration - Seeing if dehydration has any ties to high or low hapto levels (cutoff: 0.35)
```r
#                       Estimate Std. Error z value Pr(>|z|)    
#(Intercept)            -1.08678    0.08869 -12.253   <2e-16 ***
#  CE.Skin.Dehydrationred  0.93263    0.40327   2.313   0.0207 *  

#                              OR     2.5 %    97.5 %
#(Intercept)            0.3373016 0.2827383 0.4003864
#CE.Skin.Dehydrationred 2.5411765 1.1342470 5.6110516
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 1.1342 & 5.6111
- The Odds Ratio is: 2.5412
- If a cow is dehydrated it is more likely to have a high hapto level than a cow which is hydrated.


2x2 table
```r
#       1   0
#red  12  14
#phy 170 504
```
Proportion Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/61131816-71b3ec80-a4ba-11e9-81b4-fc9f30b3463e.png" width="300">



#### Hapto.0.35 ~ CE.Stom.Tension - Seeing if tension in the stomach has any ties to high or low hapto levels (cutoff: 0.35)
```r
#Estimate Std. Error z value Pr(>|z|)  
#(Intercept)          -1.07614    0.09015 -11.937   <2e-16 ***
#CE.Stom.Tension.2erh  0.41285    0.31185   1.324    0.186    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                          OR     2.5 %    97.5 %
#(Intercept)        1.941176 1.0966521 3.565062
#CE.Stom.Tensionphy 1.511111 0.8033027 2.749080
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.8033 & 2.7491
- The Odds Ratio is: 1.5111


2x2 table
```r
#       1   0
# erh  17  33
# phy 165 484
```
Proportion Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/61131822-724c8300-a4ba-11e9-87fe-d208b4e72722.png" width="300">



#### Hapto.0.35 ~ CE.Stom.Layering - Seeing if abnormal layering in the rumen has any ties to high or low hapto levels (cutoff: 0.35)
```r
#Estimate Std. Error z value Pr(>|z|)  
#(Intercept)          -1.0481     0.0876 -11.965   <2e-16 ***
#CE.Stom.Layering.20   0.2008     0.4958   0.405    0.685      
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                         OR     2.5 %   97.5 %
#(Intercept)         0.3505976 0.2945544 0.4153324
#CE.Stom.Layering.20 1.2224026 0.4273644 3.0978249
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.4274 & 3.0978
- The Odds Ratio is: 1.2224


2x2 table
```r
#        1    0
#abnorm  6   14
#norm  176  502
```
Proportion Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/61131823-724c8300-a4ba-11e9-91ad-40580c0945ff.png" width="300">



#### Hapto.0.35 ~ CE.Stom.Fluid.Movement - Seeing if abnormal movement of fluid in the stomach has any ties to high or low hapto levels (cutoff: 0.35)
```r
#  Estimate Std. Error z value Pr(>|z|)
#(Intercept)              -1.02841    0.08758 -11.743   <2e-16 ***
#CE.Stom.Fluid.Movementre -0.40668    0.50526  -0.805    0.421    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                                OR     2.5 %    97.5 %
#(Intercept)              0.3575758 0.3004420 0.4235966
#CE.Stom.Fluid.Movementre 0.6658596 0.2197081 1.6622538
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.2197 & 1.6623
- The Odds Ratio is: 0.6659


2x2 table
```r
#      1   0
#re   5   21
#obb 177 495
```
Proportion Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/61131818-71b3ec80-a4ba-11e9-8646-29805e74c259.png" width="300">



#### Hapto.0.35 ~ CE.Stom.Ping - Seeing if the ping of the rumen has any ties to high or low hapto levels (cutoff: 0.35)
```r
#                 Estimate Std. Error z value Pr(>|z|)
#(Intercept)     -1.03822    0.08626 -12.037   <2e-16 ***
#CE.Stom.Pingre -13.52785  441.37170  -0.031    0.976    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                         OR     2.5 %       97.5 %
#(Intercept)    3.540856e-01 0.2982985 4.183959e-01
#CE.Stom.Pingre 1.333303e-06        NA 1.268792e+16
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: NA & 1.268792e+16
- The Odds Ratio is: 0


2x2 table
```r
#        1   0
#re      0   4
#obb   182 514
```
Proportion Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/61131830-72e51980-a4ba-11e9-9552-acfe5a955b33.png" width="300">



#### Hapto.0.35 ~ CE.Stom.Fullness - Seeing if the fullness of the stomach has any ties to high or low hapto levels (cutoff: 0.35)
```r
#  Estimate Std. Error z value Pr(>|z|)
#(Intercept)               -0.6830     0.1233  -5.539 3.04e-08 ***
#CE.Stom.Fullness.2abnorm  -0.6848     0.1747  -3.921 8.81e-05 ***
#---
#Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                              OR      2.5 %    97.5 %
#(Intercept)              0.5051020 0.3952742 0.6413152
#CE.Stom.Fullness.2abnorm 0.5041722 0.3574266 0.7092799
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.3574 & 0.7093
- The Odds Ratio is: 0.5042
- If the cow has abnormal stomach fullness, they are less likely to have high hapto levels than a cow with normal stomach fullness.

2x2 table
```r
#           1   0
#  abnorm 82  322
#  norm   99  196
```
Proportion Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/68156001-7d676b00-ff10-11e9-914f-ef4288c0bed5.png" width="300">



#### Hapto.0.35 ~ CE.Stom.Noise.Freq - Seeing if the activity of the rumen has any ties to high or low hapto levels (cutoff: 0.35)
```r
#                           Estimate Std. Error z value Pr(>|z|)
#(Intercept)                 -1.1542     0.1939  -5.954 2.62e-09 ***
#CE.Stom.Noise.Freq.2bis_2    0.8440     0.3411   2.474   0.0134 *  
#CE.Stom.Noise.Freq.2groe_3  -0.2809     0.5340  -0.526   0.5989   
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                                OR      2.5 %    97.5 %
#(Intercept)                0.3153153 0.2126810 0.4558635
#CE.Stom.Noise.Freq.2bis_2  2.3257143 1.1872557 4.5438679
#CE.Stom.Noise.Freq.2groe_3 0.7551020 0.2383539 2.0148727
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant for Underactive
- The 95% Confidence Interval estimates that the true OR is between: Underactive - 1.1873 & 4.5439, Overactive - 0.2384 & 2.0149
- The Odds Ratio is: Underactive - 2.3257, Overactive - 0.7551
- If a cow has an underactive stomach they are more likely to have a high hapto level than a cow with normal levels of stomach activity.


2x2 table
```r
#           1   0
#under     22  30
#over       5  21
#norm      35 111
```
Proportion Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/61131828-724c8300-a4ba-11e9-9c52-28a59ddbd369.png" width="300">



#### Hapto.0.35 ~ CE.Waste.Consistency - Seeing if the consistency of the waste has any ties to high or low hapto levels (cutoff: 0.35)
```r
#                          Estimate Std. Error z value Pr(>|z|)   
#(Intercept)                  -1.0784     0.1004 -10.743   <2e-16 ***
#CE.Waste.Consistency.2thick   0.2799     0.2057   1.361    0.174    
#CE.Waste.Consistency.2thin   -0.8188     0.6272  -1.305    0.192  
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                                 OR      2.5 %     97.5 %
#(Intercept)                 0.3401535 0.2784664 0.4128679
#CE.Waste.Consistency.2thick 1.3229323 0.8787468 1.9708588
#CE.Waste.Consistency.2thin  0.4409774 0.1027374 1.3119689
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.8787 & 1.9709
- The Odds Ratio is: 1.3229



2x2 table
```r
#         1   0
#norm  133 391
#thick  45 100
#thin    3  20
```
Proportion Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/68156002-7e000180-ff10-11e9-9492-6f69e2d65e12.png" width="300">



#### Hapto.0.35 ~ CE.Waste.Digestion - Seeing if quality of digestion of the food has any ties to high or low hapto levels (cutoff: 0.35)
```r
#  Estimate Std. Error z value Pr(>|z|)
#(Intercept)              -0.99404    0.09857 -10.084   <2e-16 ***
#CE.Waste.Digestionmaess  -0.20466    0.20969  -0.976    0.329    
#CE.Waste.Digestionschl  -13.57203  441.37170  -0.031    0.975    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                  OR     2.5 %     97.5 %
#(Intercept)             3.700787e-01 0.3041391 4.477396e-01
#CE.Waste.Digestionmaess 8.149274e-01 0.5351637 1.219792e+00
#CE.Waste.Digestionschl  1.275684e-06        NA 1.210438e+16
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: Bad - NA & 1.2104e+16, Not Good - 0.5352 & 1.2198
- The Odds Ratio is: Bad - 0, Not Good - 0.8149


2x2 table
```r
#        1   0
#gut   141 381
#maess  38 126
#schl    0   4
```
Proportion Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/61131825-724c8300-a4ba-11e9-9166-9cf8613da026.png" width="300">



#### Hapto.0.35 ~ CE.Locomotion.Score - Seeing if the cow's ability to move has any ties to high or low hapto levels (cutoff: 0.35)
```r
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)           -1.4895     0.1333 -11.176  < 2e-16 ***
#  CE.Locomotion.Score2   0.5146     0.1991   2.585  0.00973 ** 
#  CE.Locomotion.Score3   1.1820     0.2952   4.003 6.24e-05 ***
#  CE.Locomotion.Score4   2.7133     0.5259   5.159 2.48e-07 ***
#  CE.Locomotion.Score5  16.0555   624.1938   0.026  0.97948    
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                               OR        2.5 %     97.5 %
#(Intercept)          2.254902e-01 1.723359e-01  0.2908171
#CE.Locomotion.Score2 1.673002e+00 1.131590e+00  2.4720837
#CE.Locomotion.Score3 3.260870e+00 1.816791e+00  5.8058921
#CE.Locomotion.Score4 1.507826e+01 5.745394e+00 47.1424096
#CE.Locomotion.Score5 9.393668e+06 2.620043e-36         NA
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 2 - 1.1316 & 2.4721, 5 - 2.62e-36 & NA
- The Odds Ratio is: 2 - 1.6730, 5 - 9,393,668
- The higher the locomotion score of the cow the more likely it is that the cow has a high hapto level compared to a cow with a locomotion score of 1.


2x2 table
```r
#      1   0
#  1  69 306
#  2  63 167
#  3  25  34
#  4  17   5
#  5   2   0
```
Proportion Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/61131831-72e51980-a4ba-11e9-8a27-f81a0e5df371.png" width="300">



#### Hapto.0.35 ~ CE.Lame - Seeing if lameness has any ties to high or low hapto levels (cutoff: 0.35)
```r
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)  -1.2599     0.0961 -13.111  < 2e-16 ***
#CE.Lame1      1.3806     0.2400   5.752 8.81e-09 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                   OR     2.5 %    97.5 %
#(Intercept) 0.2836735 0.2341616 0.3413887
#CE.Lame1    3.9771260 2.4866815 6.3876875
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 2.4867 & 6.3877
- The Odds Ratio is: 3.9771
- If a cow is lame, they are more likely to have a high hapto level than a cow which is not lame. 


#2x2 table
```r
#      1   0
#  1  44  39
#  0 139 490
```
Proportion Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/61131836-74164680-a4ba-11e9-9d3d-9a34d9fad336.png" width="300">



#### Hapto.0.35 ~ BS.BHBA.1.2 - Seeing if high BHBA levels has any ties to high or low hapto levels (cutoff: 0.35)
```r
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)  -1.10789    0.09645 -11.487   <2e-16 ***
#BS.BHBA.1.21  0.23242    0.21147   1.099    0.272 
#---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

#                   OR     2.5 %    97.5 %
#(Intercept)  0.330254 0.2725075 0.3978387
#BS.BHBA.1.21 1.261655 0.8271331 1.8983632
```
- We find that, at a significance level of 0.05, this association is: Not Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 0.8271 & 1.8984
- The Odds Ratio is: 1.2617


2x2 table
```r
#    1   0
#1  40  96
#0 143 433
```
Proportion Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/61131834-737db000-a4ba-11e9-9654-3b11d85b1de7.png" width="300">


#### Hapto.0.35 ~ BS.NEFA.0.7 - Seeing if high NEFA levels has any ties to high or low hapto levels (cutoff: 0.35)
```r
#Estimate Std. Error z value Pr(>|z|)    
#(Intercept)   -1.3262     0.1027  -12.91  < 2e-16 ***
#BS.NEFA.0.71   1.1255     0.1985    5.67 1.43e-08 ***
#  ---
#  Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
#              OR     2.5 %    97.5 %
#(Intercept)  0.2654867 0.2161935 0.3234677
#BS.NEFA.0.71 3.0818182 2.0867042 4.5486014
```
- We find that, at a significance level of 0.05, this association is: Statistically Significant
- The 95% Confidence Interval estimates that the true OR is between: 2.0867 & 4.5486
- The Odds Ratio is: 3.0818
- If a cow has a blood nefa level above 0.7, they are more likely to have a high hapto level than a cow which has a blood nefa level under 0.7.


2x2 table
```r
#      1   0
#  1  63  77
#  0 120 452
```
Proportion Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/61131835-737db000-a4ba-11e9-912f-52748d7f433b.png" width="300">




### Results
- We found that, of the 16 factor variables tested, 10 of them were statistically significant including: Cow.Breed, Hfr.or.Cow, BS.Month, CE.Skin.Dehydration, CE.Stom.Noise.Freq, CE.Stom.Fullness, CE.Waste.Consistency, CE.Locomotion.Score, CE.Lame, and BS.NEFA.0.7
