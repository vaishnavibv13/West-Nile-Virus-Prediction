# West Nile Virus Prediction for Chicago

## Scope
1. Background
2. Problem Statement
3. Executive Summary
4. Project Planning
5. Intro to Datasets
6. EDA
7. Feature Engineering
8. Modeling
9. Cost-Benefit Analysis
9. File List

## Background
West Nile Virus is most commonly spread to humans through infected mosquitos. Due to the recent epidemic in City of Chicago, Chicago Department of Public Health (CDPH) had established a surveillance and control program. The program entails setting mosquito traps, testing for WNV and spraying of airborne pesticides in the city.

Every year from late-May to early-October, CDPH setup mosquito traps scattered across the city. Every week from Monday through Wednesday, these traps collect mosquitos, and the mosquitos are tested for the presence of West Nile virus before the end of the week. The test results include the number of mosquitos, the mosquitos species, and whether or not West Nile virus is present in the cohort.

Centres for Disease Control and Prevention (CDC) has engaged Disease and Treatment Agency (DATA) for the following services:
- To conduct a review on the surveillance and control program through data analytics
- To conduct a cost-benefit analysis on the annual cost projections for various levels of pesticide coverage and  the effect of these various levels of pesticide coverage

DATA is responsible to analyze the mosquito trap location, testing and spraying datasets given by CDPH, and weather datasets given by National Oceanic and Atmosphere Administration (NOAA) to predict whether or not West Nile virus is present, for a given time, location, and species.

## Problem Statement

- To build a classification model with high sensitivity and specificity on the presence of WNV at a specific place and time so as to aid CDC in deriving an effective pesticide deployment plan
- To conduct a cost-benefit analysis on the annual cost projections for various level of pesticide coverage and the effects of these various levels of pesticide coverage

## Executive Summary
DATA has completed the review on surveillance and control program through data analytics as well as the cost-benefit analysis. DATA has built and delivered a classification model with high sensitivity and specificity, achieving a ROC AUC score of ~0.75 in Kaggle. The EDA, modeling and cost-benefit analysis arrives at the following conclusion:
- EDA shows that while it is true that dry condition (low wet bulb temperature) and hot temperature is more favorable for presence of WNV.
- High mosquito counts (approx 1500) shows that the presence of WNV is almost guaranteed
- 2 species (CULEX PIPIENS & CULEX PIPIENS/RESTUANS) of mosquitos exceeded the count of 1000
- WNV is only seen in 3 mosquito species: CULEX PIPIENS/RESTUANS, CULEX PIPIENS and CULEX RESTUANS
- High likelihood that not all species of mosquitoes found in the trap will carry WNV
- Effectiveness of current pesticide deployment plan might not be optimal as the emphasis is not on areas with high mosquito counts or presence of WNV.

CDC and CDPH to support the following recommendations:
- New pesticide deployment plan which places more emphasis on areas with high mosquito counts or presence of WNV
- DATA to further narrow the study to the control of CULEX PIPIENS & RESTUANS mosquitoes for a period of 12 months as the EDA shows these are the main carriers of WNV
- Attachment of 2 x DATA Warehouse engineers to aid in the data collection process for spray datasets for a period of 12 months

## Project Planning
- Project Milestones: https://github.com/Zoeychengg/project_4/milestones
- Task Breakdown: https://github.com/Zoeychengg/project_4/projects/1

## Intro to Datasets
Datasets provided:
- Data of 2007, 2009, 2011 & 2013
- Data to predict on: 2008, 2010, 2012 and 2014
- Weather data: 2007 to 2014
- Spray data: 2011 & 2013

## EDA
The following shows the EDA process:
1. Rolling average of 30 days for weather data
2. Explore the relations between WNV and Month, Temperature, Number of Mosquitos
3. Using ANOVA to see if the means between the presence of WnvPresent for the various features differ statistically
4. Visualizing Number of Mosquitos feature over Month
5. Mosquitoes Species Analysis

The following shows a summary on the EDA findings:
- Identified a possible seasonal trend of mosquito breeding, usually picks up in July and start decreasing after September/October
- Investigated the claim that hot and dry conditions are more favorable for WNV. Verified that while the condition of dry (low wet bulb temperature) is true, and EDA shows that higher temperature leads to higher chances of WNV presence.
- High count of mosquitos (approx 1500) shows that the presence of WNV is almost guaranteed
- 2 species (CULEX PIPIENS & CULEX PIPIENS/RESTUANS) of mosquitos ever exceeded the count of 1000. It might be worth focusing on the control of these 2 species in the future
- WNV is only seen in 3 mosquito species: CULEX PIPIENS/RESTUANS, CULEX PIPIENS and CULEX RESTUANS
- High likelihood that not all species of mosquitoes found in the trap will carry WNV

## Feature Engineering
The following shows the feature engineering process:
1. Location Clustering of traps
2. Feature Elimination
3. Encoding of Categorical Features
4. Data Scaling
5. Handling of imbalance WNV present data via SMOTE

## Modeling
The following shows the modeling process:
1. Train-Test Split
2. Hyperparameter Tuning
3. Cross Validation
4. Test Prediction
5. Model Evaluation

The following shows the models built and the corresponding ROC AUC score used for model evaluation:
|Model |Cross Validation |Test |
|:-----|:-----|:-----|
|Logistic Regression | 0.893 | 0.737 |
|Random Forest | 0.972 | 0.714 |
|XGBoost | 0.984 | 0.635 |

The Logistic Regression model was selected for Kaggle submission, yielded a ROC AUC score of approximately 0.75.

## Cost-Benefit Analysis
The following shows the Cost-Benefit Analysis process:
1. Clustering the locations of spray dataset based on the clusters of aggregated train and weather dataset.
2. Removing the multicollinear features from the datasetset.
3. Built a logistic regression model to study the effect of spray and other explanatory features on WNV.

The cost-benefit analysis explored the various features and their correlation with West Nile virus. Based on correlation, the number of mosquitoes is 1 times as likely to detect virus. However, it is surprising to see that from the data given, spraying does not have a significant impact on virus detection.

The dataset provided gives information on different set of locations (in terms of latitude and longitude) for Spray and trap. This makes it difficult to identify the mosquito trap where virus is detected was sprayed. More information on county-wise spray and trap locations might be helpful in analyzing the relationship between spray and virus detection.

The product used to control the adult mosquitoes in Chicago, Zenivex™, is applied at a rate of 1.5 fluid ounces per acre. It is approved for use by the U.S. Environmental Protection Agency and is used to control mosquitoes in outdoor residential and recreational areas.

**As per our calculations, the total estimated cost for Mosquito control spray is $6877.7 for an estimated area of 7037.14 acres.**

The benefit could be in terms of a decrease in the number of mosquitoes post-spray. Also, significant number of deaths are caused because of West Nile Virus in Chicago. The city is ranked fourth in 2019 in a list of metro areas as one of the Mosquito Hot Spots in the nation (https://patch.com/illinois/chicago/chicagos-mosquito-problem-among-worst-nation).   

The benefit can also be measured in terms of savings in the medical expenses, as fewer people will be infected with mosquitos, people taking few or no medical leaves, among others. **A typical household with employer health coverage spends about USD 800 a year in out-of-pocket costs, not counting premiums, according to research from the Commonwealth Fund. At the high end of the range, those costs can top USD 5,000 a year** (https://www.chicagobusiness.com/health-care/health-insurance-costs-surpass-20000-year-hitting-record).   

## File List

### Assets File Descriptions
**train.csv, test.csv - the training and test set of the main dataset.**    
- The training set consists of data from 2007, 2009, 2011, and 2013.
- The test set used to predict the results are from 2008, 2010, 2012, and 2014.

|Feature |Description |
|:-----|:-----|
| Id | The id of the record (not shown in train dataset) |
| Date | Date that the WNV test is performed |
| Address | Approximate address of the location of trap. This is used to send to the GeoCoder |
| Species | The species of mosquitos |
| Block | Block number of address |
| Street | Street name |
| Trap | Id of the trap |
| AddressNumberAndStreet | Approximate address returned from GeoCoder |
| Latitude | Latitude returned from GeoCoder |
| Longitude | Longitude returned from GeoCoder |
| AddressAccuracy | Accuracy returned from GeoCoder |
| NumMosquitos | Number of mosquitoes caught in this trap (not shown in test dataset)|
| WnvPresent | 1: West Nile Virus is present   <br/>  0: West Nile Virus not present (not shown in test dataset)|   

**spray.csv**
- GIS data of spraying efforts in 2011 and 2013   

|Feature |Description |
|:-----|:-----|
| Date | Date of the spray |
| Time | Time of the spray |
| Latitude | Latitude of the spray |
| Longitude | Longitude of the spray |   

**weather.csv**
- weather data from 2007 to 2014     

|Feature |Description |
|:-----|:-----|
| Station | 1: Chicago O' Hare International Airport (Lat: 41.995 Lon: -87.933 Elev: 662 ft. above sea level) <br/> 2: Chicago Midway International Airport (Lat: 41.786 Lon: -87.752 Elev: 612 ft. above sea level) |
| Time | Time of the spray |
| Latitude | Latitude of the spray |
| Longitude | Longitude of the spray |  
| Date | Date |
| Tmax | Maximum Temperature in Fahrenheit|
| Tmin | Minimum Temperature in Fahrenheit|
| Tavg | Average Temperature in Fahrenheit|
| Depart | Departure from Normal Temperature in Fahrenheit|
| DewPoint | Average Dew Point in Fahrenheit where the atmospheric temperature (varying according to <br/> pressure and humidity) below which water droplets begin to condense and dew can form.|
| WetBulb | Average Wet Bulb temperature in Fahrenheit read by a thermometer covered in <br/>  water-soaked cloth (wet-bulb thermometer)|
| Heat | Heating days (Season begins with July) |
| Cool | Cooling days (Season begins with January)|
| Sunrise | 24 hours clock, calculated not observed |
| Sunset | 24 hours clock, calculated not observed |
| CodeSum | +FC - Tornado//Waterspout <br/> FC - Funnel Cloud <br/> TS - Thunderstorm <br/> GR - Hail <br/> RA - Rain <br/> GS -  Small Hail &/Or Snow Pellets <br/> PL - Ice Pellets <br/> IC - Ice Crystals <br/> FG+ - Heavy Fog (FG & LE.25 Miles Visibility) <br/> FG - Fog <br/> BR - Mist <br/> UP - Unknown Precipitation <br/> HZ - Haze <br/> FU - Smoke <br/> VA -  Volcanic Ash <br/> DU - Widespread Dust <br/> DS - Duststorm <br/> PO - Sand/Dust Whirls <br/> SA - Sand <br/> SS -  Sandstorm <br/> PY - Spray <br/> SQ - Squall <br/> DR - Low Drifting <br/> SH - Shower <br/> FZ - Freezing <br/> MI - Shallow <br/> PR - Partial <br/> BC - Patches <br/> BL - Blowing <br/> VC - Vicinity ( - Light, + Heavy) <br/> "No Sign" Moderate


**sampleSubmission.csv**   

- a sample submission file in the correct format   


### Dataset File Descriptions

**Final dataset used for modelling**  

| Feature             | Type          | Remarks                                                 |
|:--------------------|:--------------|:------------------------                                    |
| Species             | Categorical   | OneHotEncoded the different species                         |
| Cluster             | Categorical   | Cluster created by pairing Latitude and Longitutde together |
| Months              | Categorical   | OneHotEncoded the different months present                  |
| Tmax                | Numerical     |                                                             |
| Tmin                | Numerical     |                                                             |
| Tavg                | Numerical     |                                                             |
| Depart              | Numerical     |                                                             |
| DewPoint            | Numerical     |                                                             |
| WetBulb             | Numerical     |                                                             |
| Heat                | Numerical     |                                                             |
| Cool                | Numerical     |                                                             |
| PrecipTotal         | Numerical     |                                                             |
| StnPressure         | Numerical     |                                                             |
| SeaLevel            | Numerical     |                                                             |
| ResultSpeed         | Numerical     |                                                             |
| ResultDir           | Numerical     |                                                             |
| AvgSpeed            | Numerical     |                                                             |
| WnvPresent          | Categorical   | Target variable - y                                         |

### Codes File Descriptions

1. Cleaning 1 (Spray), 2 (Weather) and 3 (Train-Test)
2. EDA
3. Modeling
4. Cost-Benefit Analysis
