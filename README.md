# Bank Marketing Term Deposit Prediction

## Project Overview

This project focuses on predicting whether customers will subscribe to a term deposit based on direct marketing campaign data from a European banking institution. The marketing campaign involves making phone calls to customers, often multiple times, to promote term deposit subscriptions.

## Objective

**Primary Goal:** Predict if a customer will subscribe (yes/no) to a term deposit (target variable `y`)

**Success Metric:** Achieve 81% or above accuracy using 5-fold cross-validation

## Business Questions

1. **Customer Segmentation:** Identify customers who are more likely to buy the investment product and determine which customer segments should be prioritized using DBSCAN clustering technique
2. **Feature Importance:** Understand what drives customer purchase decisions and identify key features to focus on

## Methodology

### Models Implemented
- **XGBoost** (Best performing model)
- **Random Forest**
- **Logistic Regression**

### Model Selection Approach
- **Evaluation Metric:** F1-score (primary metric due to class imbalance)
- **Class Imbalance Handling:** Applied SMOTE (Synthetic Minority Oversampling Technique) to address the unbalanced classes in the dataset
- **Threshold Optimization:** Used `predict_proba` to generate probability predictions and tested thresholds from 0.2 to 0.8 to optimize F1-score performance
- **Cross-Validation:** 5-fold cross-validation for robust model evaluation

### Best Model Performance
**XGBoost** achieved the highest F1-score after threshold optimization, making it our selected model for deployment. The model was further optimized using GridSearchCV for hyperparameter tuning to maximize performance.

## Key Features

The model utilizes various customer attributes including:
- Demographics (age, job, marital status, education)
- Financial information (balance, default status, loans)
- Contact information (contact type, timing, duration)
- Campaign details (number of contacts, previous outcomes)

## Technical Implementation

### Model Training
1. Data preprocessing and feature engineering
2. Applied SMOTE to handle class imbalance in the target variable
3. Training multiple models (XGBoost, Random Forest, Logistic Regression)
4. Used GridSearchCV for hyperparameter optimization on the best performing model (XGBoost)
5. Applied DBSCAN clustering technique to identify relevant customer segments to prioritize

### Threshold Optimization
- Generated probability predictions using `predict_proba`
- Systematically tested thresholds from 0.2 to 0.8
- Selected optimal threshold based on F1-score performance
- This approach ensures balanced precision and recall for business impact

### Model Evaluation
- 5-fold cross-validation for reliable performance estimation
- F1-score as primary metric (addressing class imbalance)
- Accuracy tracking to meet business requirements (>81%)

## Business Impact

This machine learning solution enables the banking client to:
- **Improve Call Efficiency:** Focus efforts on customers with higher subscription probability
- **Optimize Resource Allocation:** Prioritize high-potential customer segments
- **Data-Driven Decisions:** Leverage interpretable model insights for campaign strategy
- **Measurable ROI:** Track and improve campaign success rates

