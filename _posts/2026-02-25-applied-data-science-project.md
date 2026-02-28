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

Ultimately, the project aims to deliver a reliable and generalizable predictive model that not only performs well statistically, but also provides meaningful business insights for Amazon’s e-commerce operations.

## Work Accomplished

1. Data Preparation and Cleaning
Key actions taken:
- Standardised column naming for consistency
- Checked for missing values and data anomalies
- Verified data types for numerical and categorical variables
- Ensured the target variable (TotalAmount) was properly defined   

2. Feature Engineering
Key actions taken:
- Net Price (after discount adjustment)
- Order Value (quantity × net price)
- Discount Amount
- Shipping Cost Ratio (shipping cost relative to order size)
- Month extracted from order date
- Discount Rate Band (categorical grouping of discount levels)

3. Data Transformation
- Categorical variables (Category, Country, Discount Rate Band) were converted using one-hot encoding
- Numerical variables were standardised for linear regression
- Multicollinearity was checked using Variance Inflation Factor (VIF) for the linear model
- Data was split into training and testing sets (70/30 split) to ensure fair model evaluation

4. Model Development
Three regression-based models were developed and compared:
- Multiple Linear Regression (baseline)
- Decision Tree Regressor
- Decision Tree Regressor

Each model was evaluated using:
- R²
- RMSE
- MAE
- 5-Fold Cross Validation

5. Model Optimization
Hyperparameter tuning was conducted using GridSearchCV to optimise:
- Learning rate
- Tree depth
- Number of estimators
- Subsampling ratio

### Data Preparation
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

### Modelling
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

### Evaluation
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

## Recommendation and Analysis

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

## AI Ethics
Discuss the potential data science ethics issues (privacy, fairness, accuracy, accountability, transparency) in your project. 

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

## Source Codes and Datasets
Upload your model files and dataset into a GitHub repo and add the link here. 

Please refer here for all related files [here](https://github.com/Jason-Chan1394/itd214_project)

