# Eats_ML_cash_arrear_pred

## Goal: 
The goal of the model is to predict which order placed using cash will result in arrears due to fraudulent activity. Once the model learns how to do this, it would prevent these fraudulent eaters from placing a cash order and push them to use an online payment method that we are more confident about

## Data: 
The model uses data from the following tables and a host of carefully engineered features which have boosted the prediction accuracies to ~80% with higher precision and f1-scores
1. fraud_pmt_risk_cohort_fact
2. dim_city
3. fact_eats_trip
4. fact_trip_bill
5. dim_eater
6. raw_etl_data
7. payment_profile 

## Rules:
The model only uses features which will be available when the order is being placed and no courier or restaurant information is used except for restaurant_uuid. The conditions used to determine the relevance of a feature are as below:
1. Features must be available during the placement of order
2. The data must not include any courier partner or restaurant details. rest_uuid is fine
3. Features defining why the order is fraudulent must not be used 
4. Features that expires and is non-recurrent must not be used ex: promotion_codes
5. Must not have features which are over descriptive of the target value


## Flow of the model
1. Reading the data
2. Data Cleaning
3. Feature Engineering
4. Encoding
5. Correlations and feature importance
6. Ensemble modeling
7. results validation
8. Hyperparameter tuning
9. Transfer learning
10.Out of time sample testing

## Metrics used to evaluate the performance of the data:
1. AUC_ROC
2. AUC_ROC using probabilities
3. Accuracy
4. confusion matrix values
5. Precision
6. Recall
7. F1-score

## Test results:
1. The model's performance is evaluated using an in-time sample and an out-of-time sample test
2. The out of time sampling was done using data from a date range completely different from what the model was trained on
3. All results have been attached on test_results sheet

