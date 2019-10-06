# Haptoglobin-Project
----------
## Table of Contents  
[Introduction](#introduction)  

[Importing and Organizing the Data](#importing-and-organizing-the-data)

[Getting To Know Our Variables](#getting-to-know-our-variables)



--------
## Introduction

Future description about the project will be inserted here

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
