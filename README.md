# Seattle Airbnb Price Prediction

![](https://github.com/emoreno-hub/Seattle_Airbnb_Price_Prediction/blob/main/screenshots/Airbnb-Plus-768x512.jpg)


## Project Motivation
Airbnb is a home-sharing platform that allows homeowners and renters (‘hosts’) to put their properties (‘listings’) online, so that guests can pay to stay in them. Hosts are expected to set their own prices for their listings. Although Airbnb and other sites provide some general guidance, there are currently no free and accurate services which help hosts price their properties using a wide range of data points.
Paid third party pricing software is available, but generally you are required to put in your own expected average nightly price (‘base price’), and the algorithm will vary the daily price around that base price on each day depending on day of the week, seasonality, how far away the date is, and other factors.
Airbnb pricing is important to get right, particularly in big cities like Boston, New York, Seattle where there is lots of competition and even small differences in prices can make a big difference. It is also a difficult thing to do correctly — price too high and no one will book. Price too low and you’ll be missing out on a lot of potential income.
This project aims to solve this problem, by using machine learning to predict the base/accurate price trend for properties in big cities for homeowner or renters. 


## Data Source
* Seattle Airbnb:  https://www.kaggle.com/airbnb/seattle

## Implementation
* Feature analysis
* Data cleaning and preparation
* Model evaluation
* Model recommendation

![](https://github.com/emoreno-hub/Seattle_Airbnb_Price_Prediction/blob/main/screenshots/Avg_Rental_Listing_Price.png)

## Correlation Heatmap Using R^2
A heatmap was created to visualize which features were correlated with price by looking at the attributes of a host, a property, and a review. From the heatmap we can see that several features are highly correlated with a listing price (dependent variable) such as the number of guests a listing accomodates, the number of bedrooms, the number of beds, and the cleaning fee. We can see that some of the independent variables are correlated with one another which indicates multicollinearity. This can be seen when observing the relationship between beds and accomodates or beds and bedrooms or some of the review variables.

![](https://github.com/emoreno-hub/Seattle_Airbnb_Price_Prediction/blob/main/screenshots/Heatmap.PNG)

## Baseline Model: Ordinary Least Squares Regression
To serve as a baseline model before implementing machine learning models, I performed ordinary least squares regression to predict the price of a rental using a few selected features.  The independent features chosen for this model included whether the host is a superhost, number of bedrooms, number of bathrooms, number of reviews, and the review score value.
![](https://github.com/emoreno-hub/Seattle_Airbnb_Price_Prediction/blob/main/screenshots/OLS%20Regression.png)

## Model Pipeline
Data was split using an 80%-20% train-test split.  After splitting the data, the following was performed for each model:
* A pipeline was built to standardize the data
* Depending on the algorithm, polynomial features were added
* 5-fold cross-validation was performed

## Model Evaluation
Several regressors were tested and after evaluation, Random Forest and Multi-Layer Perceptron Neural Network performed the best.
![](https://github.com/emoreno-hub/Seattle_Airbnb_Price_Prediction/blob/main/screenshots/Predictions.PNG)

