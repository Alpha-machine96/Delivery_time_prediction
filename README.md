# Food Delivery Time Prediction

A machine learning project that predicts food delivery times using ensemble methods, helping improve customer satisfaction and operational efficiency for food delivery platforms.
___________________________________________________________________________________________________________________________________________

## Overview

This project tackles the challenge of accurately predicting food delivery times by leveraging machine learning algorithms. By analyzing factors such as distance, traffic conditions, weather, delivery person characteristics, and time patterns, the model provides reliable time estimates that can enhance both customer experience and business operations.

### Why This Matters

- **Customer Satisfaction:** Accurate delivery time estimates improve user experience

- **Operational Efficiency:** Better resource allocation and route planning

- **Business Intelligence:** Identify factors that impact delivery performance

### Project Highlights

- **Dataset:** 45,000+ delivery records from Kaggle

- **Models:** Compared Linear Regression, Decision Trees, and Random Forest

- **Best Model:** Random Forest Regressor (tuned with GridSearchCV)

- **Performance:** R² = 0.84, MAE = ±6.5 minutes
  _____________________________________________________________________________________________________________________________
## Key Features

### Data Processing Pipeline

- **Data Cleaning:** Handled missing values, removed duplicates, treated outliers

- **Feature Engineering:** Created 40+ features including geospatial, temporal, and interaction features

- **Encoding:** One-hot encoding for categorical variables, feature scaling for numerical data

- **Validation:** Train-validation split with cross-validation

### Machine Learning Models

- **Linear Regression:** Baseline model for comparison

- **Decision Tree:** Single tree with depth constraints

- **Random Forest:** Ensemble of 100+ trees (best performer)

- **Hyperparameter Tuning:** GridSearchCV with 3-fold cross-validation
  ____________________________________________________________________________________________________________________________________
 ## Dataset
 
**Source:** Kaggle Food Delivery Dataset by Gaurav Malik

**Size:**

**Training Set:** 45,593 records

**Test Set:** 19,383 records
___________________________________________________________________________________________________________________________________________
## Methodology

### Phase 1: Data Preprocessing

**1. Missing Value Treatment**

- **Numerical:** Median imputation

- **Categorical:** Mode imputation

- **Removed:** < 1% of records with critical missing data

**2. Outlier Handling**

- **Detection:** IQR (Interquartile Range) method

- **Treatment:** Winsorization (capping at boundaries)

- Preserved data while reducing extreme values

**3. Data Quality**
   
- Removed 0.5% duplicate records

- Standardized categorical values (lowercase, stripped whitespace)

- Verified data types and consistency



