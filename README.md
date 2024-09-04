# Nearest Earth Objects (NEOs) Hazard Prediction

## Project Overview

This project aims to predict whether a Nearest Earth Object (NEO) observed by NASA from 1910 to 2024 is hazardous or not. Using a dataset containing various features of these NEOs, we applied several machine learning models to identify the most effective model for this binary classification task.

## Dataset

The dataset used for this project contains 338,199 records of NEOs with the following features:
- `absolute_magnitude`
- `estimated_diameter_min`
- `estimated_diameter_max`
- `relative_velocity`
- `is_hazardous` (Target variable)

### Data Cleaning

The initial dataset included some irrelevant features and missing values:
- Dropped columns `orbiting_body`, `neo_id`, and `name` as they do not contribute to the prediction.
- Removed rows with missing values.

### Exploratory Data Analysis (EDA)

Several exploratory data analysis steps were performed:
- **Target Variable Distribution**: 87% of the NEOs were identified as non-hazardous.
- **Continuous Variables Distribution**: Histograms were plotted to understand the distribution of `absolute_magnitude`, `estimated_diameter_min`, `estimated_diameter_max`, and `relative_velocity`.
- **Outliers Identification**: Outliers were identified using boxplots and calculated using the Interquartile Range (IQR) method.
- **Feature Relationships**: Correlation heatmaps, scatter plots, and violin plots were used to identify relationships between features and the target variable.

## Feature Engineering

- The dataset was split into features (`X`) and the target variable (`y`).
- Label encoding was applied to the target variable (`y`).
- The dataset was split into training and testing sets with an 80-20 split, ensuring stratification to maintain the distribution of the target variable.

### Handling Imbalance

- The target variable was imbalanced, with 87% of the NEOs being non-hazardous.
- SMOTE (Synthetic Minority Over-sampling Technique) was applied to the training data to handle the imbalance.

## Model Training and Evaluation

Several machine learning models were trained and evaluated:

1. **Logistic Regression**
   - Accuracy: 52%
   - AUC-ROC Curve was plotted.

2. **Random Forest**
   - Accuracy: 91%
   - AUC-ROC Curve was plotted.
   - Identified as the best-performing model.

3. **XGBoost**
   - Accuracy: 80%
   - AUC-ROC Curve was plotted.

4. **Decision Tree**
   - Accuracy: 90%
   - AUC-ROC Curve was plotted.

5. **K-Nearest Neighbors (KNN)**
   - Accuracy: 65%
   - AUC-ROC Curve was plotted.

### Feature Importance

For the best-performing model (Random Forest):
- The feature importance was analyzed, highlighting which features had the most significant impact on the model's performance.
- The most important features were plotted in a histogram.

## Insights and Findings

- **Model Performance**: The Random Forest model provided the highest accuracy of 91%, making it the most reliable model for predicting hazardous NEOs.
- **Feature Importance**: The analysis of feature importance revealed that `absolute_magnitude` and `relative_velocity` were among the most influential features in predicting whether an NEO is hazardous.

## Conclusion

This project successfully developed a model that can predict the hazardousness of NEOs with high accuracy. The Random Forest model stood out as the best-performing model, and feature importance analysis provided valuable insights into which features are most critical in the prediction process.
