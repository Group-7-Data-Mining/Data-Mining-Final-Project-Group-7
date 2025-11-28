# Data Mining Final Project Group 7
## INTRODUCTION
Our project focuses on identifying relationships and patterns between air quality indicators and health outcomes to determine which pollutants have the greatest negative impact on human health. By examining air pollution levels and overall air quality across different regions and time periods, we aim to uncover trends that highlight key environmental risk factors. Through this analysis, we hope to provide data-driven insights that can inform public health initiatives and guide future environmental policy decisions.

## ABOUT THE DATA
The datset we will be using for this project is on Kaggle the link is https://www.kaggle.com/datasets/jsmith51/aqi-relation-to-respiratory-death-rate and it is called AQI Relation to Respiratory Death Rate. There are 20 columns and the timeline is between 2000 to 2019 with locations of counties across the US.
### Shape of the Data
- **Before Pre-processing**: 20 columns and 43,472 rows  
- **After Pre-processing**: 18 columns and 21,028 rows  

The 20 columns are:
- **FIPS, YEAR**: The county FIPS code and the year  
- **location_name**: The County and State  
- **fips**: The County identifying number  
- **year**: The year in which the measurements were taken (2000–2019)  
- **Resp Death Rate**: Death rate due to respiratory illnesses (primary target variable)  
- **Days with AQI**: Total number of days in the year with a recorded Air Quality Index (AQI)  
- **Good Days**: Number of days where AQI less than or equal to 50  
- **Moderate Days**: Number of days where AQI is between 51 and 100 
- **Unhealthy for Sensitive Groups Days**: Number of days where AQI is between 101 and 150  
- **Unhealthy Days**: Number of days where AQI is between 151 and 200 
- **Very Unhealthy Days**: Number of days where AQI is between 201 and 300 
- **Hazardous Days**: Number of days where AQI greater than 300 
- **Max AQI**: Highest AQI value recorded in the county for that year 
- **90th Percentile AQI**: AQI value at the 90th percentile for the year 
- **Median AQI**: Median AQI value for the year
- **Days CO**: Number of days where Carbon Monoxide (CO) was the main pollutant  
- **Days NO2**: Number of days where Nitrogen Dioxide (NO2) was the main pollutant  
- **Days Ozone**: Number of days where Ozone (O3) was the main pollutant  
- **Days PM2_5**: Number of days where Particulate Matter PM2.5 was the main pollutant  
- **Days PM10**: Number of days where Particulate Matter PM10 was the main pollutant  

## METHODS
- For Preprocessing, two columns were removed which was (FIPS, YEAR) and (year) this missing values were checked for and any rows that had missing values like (NaN) were dropped then numeric features were standardizes and the cleaned dataset was checked by listing columns and showing the five first rows.
- Clustering will be the main model of use as it will allow us to see patterns between pollutant concentrations and negative health outcomes. Two clustering models will be created with standardized and non–standardized data. Both models will be compared to see if standardization improves the model’s grouping of data points.
- Linear Regression will be the secondary model that will be used in predicting the number of respiratory and cardiovascular cases and hospital admissions. The goal will be figuring out if one certain type of pollutant is better at predicting the number of negative health impacts.  Multivariable regression is potentially being considered along with creating single-variable models for each type of pollutant. 


## EVALUATION
We will evaluate model performance using:
Regression Metrics: MAE, RMSE, Coefficient of Determination(R-squared) to measure predictive accuracy
Clustering Metrics: Elbow method to find optimal clusters.
Visual Analysis: Scatter plots, heatmaps, and trend visualizations to interpret model insights.
The evaluation will focus on both statistical performance and interpretability – determining which pollutants have the most significant impact on health outcomes. 


## CONCLUSION/STORYTELLING


## IMPACT
