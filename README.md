# Project Name
Bike Demand Prediction for BoomBikes
A bike-sharing system is a service in which bikes are made available for shared use to individuals on a short term basis for a price or free. Many bike share systems allow people to borrow a bike from a "dock" which is usually computer-controlled wherein the user enters the payment information, and the system unlocks it. This bike can then be returned to another dock belonging to the same system.

## Overview
This project focuses on predicting the demand for shared bikes for BoomBikes, a US bike-sharing provider, particularly in the post-Covid-19 scenario. The goal is to identify significant factors affecting bike demand in the American market and to quantify their impact.

## Problem Statement
In the wake of Covid-19, BoomBikes aspires to understand and prepare for the expected demand for shared bikes. The company aims to identify key variables influencing this demand to outperform competitors and maximize profits.


## Data Preparation
Import and Inspection: Loaded the dataset, examined its structure and variables.
Dropping Irrelevant Variables: Removed 'dteday', 'casual', 'registered', and 'instant' due to redundancy and irrelevance.
Mapping Values: Transformed categorical variables like 'season', 'weathersit', 'weekday', 'mnth', and 'yr' into readable formats.
Dummy Variable Creation: Generated dummies for categorical variables for linear modeling.

## Analysis
## Univariate Analysis
Observed distribution of variables like 'cnt', 'humidity', and 'temp'.
Noted the maximum frequency of bike counts and the range of weather conditions.

## Bivariate Analysis
Identified correlations between temperature, humidity, windspeed, and bike counts.
Explored relationships between bike counts and variables like holidays, working days, seasons, and weather conditions.

## Correlation Analysis
Analyzed the correlation matrix to understand inter-variable relationships.

## Model Development
Data Splitting & Scaling: Divided data into training (70%) and testing (30%) sets, and applied Min-Max scaling.
Initial Model: Achieved an R-squared of 0.853, but noticed several variables with high p-values.
Feature Reduction with RFE: Reduced variables to 17 using Recursive Feature Elimination (RFE), slightly adjusting the R-squared.
VIF & P-value Adjustments: Dropped variables like 'humidity', 'holiday', 'temp', and 'winter' based on VIF and p-values.
Final Model: Established a final model with an R-squared of 0.798.

## Residual Analysis
Checked for normal distribution of residuals to validate linear regression assumptions.
Predictions and Model Evaluation
Made predictions on the test set and evaluated using a scatter plot.
Final test R-squared: 0.7832504527952754.

## Conclusion

##The company wants to know:
- Which variables are significant in predicting the demand for shared bikes.
- How well those variables describe the bike demands

Identified significant variables influencing bike demand.
Provided insights for BoomBikes to strategize for the post-Covid-19 market.

Significant variables to predict the demand for shared bikes

- holiday
- temp
- hum
- windspeed
- Season
- months(January, July, September, November, December)
- Year (2019)
- Sunday
- weathersit( Light Snow, Mist + Cloudy)

## Final Model Equation
cnt = 0.0570*workingday - 0.1926*windspeed - 0.2381*spring - 0.0403*summer + 0.2457*2019 - 0.1186*Dec - 0.1231*Jan - 0.1127*Nov + 0.0558*Sep + 0.0665*Mon - 0.3207*Light Snow_Weather - 0.0901*Misty_Weather + 0.5360


## Dependencies
This analysis was performed using the following libraries:

NumPy (numpy)
Pandas (pandas)
Matplotlib (matplotlib.pyplot)
Seaborn (seaborn)
Scikit-learn (sklearn.model_selection, sklearn.preprocessing, sklearn.feature_selection, sklearn.linear_model)
Statsmodels (statsmodels.api)