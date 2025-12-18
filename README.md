# Nigerian Telecom Customer Churn Prediction
Project Status: Completed

Domain: Telecommunications / Data Science

Techniques: Machine Learning (Gradient Boosting), SMOTE, Exploratory Data Analysis

# 1. Introduction
In the highly competitive telecommunications sector, acquiring a new customer is significantly more expensive than retaining an existing one. For telecom providers in Nigeria (like MTN), high churn rates directly impact revenue and market share.

This project focuses on building a robust Machine Learning system to identify customers who are at risk of leaving the service (churning). By moving from reactive measures to proactive predictions, the business can intervene early with targeted retention strategies.

# 2. Aim and Objectives
Aim: To develop a predictive model that accurately identifies telecom customers likely to churn.

Objectives:

Analyze: Perform Exploratory Data Analysis (EDA) to identify key patterns and drivers of churn (e.g., Network Quality, Price).

Process: Clean and engineer features from raw customer data, addressing class imbalance using SMOTE.

Build: Train and optimize Machine Learning models (Gradient Boosting).

# 3. Data Information
Source: The dataset contains customer demographics, service usage, and subscription details for a Nigerian Telecom provider. Size: 974 Records | 17 Features

# Metadata (Key Columns)

Column Name -    Description

Customer - ID Unique identifier for each customer.

Age - Customer's age.

Gender - Male or Female.

State - The Nigerian state where the customer resides.

MTN Device - Type of device used (e.g., 4G Router, Mobile SIM).

Subscription Plan - Current data or voice plan (e.g., Daily Plan, Unlimited).

Satisfaction Rate - Customer rating (1-5 scale).

Customer Review - Text sentiment (Excellent, Good, Poor).

Total Revenue - Total money spent by the customer.

Customer Churn Status - Target Variable: 'Yes' (Churned) or 'No' (Retained).

Reasons for Churn - Reason for leaving.

# 4. Research Questions
  1. What are the primary factors driving customer attrition in Nigeria?

  2. Does the type of device (e.g., 5G Router vs. Mobile SIM) impact retention?

  3. Are high-value customers (High Revenue) more or less likely to churn?

  4. Can we accurately predict churn despite the class imbalance in the dataset?

# 5. Methodology
## 5.1 Data Cleaning & Preprocessing
Dropped Identifiers: Removed Customer ID, Full Name, and Date of Purchase.

Leakage Prevention: Removed Reasons for Churn from the training set.

Feature Engineering: Created Average Monthly Spending (Total Revenue / Tenure) to analyze spending power.

Encoding: Applied One-Hot Encoding to categorical variables (State, Device, Plan).

## 5.2 Addressing Imbalance
The dataset was heavily imbalanced (~71% Retained vs. ~29% Churned).

Technique Used: SMOTE (Synthetic Minority Over-sampling Technique) and Upsampling.

Result: Balanced the training data to ensure the model learned to recognize churners effectively, improving Recall from <10% to >50%.

## 5.3 Modeling
We experimented with the algorithm:

Gradient Boosting Classifier

Final Model Performance (Gradient Boosting):

Accuracy: 73%

Precision: 54%

Recall: 49% 

# 6. Key Insights from EDA
Spending Power: High-value customers (Big Spenders) are actually more likely to churn than low-value users.

Lifecycle Risk: A significant spike in churn occurs between 6-12 months of tenure.

Device Impact: Users with 5G Broadband Routers showed the highest churn rate (45%), suggesting potential coverage or hardware issues.

Satisfaction: There is a clear threshold; customers with a satisfaction rating < 2.5 are nearly guaranteed to churn.

# 7. Recommendations
  VIP Retention Program: Target high-revenue customers (>₦50k/mo) with personalized calls and exclusive offers, as they are a high-risk segment.
  
  6-Month Loyalty Bonus: Implement an automated reward at the 6-month mark to bridge the "first-year" drop-off gap.
  
  Technical Audit: Investigate network performance for 5G Router users, given their abnormally high attrition rate.
  
  Price Matching: Competitor offers are a top churn driver; implement price-matching guarantees for customers with "Excellent" satisfaction ratings who are at risk of leaving.

# Tools Used
  Python (Pandas, NumPy)
  
  Scikit-Learn (Modeling, Preprocessing)
  
  Imbalanced-Learn (SMOTE)
  
  Matplotlib / Seaborn (Visualization)
