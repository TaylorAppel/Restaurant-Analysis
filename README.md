# Restaurant-Analysis
Performing an in-depth time series analysis on individual entrées, as well as providing weather correlation matrices.

## Project Purpose
The average restaurant's profit margins fall between **3%-5%**. The average amount of food waste in a restaurant is between **4%-10%**. With such low profit margins and potentially high food waste, inventory management is key for a successful restaurant.  

The goal of this project was to perform a time series analysis on individual entrées to detect potentially hidden trends in day-by-day, week-by-week, and month-by-month interest in certain dishes. Additionally, I correlated the daily sales quantities of entrées with daily weather conditions in the location of the restaurant. The purpose of this was to see if, subconsciously, there is a preference for certain dishes given certain weather conditions. Ultimately, I wanted to see if I could use machine learning to identify trends that could otherwise likely go unnoticed, in order to potentially decrease food waste and increase profit margins, as well as offer insights into when certain dishes are more desired over others. 

## Data
I worked with [Redwoods Grill and Bar](http://www.redwoodsgrillandbar.com/) in Chester, NJ, a favorite and often-frequented restaurant of mine growing up. They were able to give me:
* 13 months of daily movement reports via their POS system
* Daily sales quantities on 11 dishes

Additionally, I was able to obtain daily weather conditions during the 13 month period from the [NOAA](https://www.ncdc.noaa.gov/cdo-web/search) so I could correlate the dishes with weather conditions.

## A Single Entrée's Results
As an example of the work performed, I will show the results of their most popular dish, the glazed salmon!

<img src="https://github.com/TaylorAppel/Restaurant-Analysis/blob/master/Salmon%20Pics/Glazed%20Salmon%20Picture.jpg" width="500" height="300">

First, I decided to plot the daily sales quantities to see what I could glean from a quick look.

<img src="https://github.com/TaylorAppel/Restaurant-Analysis/blob/master/Salmon%20Pics/Glazed%20Salmon%20Entree%20Plot.png" width="750" height="500">

Next, using Facebook Prophet, I fit the model, making sure to avoid overfitting, while factoring in seasonalities and accounting for outliers, such as holidays. I then overlay the daily sales plot on top of the model. Note that this also includes a 30-day forecast, so as to potentially predict the sales for the following month.

<img src="https://github.com/TaylorAppel/Restaurant-Analysis/blob/master/Salmon%20Pics/Glazed%20Salmon%20Prediction.png" width="850" height="500">

I also plotted the Root Mean Squared Error for those that my be interested. I used the RMSE to account for the relatively large, undesirable errors.

<img src="https://github.com/TaylorAppel/Restaurant-Analysis/blob/master/Salmon%20Pics/Glazed%20Salmon%20RMSE.png" width="850" height="500">

Next, I plotted my absolute favorite plot, the trends! These graphics show how holidays trend, as well as the overall trend, the weekly trend, and the monthly trend of the dish. 

<img src="https://github.com/TaylorAppel/Restaurant-Analysis/blob/master/Salmon%20Pics/Glazed%20Salmon%20Trends.png" width="600" height="800">

Finally, I wanted to see how weather conditions may affect a diner's preference in dish for the day, if at all. I correlated the daily sales data with the weather data to produce a correlation matrix.

<img src="https://github.com/TaylorAppel/Restaurant-Analysis/blob/master/Salmon%20Pics/Glazed%20Salmon%20Weather%20Correlation.png" width="700" height="500">

## Overall Results
While I only provided the data from one of the dishes (and I'll leave it up to the reader to make their own deductions on what that data tells us), I was able to perform this process on 11 unique dishes, as well as their food, liquor, and total business revenue during this time period. For confidentiality purposes, I can only post information on their individual entrées. But I can provide some fascinating insights!
* Their 2018 liquor revenue showed a positive correlation with bad weather, while their 2019 liquor revenue showed a slightly negative correlation
* The Ribeye and Filet Tips sold best during the warmer months, while the Filet Mignon was the exact opposite
  - All three steak dishes had negative correlations with weather, suggesting people may prefer steak on a nice day when there is no rain or snow
* The Scallops and Crab Cakes sold best in the colder months, whereas the Salmon and Seafood Risotto sold best in the warmer months
* The Pork Chops sold best around Thanksgiving and Christmas/New Years but had a surprisingly negative correlation with snow

I found this project to be really fascinating, and I am looking forward to working with more restaurants to discover hidden trends that were revealed from this experiment, as well as incorporate any other information that may be useful to better these results. Thanks for checking out this project of mine!
