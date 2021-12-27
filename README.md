# Using Multiple Linear Regression to Predict Prices of Homes in King's County, WA

## Project Overview

The goal of this project is to utilize existing data from the King's County housing set from 2014-2015 to predict prices of homes in the area.

### Business Problem

The stakeholder represents a real estate agency that intends to establish itself in King's County. The agency aims to take advantage of predictive modeling to find undervalued homes or characteristics of high-grossing homes to build these kinds of homes. 

### The Data

This project uses the King County House Sales dataset, which can be found in  `kc_house_data.csv` in the data folder in this assignment's GitHub repository. The description of the column names can be found in `column_names.md` in the same folder. 

The dataset has about 21,600 different homes. 

### Methods

First, the data will be cleaned to handle null-values and to handle datatypes. Specifically, 'object' datatypes will be treated in some way to allow for histograms, scatterplots, etc. 

Variables will be examined to evaluate correlation with the target variable, 'price'. Then, variables will be chosen to build a linear regression model with the target variable of price. 

Iterative models will be used to find a multiple linear regression model with an acceptable r-squared value. 

### Model 1

The two highest correlative variables with price are grade and sqft_living, so these variables were chosen to build the first linear regression model. The r-squared value was less than 0.6, and was not deemed acceptable for accurately predicting homes prices.

### Model 2

The same two variables were chosen for this model as the first model, and the grade variable was transformed using dummy variables. This method is very common for dealing with categorical variables. The model was slightly more successful than the first one with a .05 or so increase in r-squared.

### Model 3

This model took advantage of most of the variables offered in the dataset including: bedrooms, bathrooms, sqft_lot, floors, waterfront, view, condition, grade, sqft_basement, yr_built, yr_renovated, zipcode, lat	long, sqft_lot15, price, sqft_living, sqft_above, and sqft_living15. This model also log-normalized the variables that appeared to be log-normally distributed in the initial evaluation of the data. These variables include: 'price', 'sqft_living', 'sqft_above', and 'sqft_living15'. 

This linear regression model achieved an r-squared value of about .78.

### Model 4

This model intended to utilize the same methods of the third model, but this model transformed all categorical variables from model 3 by utilizing dummy variables. This model achieved the same r-squared value as the third model. 

### Conclusions

The best model was able to achieve a fairly high r-squared value of .78, which allows the real estate agency to predict values of homes with some accuracy. However, it probably should not be used as the only decision maker in pursuing business decisions. This model allows the real estate agency to seek out promising homes that are undervalued or to build homes based on various parameters. However, this model should not be used as the only mechanism to determine business decisions. Other research methods should be carried out to ensure that final decisions offer profitable results.