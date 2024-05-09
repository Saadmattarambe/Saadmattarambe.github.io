**ITEM 1: INTRODUCTION**
This case study is part of the Capstone Project of Google Data Analytics Professional Certificate. To complete the analysis, I have used the 6 steps of Data Analysis.

By: Sa’ad Abubakar Mattarambe				Date: January 2024

**1.0	Statement.**
I am a junior data analyst working in the marketing analyst team at Cyclistic: a bike-share company in Chicago. It was launched in 2016 and has successfully grown to a fleet of 5,824 bicycles that are geo-tracked and locked into a network of 692 stations across Chicago. Until now, the company’s marketing strategy relied on building general awareness and appealing to broad consumer segments. One approach that helped make these things possible was the flexibility of its pricing plans: single-ride passes, full-day passes, and annual memberships. Annual membership customers are referred to as members while single day or full day membership customers are referred to as casual riders. The company’s finance analyst concluded that annual members are much more profitable than casual riders, Although the pricing flexibility helps Cyclistic attract more customers. However, the Director of marketing, Moreno believes that maximizing the number of annual members will be key to future growth to the company. So, rather than creating a marketing campaign that targets all-new customers, Moreno believes there is a very good chance to convert casual riders into members. She notes that casual riders are already aware of the Cyclistic program and have chosen Cyclistic for their mobility needs. Therefore there is a need to understand how casual riders and annual members use cyclistic bikes differently in order to design a new marketing strategy to convert casual riders into annual members. However, the new marketing strategy must be approved by the company’s executives hence the need to provide recommendations with simple and clear data insights and visualizations.

**1.2 Goal**

Understand how casual riders and annual members use Cyclistic bikes differently. Then design marketing strategies that will aim at converting riders into annual members.

**1.3 Objectives**
1.	How do annual members and casual riders use Cyclistic bikes differently?
2.	Why would casual riders buy Cyclistic annual memberships?
3.	How can Cyclistic use digital media to influence casual riders to become members?
   
**1.4 Task**
1.	Draft a clear statement of the business task.
2.	State data sources used.
3.	Document of cleaning and manipulation of the data.
4.	Provide a summary analysis.
5.	Visualizations key findings.
6.	Draft Top three recommendations based on analysis conducted. 


**ITEM 2: DATA SOURCE**

**2.1 Information on Data Source**
1.	The data is stored in cloud on this link: https://divvy-tripdata.s3.amazonaws.com/index.html and stored in ZIP files.
2.	Riders personal information were barred from being used.
3.	The data is downloaded and stored in csv format.
4.	I checked and verify that the Data ROCCC.
5.	The data is organized to my liking and no further organizing needed.
6.	There are no issues of bias or credibility as the data is licensed and made available to the public.

   
**ITEM 3: PROCESS.**

I choose R to clean, transform and analyze the data.      

**3.1 Importing the data:**
I have saved the data in documents and named the folder “Raw_csv”


3.1 Importing the data: I have saved the data in documents and named the folder “Raw_csv”
#_____LOAD THE NECESSARY PACKAGES AND LOAD LIBRARIES
install.packages("tidyverse")
install.packages("lubridate")
install.packages("ggplot2")
install.packages("dplyr")
install.packages("hms")
install.packages("data.table")
install.packages("scales")

library(tidyverse)
library(lubridate)
library(ggplot2)
library(dplyr)
library(hms)
library(data.table)
library(scales)

#______SET THE DIRECTORY TO OBTAIN AND IMPORT THE DATA USING “setwd”
setwd("C:/Users/NRC-NG User1/Documents/Raw_csv")     

#______import the data using read code.
Jul_2023   <- read_csv("202307-divvy-tripdata.csv")
Jun_2023  <- read_csv("202306-divvy-tripdata.csv")
May_2023 <- read_csv("202305-divvy-tripdata.csv")
Apr_2023  <- read_csv("202304-divvy-tripdata.csv")
Mar_2023 <- read_csv("202303-divvy-tripdata.csv")
Feb_2023  <- read_csv("202302-divvy-tripdata.csv")
Jan_2023   <- read_csv("202301-divvy-tripdata.csv")
Dec_2022  <- read_csv("202212-divvy-tripdata.csv")
Nov_2022  <- read_csv("202211-divvy-tripdata.csv")
Oct_2022   <- read_csv("202210-divvy-tripdata.csv")
Sep_2022   <- read_csv("202209-divvy-tripdata.csv")
Aug_2022   <- read_csv("202208-divvy-tripdata.csv")

#_____MERGE THE 12 MONTH’S DATA INTO A SINGLE DATAFRAME FOR A WHOLISTIC CLEANING, TRANSFORMATION AND ANALYSIS. AND FURTHER NAME THE DATA FRAME AS “all_trips” USING THE “bind_rows” 
all_trips <- bind_rows(Jul_2023, Jun_2023, May_2023, Apr_2023, Mar_2023, Feb_2023, Jan_2023, Dec_2022, Nov_2022, Oct_2022, Sep_2022, Aug_2022)


3.2 Checking the data for errors.
#_____HAVE A GLIMPSE OF THE DATAFRAME TO GET SUMMARY OF THE DATA FRAME.
Head(all_trips) 
str(all_trips)
summary(all_trips)

#_____TO GET THE DETAILED SUMMARY OF THE DATAFRAME.
library(skimr)
skim_without_charts(all_trips) 

#_____CREATE A NEW COLUMN TO CALCULATE RIDE LENGTH BY; SUBTRACTING “ended_at” FROM “started_at” AND THEN CONVERTED THE UNITS TO MINUTES 



**ITEM 4: SUMMARY OF ANALYSIS **
4.1 First, let’s conduct descriptive analysis of the data.
#_____CALCULATE TOTAL RIDES.
nrow(all_trips) 

#_____MEAN, MEDIAN, MIN AND MAX RIDES.

**ITEM 5: VISUALIZATIONS AND KEY FININGS**
5.1 #_____TOTAL RIDES PER YEAR BY MEMBER/CASUAL
![image](https://github.com/Saadmattarambe/Saadmattarambe.github.io/assets/155629992/830732b3-3fe0-4126-951c-35d9e00825a2)



5.2 #_____RIDES PER MONTH BY MEMBER/CASUAL

![image](https://github.com/Saadmattarambe/Saadmattarambe.github.io/assets/155629992/717c0f36-502d-4fa7-b43a-02cd525bffa8)


