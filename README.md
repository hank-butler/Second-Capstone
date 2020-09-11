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

