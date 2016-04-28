# migrainedataviz
MyMigraine User Data Visualization
Link: http://sunnyliyanbo1357.github.io/migrainedataviz/

### Dataset
The dataset I used is generated from three independent data sources: my own health data from my iPhone HealthKit, NYC weather data from NOAA National Centers For Environmental Information, and my migraine severity data from my migraine diary. 

HealthKit is a iPhone user health data pool that collects health data from iPhone sensors and any health apps that integrate with it. Data types include but not limited to heart rate, steps, body temperature, blood glucose, body fat percentage, vitamins. Here I only use the heart rate and steps that collected from Apple Watch and iPhone sensor, for these two are the more common and complete data sources. The period of data is from July 29, 2015 to present. 

NOAA National Centers For Environmental Information (www.ncdc.noaa.gov) provides free online climate data in any particular locations. I ordered the weather data since July 29, 2015 that collected from New York Central Park OBS Belvedere Tower. It provides the highest and the lowest temperature, wind speed and level, snow, rain, and other descriptions. The variables I used are TMAX (maximum daily temperature), TMIN (minimum daily temperature), and AWND (average daily wind). The most recent data I got is until April 19, 2016.

My migraine severity data comes from my own migraine diary. It records most of my migraine date and severity (from level 1 to 4). I logged the severity manually to the dataset.

I chose these datasets because first they are free and legal, and second these are real migraine patient novel data that suggest patient living status, and more importantly, these are important triggers that may have direct or indirect impact on migraines. 

### Questions 
What might be my migraine trigger, temperature difference, wind, or exercise? What is the pattern of my migraine in terms of the date in a week? A month? A year? Does exercise help to reduce my migraine frequency or severity? 

### Visualization Tool
D3 on JavaScript with HTML and CSS. The code I wrote is referenced from Mike Bostock’s Block Calendar View (http://bl.ocks.org/mbostock/4063318).

### Transformation of the Dataset
The HealthKit data I imported from my iPhone includes date and time, heart rate, and steps. I formated the date and time as “YYYYMMDD”, and the titles of the parameters as “HR” and “Steps”. 

The weather data I ordered includes 20 parameters. I retrieved only the date, TMAX, TMIN and AWND and combined with HealthKit data. I also renamed “AWND” as “Wind” so that it can be better understood. Since neither the highest or the lowest air temperature alone means anything to migraine, I showed the difference of TMAX and TMIN as “TempDiff” instead. 

The migraine data is manually logged into the data set from my migraine diary.

As a result, I have a data set that includes “DATE”, “HR”, “Steps”, “TMAX”, “TMIN”, “Wind”, and “Migraine” in the time period of 20150729 to 20160419.

### Story Telling 
In order to show trigger-trigger and trigger-migraine relationships, all these data from different parameters should be shown in the same page. Also, for each parameter, daily data should be comparable and the trend in a year should be clear. Therefore, the best way to emphasize on both parameter relationships and yearly trend is the d3 calendar view. 

Also, the intensity of the color represent the range of the data. The darker the color, the higher value of the data on the specific day. 
Therefore, for each parameter, the visualization shows that my heart rate was comparatively higher in winter than last year summer; the New York air temperature differs the most in spring and autumn; wind was stronger this year than 2015; I walked more during the weekends than weekdays; my severe migraines happened mostly during the weekdays, and my migraine frequency was higher this spring.

Comparing between parameters, the visualization shows that my migraines happened mostly when my steps was low. And the migraine frequency seems to correspond with the wind and temperature difference, as the stronger the wind, and the more difference in daily highest and lowest air temperature, the more likely that I have a migraine. 

As a result, the visualization suggested that my migraine is very likely to be triggered by weekday workload, and possibly also triggered by the wind and air temperature difference. More outdoor walking may help to reduce the severity of my migraine. 



