# King County House Data Analysis
![IMG_0463](https://user-images.githubusercontent.com/108106393/206580830-2085d3e7-d9ce-4def-bd5a-62a63b43b213.JPG)

# Objective
The goal of this project is to analyze a housing dataset from King County, Washington to figure out what specific features drives 
house prices up, create multiple linear regressions of such features to determine which ones have the best correlation with 
house prices. The dataset has to be analyzed, filtered and cleaned and is explained further through the use of visuals. 

# Stakeholders
Beacon clean machine is looking to expand its real estate business in King County, Washington by looking for 
underutilized properties in desirable neighborhoods and building/renovating multi family housing to fully utilize the property
and generate the highest return on investment
  
# Data 
This project uses the King County House Sales Dataset and is located under the data folder in this repository

# Method 
Before analysis of every feature using linear regression, I had to clean and filter the dataset using the zipcode. I used feature engineering to create multiple columns  I wanted to focus on certain zipcodes that contain houses with a low floor to area ratio in desirable neighborhoods. Floor to area ratio is the measurement of the building area to the total area of the lot and this tells me which zipcodes contain underutilized properties that has potential for expansion. I also created a column for zoning which tells me if a certain house is single or multi-family. This column tells me which neighborhoods are dense. The last column I created is the amount of houses sold per month which tells me the best time to list a house for selling/renting purposes. After filtering the dataset, I filled in Nan values and transformed categorical variables to ordinal so I can plot it against price. I also removed one particular outlier with 33 bathrooms and dropped certain columns. 

I used "price" as the target variable, there are a lot of possible features that can be used as a predictor for the target variable to create a linear regression model with a good coefficient of determination percentage. My base model was the target variable and I used 'zipcode', 'bathrooms', 'sqft_living', 'sqft_lot', 'waterfront', 'view', 'condition', 'grade', 'sqft_basement', 'FAR' as my predictors and derived a 0.74 coefficient of determination and the best linear regression I created had a coefficient of determination of 0.85. It included every feature from the base model but I hot encoded every zipcode.

# Graph of Zipcodes with the best FAR in desirable neighborhoods and average price of houses in said zipcodes
![1234](https://user-images.githubusercontent.com/108106393/206740272-a04f6740-398f-41b9-86c1-470deb5386bd.png)
![5678](https://user-images.githubusercontent.com/108106393/206740312-02ab3b1f-ade4-47f9-87bb-0e9b6b20a435.png)

# Zoning vs Price
![zoningvsprice](https://user-images.githubusercontent.com/108106393/206797892-0bfb1e87-0afc-4b90-8787-a4e220ec5a3e.png)

# Number oh Houses Sold per Month
This graph shows the total amount of houses sold in a month, it also shows when the best time to list a property for selling or rental purposes. Summer is usually the peak of houses being sold or rentals getting rented out. So it's ideal to have it listed at least a week before the start of summer. This graph also tells us if it's a buyers market or a sellers market. For landlords and sellers, it's best to list properties when it's a sellers market or when the demand for houses is higher than the supply oh houses available. 

![numbereohousessold](https://user-images.githubusercontent.com/108106393/206797978-416f8b0b-8cf8-4190-be75-9ca20d859b5a.png)

# Base Model with a 0.74 coefficient of determination

Coefficients:
Square foot living: 102.00
Bathroom: 806.09
Waterfront: 704363
View: 78246.68
Grade: 74083.12
FAR: 63634.91
![newplot (2)](https://user-images.githubusercontent.com/108106393/206739178-7f66462e-3b11-44a8-a366-f844bbe2e90c.png)

# Linear Regression Model with 0.85 coefficient of determination
![newplot (1)](https://user-images.githubusercontent.com/108106393/206739926-28727bf5-91c7-4bdb-a621-57442f27ff83.png)

# Recommendations
1. Use a more current house dataset that contains the most recent increase in appraised value every year to see which zipcodes contain the highest percentage increase in house and land value
2. Find a foreclosed houses dataset to add to the current house dataset given to look for auctioned houses sold by the city 
(this could potentially give the highest ROI if applied to the filtered dataframe used)
3. List house for selling/renting purposes during summer

