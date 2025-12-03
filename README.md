# Data Mining Final Project Group 7
## INTRODUCTION
Our project focuses on identifying relationships and patterns between air quality indicators and health outcomes to determine which pollutants have the greatest negative impact on human health. By examining air pollution levels and overall air quality across different regions and time periods, we aim to uncover trends that highlight key environmental risk factors. Through this analysis, we hope to provide data-driven insights that can inform public health initiatives and guide future environmental policy decisions.

## ABOUT THE DATA
The dataset we will be using for this project is on Kaggle, the link is https://www.kaggle.com/datasets/jsmith51/aqi-relation-to-respiratory-death-rate, and it is called AQI Relation to Respiratory Death Rate. There are 20 columns, and the timeline is between 2000 to 2019 with locations of counties across the US.
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
- **Good Days**: Number of days where AQI is less than or equal to 50  
- **Moderate Days**: Number of days where AQI is between 51 and 100 
- **Unhealthy for Sensitive Groups Days**: Number of days where AQI is between 101 and 150  
- **Unhealthy Days**: Number of days where AQI is between 151 and 200 
- **Very Unhealthy Days**: Number of days where AQI is between 201 and 300 
- **Hazardous Days**: Number of days where AQI is greater than 300 
- **Max AQI**: Highest AQI value recorded in the county for that year 
- **90th Percentile AQI**: AQI value at the 90th percentile for the year 
- **Median AQI**: Median AQI value for the year
- **Days CO**: Number of days where Carbon Monoxide (CO) was the main pollutant  
- **Days NO2**: Number of days where Nitrogen Dioxide (NO2) was the main pollutant  
- **Days Ozone**: Number of days where Ozone (O3) was the main pollutant  
- **Days PM2_5**: Number of days where Particulate Matter PM2.5 was the main pollutant  
- **Days PM10**: Number of days where Particulate Matter PM10 was the main pollutant  

## METHODS
- For Preprocessing, two columns were removed, which were (FIPS, YEAR) and (year) these missing values were checked for, and any rows that had missing values like (NaN) were dropped. Then, the numeric features were standardized, and the cleaned dataset was checked by listing columns and showing the first five rows.
- Clustering will be the main model of use as it will allow us to see patterns between pollutant concentrations and negative health outcomes. Standardized data will be used to prevent the model from being sensitive to the sacle differnces from the various parameters   
- Linear Regression will be the secondary model that will be used in predicting the number of respiratory and cardiovascular cases and hospital admissions. The goal will be figuring out if one certain type of pollutant is better at predicting the number of negative health impacts.  Multivariable regression is potentially being considered along with creating single-variable models for each type of pollutant. 


## EVALUATION
We will evaluate model performance using:
- Regression Metrics: MAE, RMSE, Coefficient of Determination(R-squared) to measure predictive accuracy
- Clustering Metrics: Elbow method to find optimal clusters.
- Visual Analysis: Scatter plots, heatmaps, and trend visualizations to interpret model insights.
The evaluation will focus on both statistical performance and interpretability determining which pollutants have the most significant impact on health outcomes. 

*See code for the results of the clustering and regression modeling*

## CONCLUSION/STORYTELLING
Before creating the clustering model, the elbow method was used to find the optimal number of clusters to best represent the data. Unfortunately, plotting the result of the elbow calculations led to no clear ‘elbow’ point which meant that the optimal number of clusters had to be found manually. The K-means clustering method was used to create the model and it was found that 3 clusters are best at representing the key groups within the data. These clusters were based on the counties’ yearly respiratory death rates rates in which they had low or high exposure to air pollution( based on AQI values).

Cluster 0 consisted of yearly respiratory death rates that have had below average AQI days(low air pollution exposure). This cluster suggests that air pollution likely did not have a significant role in the yearly reproductive death rates. However, this does not mean that air pollution can be entirely excluded as a factor in respiratory death rates, but rather shows that the chances of respiratory related death being linked to air pollution is low.  Clusters 1 and 2 consisted of yearly respiratory death rates that have had average to above average AQI days(higher air pollution exposure). Both clusters may look the same as seen in the Respiratory Death Rates vs AQI Days plot, but the differences lie in the level of air pollution exposure and the most dominant types of pollutant they each cluster had. Cluster 1 has most of the respiratory death rates occurring during days classified as good or moderate which suggest that air pollution had a minor role in respiratory related deaths. However, comparing it to cluster 0 does show that the chances of respiratory related death being linked to air pollution is higher. In terms of the most dominant air pollutant type, cluster 1 had above average CO, NO2, Ozone, and PM10 days and below average PM2.5 days. Cluster 2 had significantly more moderate to hazardous days compared to cluster 1. In other words, the chances that respiratory related deaths are related to air pollution is the highest in this cluster. For the most domain air pollutant types, cluster 2 had above average NO2, PM10, and PM2.5 days  and below average Ozone days.

Regression modeling was our next approach to see if a one type of pollutant had a clear edge in predicting respiratory death rates. The results were mixed as individual air quality pollutants had minimal predictive power. PM2.5 was the best at predicting respiratory death rates(see Respiratory Death Rate vs Days PM2.5 regression plot), but it only explained about 1.48% of the variation. When multivariable regression was conducted, the model improved modestly with a 3x improvement compared to the regression based on PM2.5. However, the improved model could only explain 4.57% of the respiratory death rate variation. These key findings in the regression modeling showed that respiratory mortality is influenced more by factors beyond what the air quality metrics examined. This does not mean that air pollution does not cause respiratory illness and/or deaths as the regression analysis shows that the chances of  respiratory complications due to air pollution are not zero.

While our main goal of identifying the most negatively impacting air pollution(PM2.5) was achieved, the results of the regression modeling showed that air pollution likely has a small impact in influencing the yearly respiratory death rates. However, clustering showed that some respiratory death rates are more impacted by air pollution than others. One group of death rates had low exposure to air pollution while the other groups had higher exposure levels with different pollutant types being the most dominant or widespread during a specific year. This proves that there is a credible relationship between respiratory death rates and air pollution which could be revealed better with more yearly data.



## IMPACT
Our project provides meaningful insights by examining public health outcomes through environmental data. While our models show that air quality explains only a small portion of respiratory death rate variation, the patterns we identified can still support public health planning and raise awareness of environmental risks.
Identifying clusters with higher numbers of poor-air-quality days helps highlight regions where pollution may influence health outcomes. These insights can assist local agencies in prioritizing monitoring, interventions, and environmental improvements. The results also reinforce that air quality is only one factor among many that contribute to respiratory health.
However, there is potential for misinterpretation. Low R² values may lead some to incorrectly assume that pollution has little impact, which could weaken environmental protections or overlook communities facing broader socioeconomic or healthcare challenges. There is also a risk of misuse if the findings are treated as definitive, as the limited predictive power reflects gaps in the data—not an absence of environmental harm.
To avoid these issues, our results should be communicated as exploratory and paired with clear explanations of the dataset’s limitations. Future analyses should incorporate additional social and health-related variables to produce more comprehensive and responsible insights.

