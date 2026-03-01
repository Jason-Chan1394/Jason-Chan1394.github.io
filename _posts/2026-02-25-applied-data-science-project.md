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


## Work Accomplished
To achieve the objective of predicting Total Amount, the following key activities were completed:

- Data Cleaning & Preparation :
  The dataset was reviewed for consistency, missing values, and correct data types. Column names were standardised and the target variable was clearly     defined to prevent data leakage. ![Data Overview](https://github.com/user-attachments/assets/b6260726-854d-42af-9b2d-48fed4a45316)

- Feature Engineering :
  Meaningful features were created to better capture business logic, including Net Price, Discount Amount, Shipping Cost Ratio, Month, and Discount Rate   Band. Categorical variables were transformed using one-hot encoding.

- Model Development:
  Three regression models were developed and compared:
    - Multiple Linear Regression (baseline)
    - Decision Tree Regressor
    - Gradient Boosting Regressor

- Model Evaluation & Validation:
  Models were evaluated using R², RMSE, and MAE. A 70/30 train-test split and 5-fold cross-validation were applied to assess predictive accuracy and       stability.

- Model Optimisation:
  Hyperparameter tuning using GridSearchCV further improved performance while maintaining strong generalization.

  
### Data Preparation
A structured data preparation process was conducted to ensure the dataset was accurate, consistent, and ready for modelling.

- Data Quality Checks: Missing values and duplicate records were reviewed to prevent bias and ensure transaction integrity. Categorical variables were     examined for inconsistent or abnormal entries.
  
- Date Transformation: The Order Date field was converted into datetime format, and yearly transaction summaries were generated to validate temporal       consistency and overall transaction trends. ![Yearly Transaction Distribution](https://github.com/user-attachments/assets/fdde292b-3334-4e8a-a5d3-f436d9f093d8)
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
  
  - Categorical Encoding: Country, Category, and Discount Rate Band were transformed using one-hot encoding to prepare the dataset for regression            modelling. 


### Modelling
The modelling phase began with a correlation analysis to better understand the relationships between key variables and the target variable, TotalAmount. The correlation matrix helped identify meaningful predictors such as quantity, shipping-related variables, and pricing components, while also checking for potential multicollinearity issues before model development. 

![Correlation Matrix](https://github.com/user-attachments/assets/b55cf54f-7483-4147-a58e-12678f72bd9f)

Following this initial assessment, three regression models were developed and compared:
- Multiple Linear Regression as a baseline model to assess linear relationships
- Decision Tree Regressor to capture non-linear interactions
- Gradient Boosting Regressor as an ensemble method to improve predictive accuracy
The goal was to compare a linear model against non-linear and ensemble methods to determine which best captures complex e-commerce transaction patterns.

Data Splitting & Validation:
- The dataset was split into training and testing sets (70/30 split) to ensure fair performance evaluation. Additionally, 5-fold cross-validation was conducted to assess model stability and generalization capability.

Evaluation Metrics:
- Models were evaluated using R², RMSE, and MAE to measure explanatory power and prediction error. Cross-validation results provided further confirmation of model robustness. ![Evaluation Framework](https://github.com/user-attachments/assets/09088412-913d-4f72-86a9-73c97af91cce)

Model Optimisation:
- After comparison, hyperparameter tuning using GridSearchCV further improved predictive performance while maintaining stability.

Overall, the modelling process was structured to ensure statistical reliability, minimize overfitting, and deliver a high-performing model capable of supporting revenue forecasting in an e-commerce context.


### Evaluation
The evaluation process was designed to ensure that the selected model was not only accurate, but also stable and reliable across different validation methods.

Single-Split Model Comparison
The first comparison was conducted using a 70/30 train-test split. Among the three models tested, Gradient Boosting clearly outperformed the others.
- Gradient Boosting achieved the highest R² and lowest RMSE and MAE
- Decision Tree performed moderately well but showed higher prediction error
- Decision Tree Regressor to capture non-linear interactions

This initial comparison established Gradient Boosting as the strongest candidate model.
![Single Split Model](https://github.com/user-attachments/assets/7b031212-05eb-49ef-a164-930648254479)


Model Comparison After 5-Fold Cross Validation
To ensure robustness, 5-fold cross-validation was applied.
- Gradient Boosting maintained the highest average R²
- It also showed an extremely low standard deviation, indicating high stability
- Decision Tree showed moderate consistency
- Linear Regression remained stable but with low explanatory power

Cross-validation confirmed that the Gradient Boosting model was not overfitting and generalized well across different subsets of the data. ![5-Fold Cross Validation](https://github.com/user-attachments/assets/eaf73f3a-777c-41e2-98f2-bb61afb8e747)

Final Model Comparison (Single Split vs Cross Validation)
Comparing single-split results with cross-validation results showed:
- Minimal performance gap for Gradient Boosting
- Very consistent R² values between test and cross-validation
- Strong evidence of generalization

This reinforced the reliability of the model before further optimization. ![5-Fold Cross Validation](https://github.com/user-attachments/assets/d7e10c5b-702b-496c-b077-50d667019612)

Before and After Hyperparameter Tuning
Hyperparameter tuning using GridSearchCV further improved the Gradient Boosting model.
- R² increased significantly
- RMSE and MAE were substantially reduced
- Model stability remained strong

The tuned model demonstrated both higher predictive accuracy and improved bias–variance balance.
![Hyperparameter Tuning](https://github.com/user-attachments/assets/c744d7d6-3993-491e-9ab5-adead18ef5f6)

Top 3 Feature Importance
Feature importance analysis from the final tuned model revealed the most influential drivers of Total Amount:
- Shipping Cost Ratio: 0.617 (strongest impact)
- Shipping Cost: 0.218
- Shipping Cost: 0.161

This indicates that shipping-related pricing structure and basket size are the dominant factors influencing order value in this e-commerce dataset.
![Top 3 feature Importance](https://github.com/user-attachments/assets/e2c6eecc-72f4-4420-ad23-6773e42a5edf)


## Recommendation and Analysis

The analysis shows that shipping-related factors and basket size play a central role in determining the Total Amount of an order. In particular, Shipping Cost Ratio emerged as the strongest driver, indicating that the relative burden of shipping costs significantly influences overall transaction value. This suggests that customers’ spending behaviour is closely tied to how shipping charges are structured in relation to the products they purchase.

The analysis shows that shipping-related factors and basket size play a central role in determining the Total Amount of an order. In particular, Shipping Cost Ratio emerged as the strongest driver, indicating that the relative burden of shipping costs significantly influences overall transaction value. This suggests that customers’ spending behaviour is closely tied to how shipping charges are structured in relation to the products they purchase.

Based on these findings, the following recommendations are proposed:
- Optimize shipping pricing strategies, ensuring fees are structured to encourage higher basket value without negatively affecting conversion rates
- Promote bundle purchasing or multi-item discounts to increase average quantity per order
- Monitor shipping-to-order ratio metrics as part of pricing and logistics performance dashboards

Overall, integrating predictive analytics into pricing and logistics decisions can support more informed, data-driven strategies and improve revenue predictability within Amazon e-commerence business.


## AI Ethics

While this project focuses on predicting Total Amount using transactional data, it is important to consider the ethical implications of applying data science in an e-commerce environment.

Privacy:
  - Although the dataset used does not contain personally identifiable information, transactional data can still reveal purchasing patterns and behavioural          insights. In real-world applications, strict data protection policies and anonymisation practices must be enforced to safeguard customer privacy.

Fairness:
  - Features such as country or location may indirectly influence pricing or revenue predictions. Care must be taken to ensure that predictive models do not         unintentionally disadvantage specific customer groups or regions. Continuous monitoring is necessary to prevent biased outcomes.

Accuracy:
  - While the model demonstrates strong predictive performance, no model is perfectly accurate. Decisions based solely on automated predictions may lead to         incorrect pricing or operational strategies if not carefully validated. Human oversight remains important.

Accountability:
  - Clear responsibility should be defined when deploying predictive models in real business environment. Business stakeholders must understand how model outputs   are used in decision-making, particularly if they influence pricing or logistics strategies.

Transparency:
  - Using interpretable techniques such as feature importance analysis helps explain which factors drive predictions. Transparency is essential to build trust in   data-driven systems and ensure that decisions can be justified and audited when necessary.



## Source Codes and Datasets
Upload your model files and dataset into a GitHub repo and add the link here. 

Please refer here for all related files [here](https://github.com/Jason-Chan1394/itd214_project)

