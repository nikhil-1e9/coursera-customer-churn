# coursera-customer-churn
[Customer churn prediction](https://www.coursera.org/projects/data-science-challenge) challenge on Coursera.

This challenge consists of predicting the customer churn on a video streaming service. In this challenge, you are given two datasets: train.csv and test.csv. The train.csv dataset contains 243,787 subscriptions with the target variable Churn indicating whether a user has churned or not. The test.csv dataset contains 104,480 subscriptions without the Churn information, and your task is to predict the likelihood of churn for these subscriptions. The dataset description can be found in the data_descriptions.csv file. The dataset contains 20 predictor variables.

## Observations
- Data doesn't contain any null values
- There is no significant correlation between the predictor columns
- No distinctions can be drawn for churned or non-churned customers on the basis of visualizations

## Approach
- Converted all categorical column values to integers using one-hot encoding
- Calculated mutual information for predictor variables with respect to Churn
- Spliited the model into training and testing sets and set out 20% data for making predictions
- Trained an XGBoost model on the training data with default hyperparams and got ROC-AUC score of 0.738
- Tuned the hyperparameters with Optuna and increased the ROC-AUC to 0.746
- Used the tuned model to make predictions on the test data and got a final score of 0.748
