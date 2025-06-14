# Flight Delay Analysis: Classification & Clustering

## Overview

This project analyzes flight delay data using classification and clustering techniques. The main objectives are:

- To build predictive models that determine whether a flight will be delayed based on selected features.
- To explore patterns in flight characteristics using clustering methods.

## Key Features

- Classification models: Penalized Logistic Regression, Random Forest, and XGBoost
- Predictors used: `Flight_Duration`, `Day_of_Week`, and `Weather_Conditions`
- One-hot encoding and normalization of predictors
- Data balancing with SMOTE to handle class imbalance
- Model evaluation using ROC curves, AUC, and confusion matrices
- Feature importance plots for tree-based models
- K-Means clustering on `Flight_Duration` and `Day_of_Week` with automatic optimal K detection
- Clean and interpretable visualizations

## Data

The dataset used is `flights_200.csv`, which contains 200 flight records with information such as duration, airline, scheduled departure, and delay status.

## Requirements

- R (version ≥ 4.0)
- Required packages:

```r
install.packages(c("tidymodels", "tidyverse", "xgboost", "ranger", "themis", "vip", "doParallel"))
How to Run
Open the R project or script.

Ensure the flights_200.csv file is in your working directory.

Run the R script to execute both the classification and clustering pipelines.

View ROC curves, feature importance plots, and clustering results.

Examine sample predictions from the logistic regression model.

Sample Predictions Using Logistic Regression
To demonstrate the model's functionality, five realistic flights were manually constructed and passed into the logistic regression model:

Sample Input Data
Flight_Duration	Day_of_Week	Weather_Conditions
85	1 (Monday)	Clear
180	3 (Wednesday)	Rain
145	5 (Friday)	Fog
220	7 (Sunday)	Storm
110	2 (Tuesday)	Snow

Model Predictions
.pred_0	.pred_1	Predicted Class	Flight_Duration	Day_of_Week	Weather_Conditions
0.72	0.28	0 (No Delay)	85	1	Clear
0.45	0.55	1 (Delay)	180	3	Rain
0.51	0.49	0 (No Delay)	145	5	Fog
0.38	0.62	1 (Delay)	220	7	Storm
0.60	0.40	0 (No Delay)	110	2	Snow

The model reacts reasonably to different conditions, such as predicting a delay for a long flight in stormy weather on a Sunday.

License
This project is licensed under the MIT License. See the LICENSE file for details.

Author
Oklogo Samuel