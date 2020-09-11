# Prediction AirBNB Prices in Austin, TX

## Problem

AirBNB listings differ based on numerous features such as number of bedrooms, bathrooms, square footage, and proximity to points of
interest. The goal of this project is to predict the relationship a listing's distance to various points of interest has on a listing's
price. 

## Data

The data for AirBNB listings was pulled for InsideAirBNB. You can find the link here:

http://insideairbnb.com/get-the-data.html

The Points of Interest in Austin, TX were taken from Austin's Wikipedia page and their coordinates were retrieved from Google Maps.
You can see the code for retrieving for coordinates here:
https://github.com/hank-butler/Second-Capstone/blob/master/google_maps_test_code.ipynb

## Data Cleaning

The AirBNB data has lots of features that were deemed irrelevant to the target variable of interest, price. After removing the unneeded
features, the dataframe was left with the following features:

* listing id
* neighborhood
* zipcode
* latitude
* longitude
* property_type
* room_type
* bathrooms
* bedrooms
* price

## Feature Engineering

The hypothesis for the project is that a listing's location to popular attractions in Austin will have an effect on the price of the listing. Each listing's latitude and longitude was included in the AirBNB data. In order to calculate the distance from a listing to each point of interest, the coordinates for each point of interest was pulled from Google Maps. Then the Euclidean distance was calculated from a listing to each point of interest. Additionally, the minimum, median, and maxiumu distances from each listing to a point of interest were also calculated.

## Exploratory Data Analysis

A histogram of listing prices showed a heavily right skewed distribution due to highly priced listings.

Boxplots of price were then created to breakdown the distribution of prices by the room type of a listing. The boxplots further showed the outliers.

Scatter plots of the minimum, median, and maximum distance of a listing to a point of interest were also produced to chart the relationship, if any, was apparent.

## Modeling

Linear models were first experimented with but were quickly abandoned due to exceptionally poor performance. Tree based models were then used to predict price. Random Forest Regression, Gradient Boosting Regression, and Extra Trees Regression were all used.

## Model Results

The best performing models were the following:

__Random Forest Regression__

Best Parameters:
* max_depth = 20
* max_features = log2
* n_estimators = 300

Training Set Score:
* 0.804

Test Set Score:
* 0.345

__Gradient Boosting Regression__

Best Parameters:
* max_depth = 20
* max_features = log2
* min_samples_leaf = 10
* n_estimators = 100

Training Set Score:
* 0.686

Test Set Score:
* 0.317

## Model Evaluation

The models were generally overfitting. An exhaustive list of different techniques were used to reduce overfitting including removing features deemed unimportant from previous models (found via the features_importances_ attribute of models), changing different hyperparameters, and removing outliers. Ultimately the price outliers were decided to be kept in due to the fact that they are not an insiginificant part of the dataset and it would be intellectually dishonest to have removed them to simply increase a model's accuracy.

## Business Impact

There is a small relationship between an AirBNB listing's distance from points of interest and a listing's price. However, as judged by the low scores from the models, it does not paint the full picture. This does show that the closer a listing is to various points of interest, it's price should partially reflect that. Thus, new listings with similar features to existing listings can now be more appropriately priced to maximize profit for the host and AirBNB.
