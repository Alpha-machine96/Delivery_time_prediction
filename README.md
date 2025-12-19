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

### Phase 2: Feature Engineering

Geospatial Features

Temporal Features

Interaction Features

Derived Features

### Phase 3: Model Development

#### Models Evaluated

**1. Linear Regression (Baseline)**

- Simple, interpretable

- Assumes linear relationships

- Fast training and prediction

**2.Decision Tree Regressor**

- Captures non-linear patterns

- Constrained depth to prevent overfitting

- Parameters: max_depth=10, min_samples_split=20

**3.Random Forest Regressor ⭐ Selected**

- Ensemble of 100+ decision trees

- Reduces overfitting through averaging

- Robust to outliers and noise

- Parameters: n_estimators=150, max_depth=15

### Phase 4: Evaluation

#### Metrics Used

- RMSE (Root Mean Squared Error): Penalizes large errors heavily

- MAE (Mean Absolute Error): Average prediction error in minutes

- R² (R-squared): Proportion of variance explained (0-1 scale)

#### Validation Strategy

- 80-20 train-validation split

- 3-fold cross-validation during hyperparameter tuning

- Checked for overfitting (train vs validation performance)
_______________________________________________________________________________________________________________

## Results

### Model Performance Comparison

| Model   | Train RMSE | 
|  ---  | ---  |  
| Linear Reggression |  8.23 |                                                                     
| Decission Tree  | 7.45 |                                                                     
| Random Forest  | 56.8 |                                                                     
                                                                  
### Key Insights

#### Winner: Random Forest Regressor

- Validation R² = 0.841: Explains 84.1% of delivery time variance

- MAE = 6.23 minutes: Predictions typically off by ±6 minutes

- No Overfitting: Small gap (0.05) between train and validation R²

- Consistent: Low RMSE indicates reliable predictions across all ranges

#### What This Means

- Model predicts within ±6 minutes on average

- Works well for both short and long deliveries

- Captures complex patterns (distance + traffic + weather interactions)

- Production-ready performance

#### Feature Importance Analysis

**Top 10 Most Important Features**

1. Delivery_Distance_km (28.5%) - Distance is the primary driver

2. Distance_Traffic_Interaction (16.3%) - Combined effect matters

3. Order_Hour (11.2%) - Time of day significantly impacts delivery

4. Weather_Traffic_Score (9.1%) - Adverse conditions slow delivery

5. Delivery_person_Ratings (7.8%) - Better riders are faster

6. Is_Peak_Hour (6.4%) - Rush hours add delays

7. Multiple_Deliveries (5.9%) - More stops = more time

8. Expected_Time (5.3%) - Our baseline calculation helps

9. Vehicle_Condition (4.7%) - Better vehicles perform better

10. Traffic_Numeric (4.8%) - Raw traffic level important
