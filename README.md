# Predicting Bikeshare Rentals with Linear Regression

##Background
Bikeshare programs have emerged as a vital solution for local travel, helping to alleviate traffic congestion and air pollution with the added benefit of promoting active lifestyles. Like any other shared service, finding the optimal balance of supply and demand is a major challenge for operators. Accurate forecasting of usage patterns, as well as understanding the features that impact ridership, could help operators make data-informed decisions to manage these services efficiently. 

## Methodology
The goal of this project is to forecast bikeshares in London based on weather and time-based data. The project has two main objectives: i) to uncover a linear regression model that most accurately forecasts daily rental numbers and ii) to determine the most impactful features. 

The project began with an exploratory data analysis, which utilized pairwise scatterplots and a correlation matrix to determine linear relationships between predictors and the response, as well as among predictors themselves. From here, I discovered potential sources of collinearity and considered subsets of features that would avoid this issue. I then conducted an ANOVA test to determine the goodness of fit of the models to identify significant interaction effects. 

Next, I tested the generalizability of the remaining models using k-fold cross-validation to select the final model. I employed diagnostic tools such as histograms and qq-plots to check the assumptions of errors. Lastly, I evaluated the final model’s summary outputs to interpret the significance and contribution of predictors. 

Examples of visualizations from the analysis are shown below:

### Pairwise Scatterplots
![picture alt](https://github.com/eeorenstein/Bikeshare_Regression/blob/main/pairwise_scatterplots.png)

### Diagnostic Plots
![picture alt](https://github.com/eeorenstein/Bikeshare_Regression/blob/main/diagnostic_plots.png)

## Data
The dataset contains 500 days, each as a separate observation, in London from 2015 to 2016. More specifically, each observation in the dataset (txt file) includes:
* Target
  * Bikeshares rented
* Weather-based features
  * Temperature (Celcius)
  * Feels-like temperature (Celcius)
  * Humidity (%)
  * Wind speed (km/hr)
* Time-based features
  * Holiday 
  * Weekend
  * Season (0 for spring, 1 for summer, etc.)

## Results
The final model chosen to predict daily bikeshare rentals can be seen below:

![picture alt](https://github.com/eeorenstein/Bikeshare_Regression/blob/main/summary_output.png)

This model indicates that bank holidays result in approximately 8,974 fewer bikes shared that day compared to non-holidays, adjusting for all other predictors. Holiday, followed by weekend and temperature have the most impact on bike sharing numbers. However, weekend is not significant at alpha = 0.05, so we cannot say definitively that it is different from zero. Therefore, we can confidently claim that, under this model, holiday and temperature have the greatest impact on the number of bikes shared (for a one unit change or compared to its reference category for factors).

## Tools
R was the only tool used for this project.
