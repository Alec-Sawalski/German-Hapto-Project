# Haptoglobin-Project
----------
## Table of Contents  
[Introduction](#introduction)  

[Importing and Organizing the Data](#importing-and-organizing-the-data)

[Getting To Know Our Variables](#getting-to-know-our-variables)



--------
## Introduction

The aim of this data analysis is to quantify the associations between haptoglobin measures in Braunvieh and Fleckvieh cows from a data set with n=712 observations from Germany. A more detailed project description will follow soon.

The data analysis is completed using a combination of R v3.6.1, Tableau and Python 3.6
Reporting is done using knitr and github.

The data analysis and reports have the following structure:
description of the data,  
lists of numeric and factor variables, 
descriptive analysis, 
bivariate analysis, 
multiple variable data analysis using linear regression and logistic regression, and 
k-means clustering to re-assess the cut-off values for haptoglobin


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
