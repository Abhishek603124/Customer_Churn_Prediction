# Cashback User Churn Prediction & Product Analytics

## Overview

This project builds an end-to-end machine learning pipeline to predict customer churn for a cashback platform using customer demographics and transaction history.

Along with churn prediction, the project includes exploratory data analysis (EDA), feature engineering, activation funnel analysis, and business recommendations to help improve customer retention.

---

## Problem Statement

A cashback platform wants to identify users who are likely to stop using the platform so that the CRM team can proactively target them with retention campaigns.

### Churn Definition

- **Snapshot Date:** 2026-06-01
- **Eligible Users:** Users who signed up on or before 2026-02-01
- **Churned User:** A user who made **no transactions in the 90 days before the snapshot date**

---

## Dataset

The project uses two datasets.

### Users Dataset

- User ID
- Signup Date
- Signup Channel
- City
- Age
- Gender
- Platform
- Referral Count

### Transactions Dataset

- Transaction ID
- User ID
- Transaction Date
- Retailer
- Order Value
- Cashback Earned
- Cashback Status

---

## Project Workflow

### 1. Data Cleaning

- Removed duplicate records
- Handled missing values
- Corrected inconsistent signup channels
- Treated invalid ages
- Standardized categorical values
- Validated transaction records

---

### 2. Exploratory Data Analysis

Performed business-oriented analysis including:

- Transactions per user
- Revenue distribution
- Customer spending behavior
- Top revenue contributors
- Activation Funnel Analysis
    - Signup
    - First Transaction
    - Repeat Transaction
    - Confirmed Cashback

---

### 3. Feature Engineering

User-level features include:

- Transaction Count
- Total Spend
- Average Order Value
- Days Since Last Transaction
- Customer Age (Days)
- Unique Retailers
- Total Cashback Earned
- Return Rate
- Transactions in Last 30 Days
- Confirmed Cashback Rate

Special care was taken to **avoid data leakage** by creating features only from transactions before the feature cutoff date.

---

### 4. Model Building

Models Used:

- Logistic Regression
- Random Forest Classifier

Evaluation Metrics:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

Hyperparameter tuning was performed on the Random Forest model using GridSearchCV.

---

## Results

### Best Model

**Random Forest**

| Metric | Score |
|---------|--------|
| Accuracy | **77.5%** |
| Precision | **79.9%** |
| Recall | **72.9%** |
| F1 Score | **76.2%** |
| ROC-AUC | **0.83** |

---

## Key Business Insights

- Recent user activity is the strongest predictor of churn.
- Users shopping from multiple retailers are less likely to churn.
- Users with higher confirmed cashback rates show better retention.
- Activation funnel analysis identifies the biggest opportunity between first and repeat transactions.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

---

## Repository Structure

```
Customer_Churn_Prediction/
│
├── 01_Data_Cleaning.ipynb
├── 02_EDA_Model_Training.ipynb
└── README.md
```
