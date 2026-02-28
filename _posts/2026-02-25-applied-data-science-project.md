---
layout: post
author: Chan Tuck Wai, Jason
title: "Applied Data Science Project Documentation"
categories: ITD214
---
## Project Background
Overview

In the fast-paced world of e-commerce, understanding what drives customer spending is essential for sustainable growth. With large volumes of transactional data available, businesses have the opportunity to move beyond intuition and rely on data-driven insights to support pricing, logistics, and revenue planning decisions.

This project focuses on using historical Amazon transaction data to build a predictive model that estimates the Total Amount of customer orders. By analysing factors such as quantity purchased, shipping costs, discount levels, product categories, and customer location, the project aims to uncover the key drivers influencing order value.

Business Goal

The main business goal is to improve revenue forecasting and support more informed pricing and shipping decisions. By identifying which variables most strongly impact total order value, the model can help guide operational and strategic planning within an e-commerce environment.

Project Objective

The objective of this project is to develop and evaluate supervised machine learning models to predict the Total Amount of an order. The process includes data cleaning, feature engineering, model comparison, cross-validation, and performance optimisation.

## Work Accomplished
To achieve the objective of predicting Total Amount, the following key activities were completed:

- Data Cleaning & Preparation :
The dataset was reviewed for consistency, missing values, and correct data types. Column names were standardised and the target variable was clearly  defined to prevent data leakage. ![Data Overview](https://github.com/user-attachments/assets/b6260726-854d-42af-9b2d-48fed4a45316)

- Feature Engineering :
Meaningful features were created to better capture business logic, including Net Price, Discount Amount, Shipping Cost Ratio, Month, and Discount Rate Band. Categorical variables were transformed using one-hot encoding.

- Model Development
Three regression models were developed and compared: Multiple Linear Regression (baseline), Decision Tree Regressor, and Gradient Boosting Regressor.

- Model Evaluation & Validation
Models were evaluated using R², RMSE, and MAE. A 70/30 train-test split and 5-fold cross-validation were applied to assess predictive accuracy and stability.

- Model Optimisation
Gradient Boosting was selected as the best-performing model. Hyperparameter tuning using GridSearchCV further improved performance while maintaining strong generalization.
  
### Data Preparation
A structured data preparation process was conducted to ensure the dataset was accurate, consistent, and ready for modelling.

- Data Quality Checks: Missing values and duplicate records were reviewed to prevent bias and ensure transaction integrity. Categorical variables were examined for inconsistent or abnormal entries.
- Date Transformation: The Order Date field was converted into datetime format, and yearly transaction summaries were generated to validate temporal consistency and overall transaction trends. ![Yearly Transaction Distribution](https://github.com/user-attachments/assets/fdde292b-3334-4e8a-a5d3-f436d9f093d8)
- Feature Engineering: Several business-driven features were created to better reflect pricing and logistics dynamics:
  - Net Price (adjusted unit price after discount)
  - Discount Amount (monetary value of discount applied)
  - Order Value (Quantity × Net Price)
  - Shipping Cost Ratio (Shipping Cost relative to Order Value)
  - Discount Rate Band (grouped discount levels)
  - ![New Features](https://github.com/user-attachments/assets/8ef16d02-c9be-4686-a86a-2ffd1d0d0ae0)

- Feature Validation: Key engineered features were validated visually to ensure logical consistency:
  - Unit Price vs Net Price: Confirmed that net price decreases appropriately as discounts increase. ![Unit Price vs Net Price](https://github.com/user-attachments/assets/dcf43d52-56d1-4433-a171-ea6aff9c66c1)
  - Quantity vs Order Value: Verified that higher quantities lead to proportionally higher order values. ![Quantity vs Order Value](https://github.com/user-attachments/assets/a6ec55f5-f67e-45a0-87da-c424dc598f66)
  - Shipping Cost vs Shipping Cost Ratio: Ensured the ratio behaves logically, increasing when shipping cost is high relative to order size. ![Shipping Cost vs Shipping Cost Ratio](https://github.com/user-attachments/assets/c499bbc9-78f4-47ec-abac-21f33e5dede3)
- Categorical Encoding: Country, Category, and Discount Rate Band were transformed using one-hot encoding to prepare the dataset for regression modelling. 


### Modelling
The modelling phase began with a correlation analysis to better understand the relationships between key variables and the target variable, TotalAmount. The correlation matrix helped identify meaningful predictors such as quantity, shipping-related variables, and pricing components, while also checking for potential multicollinearity issues before model development. ![Correlation Matrix](https://github.com/user-attachments/assets/b55cf54f-7483-4147-a58e-12678f72bd9f)

Following this initial assessment, three regression models were developed and compared:
- Multiple Linear Regression as a baseline model to assess linear relationships.
- Multiple Linear Regression as a baseline model to assess linear relationships.
- Gradient Boosting Regressor as an ensemble method to improve predictive accuracy.
The goal was to compare a linear model against non-linear and ensemble methods to determine which best captures complex e-commerce transaction patterns.

Data Splitting & Validation:
- The dataset was split into training and testing sets (70/30 split) to ensure fair performance evaluation. Additionally, 5-fold cross-validation was conducted to assess model stability and generalization capability.

Evaluation Metrics:
- Models were evaluated using R², RMSE, and MAE to measure explanatory power and prediction error. Cross-validation results provided further confirmation of model robustness.
![Evaluation Framework](https://github.com/user-attachments/assets/049e26b1-a1d8-40b5-9de6-cc5374be58d2)

Model Optimisation:
- After comparison, Gradient Boosting was selected as the best-performing model. Hyperparameter tuning using GridSearchCV further improved predictive performance while maintaining stability.

Overall, the modelling process was structured to ensure statistical reliability, minimize overfitting, and deliver a high-performing model capable of supporting revenue forecasting in an e-commerce context.

 
### Evaluation
The evaluation process was designed to ensure that the selected model was not only accurate, but also stable and reliable across different validation methods.

Single-Split Model Comparison
The first comparison was conducted using a 70/30 train-test split. Among the three models tested, Gradient Boosting clearly outperformed the others.

- Gradient Boosting achieved the highest R² and lowest RMSE and MAE
- Gradient Boosting achieved the highest R² and lowest RMSE and MAE
- Decision Tree performed moderately well but showed higher prediction error

This initial comparison established Gradient Boosting as the strongest candidate model.![Singlr-Split Model](https://github.com/user-attachments/assets/76fc0ca7-c705-439d-b7e6-1d798c5b0cbc)

Model Comparison After 5-Fold Cross Validation
To ensure robustness, 5-fold cross-validation was applied.
- Gradient Boosting maintained the highest average R²
- It also showed an extremely low standard deviation, indicating high stability
- Decision Tree showed moderate consistency
- Decision Tree showed moderate consistency

Cross-validation confirmed that the Gradient Boosting model was not overfitting and generalized well across different subsets of the data. ![5-Fold Cross Validation](https://github.com/user-attachments/assets/eaf73f3a-777c-41e2-98f2-bb61afb8e747)

Final Model Comparison (Single Split vs Cross Validation)
Comparing single-split results with cross-validation results showed:
- Minimal performance gap for Gradient Boosting
- Minimal performance gap for Gradient Boosting
- Strong evidence of generalization

This reinforced the reliability of the model before further optimization. ![5-Fold Cross Validation](https://github.com/user-attachments/assets/d7e10c5b-702b-496c-b077-50d667019612)



## Recommendation and Analysis

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

## AI Ethics
Discuss the potential data science ethics issues (privacy, fairness, accuracy, accountability, transparency) in your project. 

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

## Source Codes and Datasets
Upload your model files and dataset into a GitHub repo and add the link here. 

Please refer here for all related files [here](https://github.com/Jason-Chan1394/itd214_project)

