# Haptoglobin-Project
----------
## Table of Contents  
[Introduction](#introduction)  

[Importing and Organizing the Data](#importing-and-organizing-the-data)

[Getting To Know Our Variables](#getting-to-know-our-variables)

[List of variables](#list-of-variables)

--------
## Introduction

The aim of this data analysis is to quantify the associations between haptoglobin measures in Braunvieh and Fleckvieh cows from a data set with n=712 observations from Germany. A more detailed project description will follow soon.

The data analysis is completed using a combination of R v3.6.1, Tableau v2.0 and Python 3.6. 
Reporting is done using knitr and github.

The data analysis and reports have the following structure:
description of the data,  
lists of numeric and factor variables, 
descriptive analysis, 
bivariate analysis, 
correlogram,
multiple variable data analysis using linear regression and logistic regression, and 
k-means clustering to re-assess the cut-off values for haptoglobin.

A brief demonstration of the Python 'pandas profiling' data exploration is added to this data analysis in a separate folder.


--------
## Importing and Organizing the Data

To start our data analysis we first need to import and format our data. 


During the formatting process, we reformatted and created several variables:
- Created a Lameness variable from our Locomotion Score variable
- Re-leveled the Stomach Fullness variable so it only had two levels (0 - normal, 1 - abnormal)
- Created a Blood Sample NEFA cutoff value variable from the regular Blood Sample NEFA variable (cutoff was 0.7)
- Created a Blood Sample BHBA cutoff value variable from the regular Blood Sample BHBA variable (cutoff was 1.2)
- Re-leveled the Month the Blood Sample was taken variable so it only had 3 levels


This completes the formatting process

-------
## Getting To Know Our Variables

Our data have 712 observations and 58 variables. 

These variables consist of:
- 29 Numerical Variables: 
      BS.NEFA, BS.BHBA, Calving.No, MS.DIM, Milk.Yield, MS.Milk.Yield, MS.Fat, MS.Protein, MS.Lactose, MS.S.Cell.Count, MS.Urea, MS.pH, MS.NSFA, MS.Acetone, MS.BHBA, MS.MFA, MS.PFA, MS.SFA, MS.Palmeic, MS.Stearine, MS.Oleic, MS.NEFA, Hapto.Result, CE.Temp, CE.Environ.Temp, CE.Fat.Level, BS.DIM, BS.MS.Date.Difference and Hapto.Log
      
- 23 Factor Variables: 
      CowID, Farm.No, Farm.Name, Cow.Breed, CE.Skin.Dehydration, CE.Stom.Tension, CE.Stom.Layering, CE.Stom.Fluid.Movement, CE.Stom.Ping, CE.Waste.Consistency, CE.Waste.Digestion, CE.Locomotion.Score, CE.Stom.Noise.Freq, Hfr.or.Cow, Hapto.0.1, Hapto.0.35, Hapto.HML, Hapto.HL, CE.Lame, BS.Month, BS.BHBA.1.2, BS.NEFA.0.7, and CE.Stom.Fullness
      
- 9 POSIX Variables for Dates: 
      BS.Date, Cow.Birth.Date, Exit.Date, MS.Date.Taken, Calving.Date, MS.Date.Analyzed, CD_DATE, and MS.Time.Taken   
      
-------
# List of variables
and additional variables generated for the analysis
```r
####### Getting to know the Variables #########

#ISO - Cow identification Number (2.76e+14)
#BLOOD_DATE - Date the blood sample was taken ("2018-02-06")
#FARM_NO - Farm number (1.42e+10)
#FARM_NAME - Farm name ("Stadler)
#BIRTH_DATE - Birth date of the cow ("2015-09-07")
#BREED - Number which represents a breed (01)
#EXIT_DATE - Date cow died, was removed, or was sold ("2018-07-09")
#BLOOD_NEFA - NEFA levels in the blood (ng/mL) (0.24)
#BLOOD_BHBA - BHBA levels in the blood (ng/mL) (0.71)
#SAMPLE_DATE - Milk sample date ("2018-02-05")
#SAMPLE_TIME - What time the milk sample was taken ("08:07:00")
#MILK_CALVING_DATE - Calving date ("2017-12-31")
#MILK_CALVING_NO - How many times has the cow had a calf (1)
#MILK_DIM - Number of days after calving the milk was sampled (36)
#MPR_DATE - Date when lab analyzed milk sample ("2018-02-08")
#MILK_YIELD - Milk/day in kg (26.1)
#MILK_YIELD_SAMPLE - How much milk there was in that sample in kg (26.1)
#MPR_FAT - %Fat of the milk (6.18)
#MPR_PROT - %Protein of the milk (3.21)
#MPR_SCC - Somatic cell count in thousand cells/mL in the milk (226)
#MPR_LACTOSE - %lactose in the milk (4.82)
#MPR_UREA - %urea found in urine (waste) (26)
#MPR_PH - pH of milk sample (6.61)
#MPR_NSA - Amount of non-saturated fatty acids (Micro Mole/L) (20.5)
#MPR_ACETONE - Amount of acetone in the milk (UNIT?) (50)
#MPR_BHBA - Amount of BHBA in milk (ng/mL) (50)
#MPR_SNSA - Amount of monounsaturated fatty acids (Micro Mole/L) (1.752)
#MPR_PNSA - Amount of polyunsaturated fatty acids (Micro Mole/L) (0.224)
#MPR_SFA - Amount of short fatty acids (Micro Mole/L) (3.93)
#MPR_PALM - Amount of palmeic fatty acids (C16, mixed FA) (Micro Mole/L) (1.57)    
#MPR_STEA - Amout of stearine fatty acid (c18, preformed FA) (Micro Mole/L) (0.75) 
#MPR_OL - Amount ol oleic acid (C18.1, preformed FA) (Micro Mole/L) (1.67)         
#MPR_NEFA - Amount of NEFA in milk (ng/mL) (6.1)
#HAPT_RESULT - Haptoglobin measurement (ng/mL) 
#CD_Date - Clinical evaluation date (UNIT?) ("111218")
#CD_IKT - Cow body temperature in Celsius (38.8)
#CD_Environ_Temp - Environmental temperature in celsius (4.3)
#CD_RFD - Level of fat on the back of the cow (mm) (16)                                      
#CD_Skin_Elas - Skin elasticity of the cow, dehydration measurement, ("phy" - normal, "red" - reduced)               
#CD_BauchDe - Measurement of abdominal tension (stomach ache) ("phy" - normal, "erh" - increased)
#CD_Pans_Sc2 - Measure of how full the stomach is ("norm" = normal, "abnorm" = abnormal)
#CD_Pans_Sch - Layering of the rumen (0 = abnormal layering, 1 = normal layering)
#CD_SA - Movemement of fluid in the stomach ("obb" - normal, "re" - abnormal)
#CD_PA - Ping of the stomach ("obb" - normal, "re" - abnormal)
#CD_Kot_K2 - Waste consistency (thick, normal, thin)
#CD_Kot_Verd - How much has been digested by the cow? ("gut" - normal, "maess" - less than good, "schl" - bad)
#CD_LS - Locomotion Score (1 & 2 - ok, everything else - bad)
#CD_Pans_F - Rumen Frequency ("phy" - normal, "bis_2" - less than 2 contractions/minute bad, "groe_3" - too many contractions bad >3)
#loghapto - log of the hapto measurement (6.39)
#hapto_hilo0.1 - boolean stating if the hapto level is high3er than 0.1 (1 - cow is >0.1, 0 - cow is <0.1)
#hapto_hilo0.35 - boolean stating if the hapto level is higher than 0.35 (1 - cow is >0.35, 0 - cow is <0.35)
#hapto_hml - boolean stating if the hapto level is low, med, or high (2 = clinical >1.6, 1 = subclinical 0.4<x<1.599, 0 = low healthy <0.4)
#hapto_hl_nomed - boolean stating if the hapto level is high or low (1 = low healthy, 3 = clinical)
#DIM_bsample - how many days after calving at which the blood sample was taken
#bSample_MONTH - Month the blood sample was taken (11-2018)
#Lact_cat - stating if the animal was a hfr or a cow
#sample_diff - difference in days between the blood sampling date and the milk sampling date
#Lame - states whether the cow is lame or not (1,2 = 0 not lame, 3,4,5 = 1 lame)
#CD_Pans_Sc2 - rumen score (1,2,3=norm, 4,5=abnormal)
#CD_Kot_K2  - consistency of waste (db, dick = thick, sup,was=thin, mb=normal)
#BS.Month_warm - warm months = 1 (July-Sept), cool months = 0 (June, Oct-Dec)


```

