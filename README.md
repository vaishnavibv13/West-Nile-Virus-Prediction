# Project 1: SAT & ACT Analysis

## Problem statement

ACT and SAT are standardised test used for college admissions in the United States.Over past few years, ACT (American College Testing) test is widely recognised  than SAT (Scholastic Assessment Test)  for college admissions in the United States.This project will explore in detail the trends of ACT and SAT test conducted in the year 2017 and 2018 and discuss about the improved participation rates of SAT and recommendations to college board.


## Executive Summary
    Data Import & Cleaning
    Exploratory Data Analysis
    Data Visualisation
    

The following four datasets have been used in this project :<br> 
 *[SAT 2017](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/) <br>
 *[ACT 2017](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows) <br>
 *[SAT 2018](https://reports.collegeboard.org/sat-suite-program-results/state-results)<br>
 *[ACT 2018](http://www.act.org/content/dam/act/unsecured/documents/cccr2018/Average-Scores-by-State.pdf) 
	    
These data provide information about the average SAT and ACT scores (Total and section wise ) by state, as well as participation rates, for the graduating class of 2017 and 2018.


### Data Import & Cleaning

This involves importing the datasets and process of detecting and correcting inaccurate records of the data and then replacing, modifying and deleting the coarse data. Renaming the column name of the data to more appropriate names. Merging the two dataset sat_2017 and act_2017 into single dataset **act_sat_2017** and saving the clean data into csv file as **combined_2017.csv**. The same process has been repeated with act_2018 and sat_2018 and merged dataset is called **act_sat_2018** and saving into csv file as **combined_2018.csv**. These two combined dataset have been merged together as a dataset called **final** which is used for exploratory data analysis and visualisation.

### Data Dictionary
**act_sat_2017**

|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|act_sat_2017|Name of the state in USA|
|sat_2017_participation|int64|act_sat_2017|Average Participation rate of students who took sat_2017| 
|sat_2017__evidence-based_rw|float64|act_sat_2017|Average mark of students in Evidence based reading and writing section-	sat_2017|
|sat_2017_Math|float64|act_sat_2017|Average mark of students in Math section -sat_2017|
|sat_2017_Total|float64|act_sat_2017|Average Total mark of students-sat_2017|
|act_2017_participation|int64|act_sat_2017|Average Participation rate of students who took act_2017| 
|act_2017_English|float64|act_sat_2017|Average mark of students in English section act_2017|
|act_2017_Math|float64|act_sat_2017|Average mark of students in Math section act_2017|
|act_2017_Reading|float64|act_sat_2017|Average mark of students in Reading section act_2017|
|act_2017_Science|float64|act_sat_2017|Average mark of students in science section act_2017|
|act_2017_total|float64|act_sat_2017|Average Total mark of students act_2017|


**act_sat_2018**

|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|act_sat_2018|Name of the state in USA|
|sat_2018_participation|int64|act_sat_2018|Average Percentage of students who took sat_2018| 
|sat_2018__evidence-based_rw|float64|act_sat_2018|Average mark of students in Evidence based reading and writing section-	sat_2018|
|sat_2018_Math|float64|act_sat_2018|Average mark of students in Math section -sat_2018|
|sat_2018_Total|float64|act_sat_2018|Average Total mark of students-sat_2018|
|act_2018_participation|int64|act_sat_2018|Percentage of students who took act_2018| 
|act_2018_English|float64|act_sat_2018|Average mark of students in English section act_2018|
|act_2018_Math|float64|act_sat_2018|Average mark of students in Math section act_2018|
|act_2018_Reading|float64|act_sat_2018|Average mark of students in Reading section act_2018|
|act_2018_Science|float64|act_sat_2018|Average mark of students in science section act_2018|
|act_2018_total|float64|act_sat_2018|Average Total mark of students act_2018|

### Exploratory Data Analysis

 Interesting trends is observed by exploring the following data : <br>

  *States with the highest and lowest participation rates in 2017 SAT,2018 SAT,2017 ACT,2018 ACT <br>
  *States with the highest and lowest average total scores in 2017 SAT,2018 SAT,2017 ACT,2018 ACT <br>
  *States with 100% participation on a given test also if they have a rate change year-on-year <br>
  *States with >50% participation on both tests either year <br>
	


### Data Visualization
The following relationship has been graphically visualised: <br>
**Heat-map** - to identify relationships of potential interest <br>
**Histogram**-to read the spread of Participation rates for SAT & ACT (2017 and 2018),Math scores for SAT & ACT (2017 and 2018),Reading/verbal scores for SAT & ACT (2017 and 2018)  <br>
**Scatter plot** -to understand the relationship between SAT vs. ACT math scores for 2017
SAT vs. ACT verbal/reading scores for 2017,
SAT vs. ACT total scores for 2017,
Total scores for SAT 2017 vs. 2018,
Total scores for ACT 2017 vs. 2018<br>
**Box plot**- to understand distribution of data, first and third quartile and outliners in data
the participation rates of ACT and SAT (2017 and 2018 ) has been displayed.<br>	


## Descriptive and Inferential Statistics
It is clearly see that ACT has performed better than SAT in the year 2017 and 2018.But the average participation rate of ACT has gone down from 65% in 2017 to 61% in 2018.On the other hand, SAT has improved from 39% participation rate in the year 2017 to 45% in 2018.Though the average score of ACT(English,Math,Reading,Science and Total) and SAT (Evidence based Reading and Writing,Math and Total) is consistent in the year 2017 and 2018, it is important to note that students are performing better in ACT Science section as minimum score in science has drastically improved from 2.3 to 17 in the year 2018 and in Math section of SAT as minimum score in Math has improved from 468 to 480 in 2018 and the minimum Total score of SAT has improved from 950 to 977.

## Outside Research

Based upon the observations- Colorado, Illinois and Rhode Island have interesting trends in ACT and SAT participation rates.It is seen that the above states have drastically improved their SAT participation rates and dropped ACT participation rates.The increase in the rates of these states is because of the following factors:<br> 
-States have implemented SAT School Day which allows students to take the SAT at their own school, during the school day.<br> 
-SAT pattern has been changed in the year 2016 which fits with common core pattern of the School.

Note :
Nine states—Colorado, Connecticut, Delaware, Idaho, Illinois, Maine, Michigan, New Hampshire, and Rhode Island—and the District of Columbia administered the SAT statewide, which shows participation rates of more than 90%.(https://reports.collegeboard.org/archive/sat-suite-program-results/2017/class-2017-results)

## Conclusions and Recommendations

The ACT and SAT participation distributions roughly mirror each other, with states tending to prefer one test or the other. ACT shows a large group of highly committed states, and a higher participation nationwide.SAT shows a larger group of states with 20-75% participation, as well as a smaller set of highly committed states.The ACT has been doing quite well.The SAT made clear gains in 2018 relative to the ACT.Targeting states similar to 2018, should be promising for the College Board moving forward.


