# E-commerce Customer Churn Prediction using Machine Learning

## Overview
This project predicts customer churn for an e-commerce business using customer-level RFM and behavioral features. It compares multiple baseline machine learning models and evaluates how robust the models are when noisy or outlier data is introduced.

The goal is to identify customers who are likely to churn so that businesses can target them with retention campaigns before they become inactive.

## Business Problem
E-commerce companies lose revenue when customers stop purchasing or become inactive. Retaining existing customers is often more cost-effective than acquiring new ones.

This project answers the question:

**Can customer transaction history, RFM metrics, and behavioral features be used to accurately predict e-commerce customer churn?**

## Project Objectives
- Analyze customer churn behavior using e-commerce transaction data.
- Build customer-level RFM and behavioral features.
- Perform exploratory data analysis on churn, recency, frequency, and revenue patterns.
- Apply wrapper-based feature selection to reduce dimensionality.
- Train and compare baseline machine learning classifiers.
- Evaluate model performance on clean data, noisy data, and data cleaned using outlier detection.
- Translate model findings into business retention insights.

## Dataset
The project uses a UK e-commerce customer dataset.

Reported dataset summary:
- Original dataset: approximately 112,610 rows and 276 columns
- Final modeling dataset: approximately 21,605 user-level rows
- Modeling features: approximately 275 features before feature selection
- Target variable: `target_event`, representing customer churn status

The dataset is not uploaded in this repository. Add the dataset locally inside the `data/` folder before running the notebook.

## Methods Used
- Data preprocessing
- User-level aggregation
- RFM analysis
- Behavioral feature analysis
- StandardScaler normalization
- Stratified train-test split
- Class imbalance handling
- SMOTE comparison
- Wrapper-based feature selection
- Synthetic outlier injection
- KNN-based outlier detection
- Model comparison and evaluation

## Models Compared
- Logistic Regression
- Logistic Regression with SMOTE
- Support Vector Machine with RBF kernel
- Random Forest

## Evaluation Metrics
- Accuracy
- F1-score
- Precision
- Recall
- Confusion matrix
- 3-fold cross-validation
- 5-fold cross-validation
- Outlier robustness comparison

## Key Results
The models were evaluated under three scenarios:

1. Clean in-distribution test data
2. Test data with synthetic outliers
3. Test data after KNN-based outlier removal

The Support Vector Machine model was selected as the final model because it showed strong performance and robustness under noisy and outlier conditions.

Reported SVM performance:
- Clean test accuracy: approximately 99.58%
- Accuracy with synthetic outliers: approximately 98.19%
- Accuracy after KNN-based outlier removal: approximately 99.71%

## Business Insights
- Customers with high recency and low purchase frequency are more likely to churn.
- High-value customers should be prioritized for retention campaigns.
- Outlier and data-quality handling improves the reliability of churn prediction.
- A churn model can support customer segmentation, retention targeting, and campaign prioritization.
- KNN-based outlier detection can help reduce missed churners and improve model reliability before deployment.

## Repository Structure
```text
ecommerce-customer-churn-prediction-ml/
│
├── README.md
├── requirements.txt
│
├── notebooks/
│   └── ecommerce_customer_churn_prediction_ml.ipynb
│
└── data/
    └── README.md
