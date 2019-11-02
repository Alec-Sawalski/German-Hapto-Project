# Descriptive Statistics

--------------------------
## Table of Contents  
[List of all variables in the data set](#List-of-all-variables-in-the-data-set)

[Descriptive Statistics - Factor Variables](#descriptive-statistics---factor-variables)

[Descriptive Statistics - Numerical Variables](#descriptive-statistics---numerical-variables)  

[Descriptive Statistics - Log Transformations of Skewed Numerical Variables](#descriptive-statistics---log-transformations-of-skewed-numerical-variables)  


---------
## List of all variables in the data set 
including the additional variables that were re-coded or generated

MCS to insert table here!!!!





---------
## Descriptive Statistics - Factor Variables


#### Cow.Breed - Breed of the cow, represented by numbers, 1 = Simmental  & 2 = Braunvieh

61.4% of the cows are Simmental, 38.6% are Braunveih

Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/60673106-48221200-9e77-11e9-9ec9-8c341ec6e536.png" width="300">

#### CE.Skin.Dehydration - Elasticity of the skin of the cow to measure the dehydration, "phy" = normal, "red" = abnormal

94.6% are normal, 5.4% are abnormal

Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/60673001-0b561b00-9e77-11e9-808e-c5a64614b62f.png" width="300">

#### CE.Stom.Tension - Measurement of abdominal tension aka stomach aches, "phy" = normal, "erh" = abnormal

7.0% are abnormal, 93% are normal

Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/60672811-a1d60c80-9e76-11e9-8121-f19e41dd6d19.png" width="300">

#### CE.Stom.Fluid.Movement - Movement of fluids in the stomach, "obb" = normal, "re" = abnormal

94.4% are normal, 5.6% are abnormal

Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/60673029-232d9f00-9e77-11e9-9edf-37447dd3f69b.png" width="300">

#### CE.Stom.Ping - Ping of the stomach, "obb" = normal, "re" = abnormal

97.8% are normal, 2.2% are abnormal

Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/60672991-0002ef80-9e77-11e9-81df-e19bd3f44c45.png" width="300">

#### CE.Waste.Consistency - Waste Consistency, "thick", "normal", "thin"

75.7% are normal, 7.7% are thick, 16.6% are thin

Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/60672899-cd58f700-9e76-11e9-8f43-5333cc7827d4.png" width="300">

#### CE.Waste.Digestion - How well food has been digested by the cow, "gut" = good, "maess" = less than good, "schl" = bad

73.3% are well-digested, 23.0% are mildly-digested, 0.6% are terribly-digested

Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/60672787-8b2fb580-9e76-11e9-9fe5-abdcbbe4e7e9.png" width="300">

#### CE.Stom.Noise.Freq - Frequency of Rumen Rumbles, "phy" = normal (3 per minute), "bis_2" = under-active (less than 3 per minute), "groe_3" = over-active (more than 3 per minute)

23.2% are under-active, 11.6% are over-active, 65.2% are normal

Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/60673012-16a94680-9e77-11e9-8f41-b34875d35128.png" width="300">

#### CE.Stom.Layering - Layering of the rumen, 0 = abnormal layering, 1 = normal layering

2.9% are abnormally layered, 97.1% are normally layered

Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/60672867-c03c0800-9e76-11e9-8f3f-84da012d672a.png" width="300">

#### CE.Stom.Fullness - Measure of how full the stomach is, "normal", "low", and "high"

96% are normal, 3.5% are low, 0.5% are high

Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/60672833-b0bcbf00-9e76-11e9-9782-f37c1e63bf1c.png" width="300">

#### CE.Locomotion.Score - Locomotion Score, 1 & 2 = okay, 3, 4, & 5 = lame

87.9% are okay, 12.1% are lame

Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/60673083-3f314080-9e77-11e9-8404-f5a7b8260cd1.png" width="300">


#### Hfr.or.Cow - Is it a heifer or a cow?

70.9% are cows, 29.1% are heifers

Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/60673067-36d90580-9e77-11e9-9416-68869788c1fd.png" width="300">

#### Lame - is the cow lame, 1 = yes, 0 = no

87.9% were not lame, 12.1% were lame

Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/60672775-7f43f380-9e76-11e9-8874-39363a6ff349.png" width="300">

#### BS.Month - Month the blood sample was taken

43.7% were taken in the warm months (July, August, September), 56.3% were taken in the cooler months (June, November, December).

Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/65374236-3ddd0c00-dc4d-11e9-98a2-10a837a3658d.png" width="300">


#### Hapto.0.1 - is this cow's haptoglobin level above 0.1? 1 = yes (>0.1), 0 = no (<0.1)

62.9% are below 0.1, 37.1% are above 0.1

Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/61126293-5b9f2f80-a4ac-11e9-83a8-85eead1818a9.png" width="300">

#### Hapto.0.35 - is this cow's haptoglobin level above 0.35? 1 = yes (>0.35) 0 = no (<0.35)

74.3% are below 0.35, 25.7% are above 0.35

Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/61126294-5cd05c80-a4ac-11e9-9411-b2b319ce9566.png" width="300">

#### Hapto.HML - states whether this cow has low, medium, or high hapto levels according to a model, 0 = low (<0.4), 1 = medium (1.599>x>0.4), 2 = high (>1.6)

75.4% have low hapto levels, 5.9% have medium hapto levels, 18.7% have high hapto levels

Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/60672958-e82b6b80-9e76-11e9-82fa-7b54ef43ef92.png" width="300">

#### Hapto.HL - states whether this cow has high or low hapto levels according to a model, medium taken out, 1 = low, 3 = high 

80.1% have low hapto levels, 19.9% have high hapto levels

Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/60672983-f7aab480-9e76-11e9-88dc-98f1670d78c9.png" width="300">

#### BS.NEFA.0.7 - States whether the cow had a high or low blood NEFA level, 1 = >=0.7, 0 = <0.7

80.3% had low NEFA levels, 19.7% had high NEFA levels

Bar Graph:
<img src="https://user-images.githubusercontent.com/52465712/60884932-88560b80-a24e-11e9-8cf9-d54fbbc394e1.png" width="300">

#### BS.BHBA.1.2 - States whether the cow had a high or low blood BHBA level, 1 = >=1.2, 0 = <1.2

80.9% had low BHBA levels, 19.1% had high BHBA levels

Bar Grpah:
<img src="https://user-images.githubusercontent.com/52465712/60884939-8ee48300-a24e-11e9-9fd5-e8394bb98c65.png" width="300">

--------------
## Descriptive Statistics - Numerical Variables

#### BS.NEFA - NEFA levels in the blood (ng/mL)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60725989-b8de3280-9f3a-11e9-8f4f-77699b54a8bd.png" width="300">
 
#### BS.BHBA - BHBA levels in the blood (ng/ml)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60725977-b24fbb00-9f3a-11e9-8ff0-a5275f01f1b5.png" width="300">


#### BS.DIM - number of days after calving that the blood sample took place (days)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60726054-e5924a00-9f3a-11e9-878e-36d0c40e6492.png" width="300">


#### BS.MS.Date.Difference - days difference between the milk sample and the blood sample (days)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60725894-7f0d2c00-9f3a-11e9-8f73-9a4d6b1cfcae.png" width="300">


#### Calving.No - Number of calves this cow has had (calves)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60725961-a5cb6280-9f3a-11e9-9e41-900b37dd6ca6.png" width="300">


#### MS.DIM - How many days after calving was the milk sampled (days)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60725967-abc14380-9f3a-11e9-919c-db598f34b0bc.png" width="300">


#### Milk.Yield - Milk per day (kg)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60726018-cf848980-9f3a-11e9-939d-d95b4c80aaba.png" width="300">


#### MS.Milk.Yield - Kg of milk of that milk sample (kg)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60726086-0064be80-9f3b-11e9-9d8c-c97c43dad357.png" width="300">

#### MS.Fat - % fat of the milk (%)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60726006-c5628b00-9f3a-11e9-9a28-e0aae88ddf28.png" width="300">


#### MS.Protein - % protein of the milk (%)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60725907-86ccd080-9f3a-11e9-96c3-2cef8205f337.png" width="300">


#### MS.Lactose - % lactose of the milk (%)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60725924-92b89280-9f3a-11e9-8cbc-75be71fecdd6.png" width="300">


#### MS.S.Cell.Count - amount of somatic cells in the milk (1000 cells/mL)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60802124-86217d80-a178-11e9-97d0-a089bb14cfba.png" width="300">


#### MS.Urea - % Urea measurement (%)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60726003-bf6caa00-9f3a-11e9-8489-a7bb9f45a7b6.png" width="300">


#### MS.pH - pH measurement of the milk

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60726038-da3f1e80-9f3a-11e9-90fe-98797d8ccafe.png" width="300">

#### MS.Acetone - Acetone in milk (UNIT?)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60726047-e034ff80-9f3a-11e9-8576-c42c8cafd804.png" width="300">


#### MS.BHBA - amount of BHBA in milk (ng/mL)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60725937-99470a00-9f3a-11e9-9ace-d20458ea0ab7.png" width="300">


#### MS.NEFA - amount of NEFA in milk (ng/mL)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60725948-9f3ceb00-9f3a-11e9-84bb-9612b451dcf2.png" width="300">


#### MS.NSFA - Amount of non-saturated fatty acids in the milk (Micro mole/L)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60726028-d57a6a80-9f3a-11e9-9679-f6ab6ee6fd16.png" width="300">


#### MS.MFA - Amount of monounsaturated fatty acids in the milk (Micro mole/L)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60726012-ca273f00-9f3a-11e9-8571-3766d8cafb39.png" width="300">

#### MS.PFA - Amount of polyunsaturated fatty acids in the milk (Micro Mole/L)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60725884-7583c400-9f3a-11e9-920a-074544c58a7f.png" width="300">


#### MS.SFA - Amount of short fatty acids in the milk (Micro mole/L)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60726064-ea56fe00-9f3a-11e9-9a03-3664b39a2f74.png" width="300">


#### MS.Palmeic - Amount of palmeic fatty acid in the milk (Micro mole/L)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60726110-11adcb00-9f3b-11e9-97f8-574bba498c4e.png" width="300">


#### MS.Stearine - Amount of stearine fatty acid in the milk (Micro mole/L)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60725916-8cc2b180-9f3a-11e9-945b-6d319622bf64.png" width="300">

#### MS.Oleic - Amount of oleic acid in the milk (Micro mole/L)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60726094-08246300-9f3b-11e9-82b2-a48a15dc9064.png" width="300">


#### Hapto.Result/Hapto.Log - Amount of Haptoglobin (ng/mL)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60726100-0c508080-9f3b-11e9-85dc-65a5f30496db.png" width="300">


#### CE.Temp - Inner body temperature of the cow (celsius)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60726076-f478fc80-9f3a-11e9-81ec-57e9f16d8ef9.png" width="300">


#### CE.Environ.Temp - Environmental temperature during the clinical evaluation (celsius)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60726071-ef1bb200-9f3a-11e9-8c7f-02a644109bac.png" width="300">


#### CE.Fat.Level - Fat level on the back of the cow (mm)

Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60726082-f93db080-9f3a-11e9-80d3-4d0d2ad8c0f2.png" width="300">

-------------
## Descriptive Statistics - Log Transformations of Skewed Numerical Variables
      
Looking at some of our histograms and bar charts above we can see that some of these variables are highly skewed. So we must log transform some of them.


#### Hapto.Result --> Hapto.Log

Since this variable is skewed very far right, we need to log transform it. 

We first check if there are any 0's in the original data because if a value in the data is 0, the log transformation will fail, there are no 0's so we're are ready to transform the variable.

Log-Transformed Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60805270-e36cfd00-a17f-11e9-91c2-2bb309711f01.png" width="300">


#### BS.NEFA --> BS.NEFA.Log

Since this variable is skewed very far right, we need to log transform it. 

We first check if there are any 0's in the original data because if a value in the data is 0, the log transformation will fail, there are no 0's so we're are ready to transform the variable.

Log-Transformed Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60805246-d3551d80-a17f-11e9-9e30-1b8c8c43dd3c.png" width="300">


#### BS.BHBA --> BS.BHBA.Log

Since this variable is skewed very far right, we need to log transform it. 

We first check if there are any 0's in the original data because if a value in the data is 0, the log transformation will fail, there are no 0's so we're are ready to transform the variable.

Log-Transformed Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60805276-e9fb7480-a17f-11e9-97c2-bd1b78c09803.png" width="300">


#### MS.S.Cell.Count --> MS.S.Cell.Count.Log

Since this variable is skewed very far right, we need to log transform it. 

We first check if there are any 0's in the original data because if a value in the data is 0, the log transformation will fail, there are no 0's so we're are ready to transform the variable.

Log-Transformed Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60805228-c9331f00-a17f-11e9-9165-884484524b90.png" width="300">


#### MS.BHBA --> MS.BHBA.Log

Since this variable is skewed very far right, we need to log transform it. 

We first check if there are any 0's in the original data because if a value in the data is 0, the log transformation will fail, there are no 0's so we're are ready to transform the variable.

Log-Transformed Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60805218-c20c1100-a17f-11e9-9b54-568de9ee0df6.png" width="300">


#### MS.Acetone --> MS.Acetone.Log

Since this variable is skewed very far right, we need to log transform it. 

We first check if there are any 0's in the original data because if a value in the data is 0, the log transformation will fail, there are no 0's so we're are ready to transform the variable.

Log-Transformed Histogram:
 <img src="https://user-images.githubusercontent.com/52465712/60805263-dcde8580-a17f-11e9-8967-49702e26ef22.png" width="300">
 
 
 
 And there we go, all our variables have been log transformed and are ready for the bi-variate analysis.
