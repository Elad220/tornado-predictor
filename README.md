# Tornado Predictor - Machine Learning
## Project Goal
We decided to research the tornado scale in the US and Europe based on data from 1990-2021.
After data analysis and understanding the correlation between our data features we built a machine learning model which predicts the scale of the tornado based on previous data of length, width, and location (longitude and latitude).
## Research Question 
What will the tornado scale be, given the geographical location, length, and width of previous ones?
Is there a correlation between the width, the length and the scale of the tornado?
Where do tornadoes tend to occur, both in the US and Europe?
## Data Sources
NOAA - https://www.ncdc.noaa.gov/stormevents/choosedates.jsp?statefips=-999,ALL ; https://www.ncei.noaa.gov/pub/data/swdi/stormevents/csvfiles/

ESWD - https://eswd.eu/
## Data Cleaning
After we merged both of the dataframes, we needed to ensure our data sources are fit for exploratory data analysis and visualization later on. 
We needed to convert N,W,E location pointers to latitude and longtitude coordinates, as well as convert the data we acquired from NOAA from yards and miles to KM and meters.
We removed duplicates and took care of missing values.
## EDA and Visualization
### Scale Plots
![image](https://user-images.githubusercontent.com/58027836/148640504-4a66c9fb-b865-497a-92ae-97021db47118.png)
![image](https://user-images.githubusercontent.com/58027836/148640521-fe4e02dd-9843-4503-b180-4f7625f26c50.png)

F5 tornadoes are a rare occurrence and only happen in certain areas, at low quantities.
### Scale by Width/Length
![image](https://user-images.githubusercontent.com/58027836/148640572-01aab2ea-0750-4a22-b691-98a900b03fc4.png)
![image](https://user-images.githubusercontent.com/58027836/148640573-ea99afe7-e7ac-4010-b7a7-f1dea0e1dccd.png)

Also as expected, the higher the scale of the tornado, the longer and wider it is.
### Tornadoes per Time Period
![image](https://user-images.githubusercontent.com/58027836/148640585-a5d143da-b9b6-4c76-9120-a98ccb757cb9.png)
![image](https://user-images.githubusercontent.com/58027836/148640588-3f4c925c-eec3-4ea5-aa9a-16f70699090d.png)

Most of the tornadoes occur during the months of April-June.
### Deaths by Scale
![image](https://user-images.githubusercontent.com/58027836/148640811-673ee630-d964-47b9-b5d2-a6c444142d84.png)
### Deaths by Year
![image](https://user-images.githubusercontent.com/58027836/148640615-6370dcaa-74c4-4995-b62c-073c40a75295.png)

As expected, the stronger the tornado, the higher the number of deaths it causes. In the ”Deaths by Year” graph we can see that in 2011 the number of deaths was the highest because of The 2011 Super Outbreak.
### Geo-location map
![image](https://user-images.githubusercontent.com/58027836/148640629-3ed16230-f94e-4720-a8dc-81a28829b39d.png)

We can see from the map that in the US there is a high concentration of tornadoes in the area of “tornado alley”, since the climate conditions for creating one are ideal there.
Texas, Kansas, Oklahoma, Mississippi and Alabama Illinois have the highest death count out of all the US and Europe (“tornado alley”).

### 3D plot of Deaths by Coordinates
![image](https://user-images.githubusercontent.com/58027836/148640648-13a635a3-99a4-40c0-96a5-98da68e26b4e.png)

## Modeling
In order to prepare the data for modeling, we converted the country column to numerical values, and got rid of irrelevant categorical columns.
We tested the accuracy of 3 different machine learning algorithms on our data. 
We found that Linear Regression algorithm performed the worst out of the 3 algorithms, with 40% accuracy.
The Decision Tree algorithm performed significantly better, with 67% accuracy.
The Random Forest algorithm performed the best out of them, with 70% accuracy (after fine-tuning the hyperparameters).

![image](https://user-images.githubusercontent.com/58027836/148640740-78cafad9-c646-4f93-ab97-124afc10aa83.png)
