# Descriptive Statistics

--------------------------
## Table of Contents  

[Descriptive Statistics - Factor Variables](#descriptive-statistics---factor-variables)

[Descriptive Statistics - Numerical Variables](#descriptive-statistics---numerical-variables)  

[Descriptive Statistics - Log Transformations of Skewed Numerical Variables](#descriptive-statistics---log-transformations-of-skewed-numerical-variables)  


---------
## List of all variables in the data set, including the additional variables that were re-coded or generated

Observations: 712
Variables: 72
CowID                  <fct> 276000941090648, 276000951311013, 276000951311013, 276000947406879, 276000944234103, 2760…
Cow.Birth.Date         <date> 2007-10-19, 2016-05-31, 2016-05-31, 2012-08-14, 2010-03-13, 2007-10-19, 2013-05-21, 2011…
Farm.Name              <fct> Stadler, Stadler, Stadler, Stadler, Stadler, Stadler, Stadler, Stadler, Stadler, Stadler,…
Farm.No                <fct> 14184137142, 14184137142, 14184137142, 14184137142, 14184137142, 14184137142, 14184137142…
Cow.Breed              <fct> 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 01, 0…
Cow.Exit.Date          <date> NA, NA, NA, NA, NA, NA, NA, NA, 2018-09-10, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, …
BS.DATE                <date> 2018-11-06, 2018-07-24, 2018-08-07, 2018-12-11, 2018-12-04, 2018-11-13, 2018-08-07, 2018…
BS.Month               <fct> 11-2018, 07-2018, 08-2018, 12-2018, 12-2018, 11-2018, 08-2018, 12-2018, 09-2018, 09-2018,…
BS.MS.Date.Difference  <dbl> 1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 1, 1, 0, 1, 1, 1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 1,…
BS.DIM                 <dbl> 21, 15, 29, 16, 16, 28, 11, 22, 6, 13, 13, 10, 17, 15, 20, 28, 10, 17, 16, 23, 19, 26, 25…
Hapto.Result           <dbl> 597.50, 280.00, 741.50, 280.00, 1903.50, 11584.50, 3850.00, 280.00, 12764.00, 4791.00, 38…
Hapto.Log              <dbl> 6.392754, 5.634790, 6.608675, 5.634790, 7.551450, 9.357423, 8.255828, 5.634790, 9.454384,…
Hapto.0.1              <fct> 0, 0, 0, 0, 1, 1, 1, 0, 1, 1, 0, 1, 1, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 1, 1, 1,…
Hapto0.35              <fct> 0, 0, 0, 0, 0, 1, 1, 0, 1, 1, 0, 1, 1, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 1, 0, 1,…
Hapto.HML              <fct> 0, 0, 0, 0, 0, 1, 0, 0, 1, 1, 0, 0, 2, 0, 0, 0, 0, 0, 0, 0, 2, 0, 0, 0, 0, 0, 0, 2, 0, 1,…
Hapto.HL               <fct> 1, 1, 1, 1, 1, NA, 1, 1, NA, NA, 1, 1, 3, 1, 1, 1, 1, 1, 1, 1, 3, 1, 1, 1, 1, 1, 1, 3, 1,…
BS.NEFA                <dbl> 0.23, 0.68, 0.48, 0.32, 0.33, 0.22, 0.50, 0.47, 0.63, 0.83, 2.08, 0.36, 0.55, 0.32, 0.50,…
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

75.7% are normal, 21.0% are thick, 3.3% are thin

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

#### CE.Stom.Fullness - Measure of how full the stomach is, "norm" = normal, "abnorm" = abnormal

57.8% are normal, 42.2% are abnormal

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
