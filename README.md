USA Hospital Readmission Risk Prediction:

Project Overview

This project predicts whether a hospital/facility is at high risk of patient readmissions based on historical data and hospital characteristics.

Type: Binary Classification

Target: High_Readmission (1 if predicted readmission rate > median, else 0)

Dataset: Hospital Readmission data from CMS (USA-based)

Goal: Identify high-risk hospitals and provide explainable insights for healthcare decision-making.

Motivation:

Hospital readmissions are a critical metric for quality of care. Reducing unnecessary readmissions saves costs and improves patient outcomes. This project demonstrates:

Advanced ML and DL techniques on healthcare tabular data

Handling missing data and categorical features

Probability calibration and threshold optimization

Explainable AI (SHAP) for interpretability

Dataset

Source: CMS Hospital Readmissions Data

Key Features:

Facility Name, State, Measure Name (categorical)

Number of Discharges, Predicted Readmission Rate, Excess Readmission Ratio (numeric)

Start Date, End Date (temporal)

Footnote (optional textual context)

Target Variable: High_Readmission (binary)

Project Steps
1. Data Preprocessing

Cleaned column names to remove special characters for LightGBM/XGBoost compatibility

Handled missing values: numeric → median, categorical → mode

Created binary target variable High_Readmission

2. Feature Engineering

One-hot encoding for categorical features

Scaling numeric features for deep learning

Optional temporal features from Start Date / End Date

3. Machine Learning Models

XGBoost, LightGBM, CatBoost (baseline models)

Stacking Ensemble combining Logistic Regression, Random Forest, XGBoost

Threshold Optimization to maximize F1-score

Probability Calibration for risk probabilities

4. Deep Learning Baseline

Fully connected neural network with BatchNorm and Dropout

Evaluated using ROC-AUC

5. Model Explainability

SHAP values for feature importance visualization

Provides interpretable insights on which features drive high readmission risk

Evaluation Metrics

Classification Report: precision, recall, F1-score

ROC-AUC: model discrimination ability

Calibration Curve: reliability of predicted probabilities

SHAP Summary: global and local feature importance

Key Insights

Features like Number of Discharges, Excess Readmission Ratio, and State are highly predictive

Stacking ensemble improved overall ROC-AUC compared to individual models

Threshold optimization significantly improves F1-score for identifying high-risk hospitals

SHAP analysis highlights actionable insights for hospital administrators
