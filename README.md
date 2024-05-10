Telecom_churn
Introduction

Customer churn is a significant challenge for businesses, leading to revenue loss and a decrease in customer base. It refers to the loss of customers or subscribers for any reason. Businesses track churn as a percentage of lost customers compared to the total number of customers over a given period, usually monthly. Identifying and retaining customers likely to churn is crucial.

Objective

The project aimed to analyze the Telco dataset to understand why customers left and identify patterns through data analysis. Twelve Machine learning techniques such as ANN, RNN, LSTM, Random Forest, and XGBoost have been used to predict future churn.

Dataset Overview The dataset contained customer details of size 7043 rows and 21 columns, from a telecommunications company, including demographics (gender, family setup), services used (phone, multiple lines, internet, security features, support services, streaming), and account details (contract type, payment method, billing amounts, churn record). By analyzing these factors, we aimed to predict which customers may churn.

Exploratory Data Analysis

Churn Distribution:

A pie chart depicting churn distribution showed that out of 7043 clients, 5174 (73.5%) did not churn, while 1869 (26.5%) did churn.
Tenure by Churn:

A histogram plot revealed that after the fourth month, the number of clients who churn decreased significantly, while the number of clients who do not churn peaked on the seventh month.
Monthly Charges by Churn:

A histogram and density plot for monthly charges by churn indicated multiple peaks, suggesting that different customers preferred different packages.
Total Charges by Churn:

The total charges distribution was skewed to the left, indicating that many customers had low total charges, potentially indicating newer customers.
Gender Distribution:

The gender distribution showcased a balanced ratio of males to females, with churn not significantly influenced by gender.
Contract Distribution:

The churn rate was highest for month-to-month subscriptions at 43%, followed by one-year contracts at 11%, and two-year contracts at 3%.
Payment Method:

Customers with an electronic check as a payment method had the highest churn rate of 45%, while those using a credit card had the lowest churn rate at 15%.
Internet Service:

Customers with optical fiber internet had the highest churn rate at about 42%, while those without internet service had the lowest churn rate at about 7%.
Relationship Between Payment Method and Internet Service:

Fiber optic clients preferred electronic checks as a payment method, while those without internet service preferred mailed checks.
Tech Support:

Customers without tech support had the highest churn rate at 31%.
Count Plot for Remaining Columns with against Churn:

The count plot described the remaining columns (Churn, Total Charges, Monthly Charges, Tenure, Gender, Internet Service, Tech Support, Contract, and Payment Method) with against churn.
Correlation Matrix and Feature Importance:

The correlation matrix and feature importance analysis identified several impactful features:
Tenure: The length of time the customer has been with the company.
Monthly Charges: The amount billed to the customer each month.
Total Charges: The total amount billed to the customer.
Internet Service: The type of internet service the customer has.
Contract: The type of contract the customer has (e.g., month-to-month, one year, two years).
Payment Method: The customer's preferred payment method.
Observations from the Correlation Matrix:

Customers with fiber optic internet or who use electronic checks are more likely to cancel their service, possibly due to higher costs or billing issues.
Longer contract durations are associated with lower churn rates, indicating the effectiveness of longer-term commitments in retaining customers.
Additional tech services such as online security, tech support, or device protection are associated with lower churn rates, highlighting their value in enhancing customer loyalty.
Older customers are more likely to churn, emphasizing the need to tailor services to older demographics.
Customer Segmentation (K-means Clustering):

K-means clustering was applied to identify customer segments at risk of churning based on the impactful features.
Four clusters were identified:
Cluster 0: Medium to high monthly charges, range of tenure lengths.
Cluster 1: Higher monthly charges, longer tenure, indicating loyal customers.
Cluster 2: Lower monthly charges, shorter tenure, potentially price-sensitive customers.
Cluster 3: Lower to medium monthly charges, broad range of tenure, budget-conscious customers.
Cluster Analysis:

Cluster 0: Balanced churn and retention.
Cluster 1: High retention, likely satisfied customers.
Cluster 2 and Cluster 3: Moderate to low churn, may benefit from targeted improvements or loyalty programs.
Correlation and Distribution Analyses:

Fiber optic internet, month-to-month contracts, higher monthly charges, and shorter tenure are associated with higher churn rates.
Longer tenure, two-year contracts, and certain additional services are associated with lower churn rates.
Model Training:

Categorical variables were encoded using LabelEncoder and OneHotEncoder.
The dataset was split into training and test sets.
Feature scaling was applied to normalize the data.
SMOTE (Synthetic Minority Over-sampling Technique) was used to handle imbalanced data.
Deep Learning Models:

RNN, ANN, and LSTM were used.
Test Loss and Test Accuracy for each model:
RNN: Test Loss = 0.452, Test Accuracy = 0.781
ANN: Test Loss = 0.459, Test Accuracy = 0.772
LSTM: Test Loss = 0.436, Test Accuracy = 0.786
Supervised ML Models:

A combination of 9 algorithms was used: Random Forest, Gradient Boosting, Support Vector Machine, Logistic Regression, K-Nearest Neighbors, Decision Tree, Ada Boost, XG Boost, and Naive Bayes.
Model: Random Forest Test Accuracy: 0.803 %
-Model: Gradient Boosting Test Accuracy: 0.806 %

-Model: Support Vector Machine Test Accuracy: 0.752 %

-Model: Logistic Regression Test Accuracy: 0.757 %

-Model: K-Nearest Neighbors Test Accuracy: 0.761 %

Model: Decision Tree Test Accuracy: 0.776 %

Model: Ada Boost Test Accuracy: 0.801 %

Model: XG Boost Test Accuracy: 0.808 %

Model: Naive Bayes Test Accuracy:0.76 %

Best Model:

XGBOOST model had the highest accuracy of 0.808, rounded to 81%.
A model pipeline using MinMaxScaler and XGBOOST Classifier achieved an accuracy of 0.81%.
Model Evaluation of the Best Model:
Confusion Matrix: [[953 83] [187 186]]

Precision: 0.691 Recall: 0.499 F1 Score: 0.579

Summary:
XGBOOST algorithm emerged as the best model with an accuracy of 81%, which is higher than all the other algorithms.
Therefore, the XGBOOST is recommended as the best predictor for the churn model to be deployed.
