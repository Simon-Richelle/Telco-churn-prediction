# Telco-churn-prediction

## Introduction

This repository contains a project running on the Google Cloud Platform enabling to make prediction on the customer churn rate.

The goal is to use different GCP ressources in order to ingest, explore, transform and store our training data in order to train a ML algorithm predicting the churn rate of potential customers.

## Data

Our training dataset has been retrieved from kaggle : https://www.kaggle.com/blastchar/telco-customer-churn . 

"Predict behavior to retain customers. You can analyze all relevant customer data and develop focused customer retention programs." [IBM Sample Data Sets]

In this dataset, each row represents a customer, each column contains customer’s attributes described on the column Metadata. The raw data contains 7043 rows (customers) and 21 columns (features).

customerID : Customer ID\n
gender : Whether the customer is a male or a female
SeniorCitizen : Whether the customer is a senior citizen or not (1, 0)
Partner : Whether the customer has a partner or not (Yes, No)
Dependents : Whether the customer has dependents or not (Yes, No)
tenure : Number of months the customer has stayed with the company
PhoneService : Whether the customer has a phone service or not (Yes, No)
MultipleLines : Whether the customer has multiple lines or not (Yes, No, No phone service)
InternetService : Customer’s internet service provider (DSL, Fiber optic, No)
OnlineSecurity : Whether the customer has online security or not (Yes, No, No internet service)
OnlineBackup : Whether the customer has online backup or not (Yes, No, No internet service)
DeviceProtection : Whether the customer has device protection or not (Yes, No, No internet service)
TechSupport : Whether the customer has tech support or not (Yes, No, No internet service)
StreamingTV : Whether the customer has streaming TV or not (Yes, No, No internet service)
StreamingMovies : Whether the customer has streaming movies or not (Yes, No, No internet service)
Contract : The contract term of the customer (Month-to-month, One year, Two year)
PaperlessBilling : Whether the customer has paperless billing or not (Yes, No)
PaymentMethod : The customer’s payment method (Electronic check, Mailed check, Bank transfer (automatic), Credit card (automatic))
MonthlyCharges : The amount charged to the customer monthly
TotalCharges : The total amount charged to the customer
Churn : Whether the customer churned or not (Yes or No)

## Project Architecture

1) The data are under the form of a csv file, manually downloaded and stored into a GCS bucket;

2) We perform data exploration in Cloud Datalab in order to :
        - better understand our dataset for ML task (ie : correlation between features);
        - knowing which transform need to be implemented in Beam pipeline (ie. outlier detection, datatype bug, missing               values);
