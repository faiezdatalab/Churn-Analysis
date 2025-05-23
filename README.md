# Churn-Analysis

## Customer Churn Analysis Project

#### Project Overview

This project analyzes customer churn behavior for a telecom company, aiming to identify key factors influencing customer attrition. Understanding churn drivers helps the business develop targeted retention strategies, optimize pricing, and improve customer satisfaction, ultimately reducing churn rates and increasing revenue.

#### Dataset Description

The dataset contains customer demographic information, service details, contract information, payment methods, and churn status. Key columns include:
* customerID: Unique identifier for each customer
* gender, SeniorCitizen, Partner, Dependents
* tenure: Number of months the customer has stayed with the company
* PhoneService, MultipleLines, InternetService and related service subscriptions
* Contract: Type of contract (Month-to-month, One year, Two year)
* PaymentMethod and PaperlessBilling
* MonthlyCharges and TotalCharges
* Churn: Target variable indicating if the customer churned (Yes/No)

#### Data Preprocessing

* Converted TotalCharges from object to numeric, handling errors by coercion.
* Label encoded binary categorical columns (gender, Partner, Dependents, PhoneService, PaperlessBilling, Churn).
* One-hot encoded multi-category columns such as MultipleLines, InternetService, Contract, and PaymentMethod.
* Dropped unnecessary columns like customerID, derived tenure groups, and some redundant dummy variables.
* Final dataframe contains only relevant numeric and encoded features for analysis and modeling.

#### Exploratory Data Analysis (EDA)

Correlation Analysis with Churn
* Computed correlation coefficients to identify features with the strongest positive and negative correlation to churn.
* Visualized top 5 positive and negative correlations using a bar plot with warm (positive) and cool (negative) color schemes.

#### Key Findings:

Negative Correlations (Customer Loyalty Drivers):
Feature	Correlation	Insight
* Tenure	-0.352	Longer-tenured customers are less likely to churn.
* Contract (Two-Year)	-0.302	Two-year contracts strongly reduce churn risk.
* Total Charges	-0.199	Higher total payments indicate longer relationships.
* Contract (One-Year)	-0.178	One-year contracts also reduce churn, but less than two-year.
* Online Security (Yes)	-0.171	Security service subscription enhances retention.

Positive Correlations (Churn Risk Factors):
Feature	Correlation	Insight
* Internet Service: Fiber optic	0.308	Fiber optic users have higher churn, possibly due to cost.
* Payment Method: Electronic check	0.302	Electronic check users churn more, indicating financial risk.
* Monthly Charges	0.193	Higher monthly bills correlate with higher churn.
* Paperless Billing	0.192	Digital billing users churn more, possibly tech-savvy churn.
* Senior Citizen	0.151	Older customers churn more, possibly due to affordability.

#### Additional EDA Visualizations
* Count plots showing churn distribution by contract types (One-year and Two-year).
* Summary statistics and KDE plots for MonthlyCharges by churn groups, highlighting higher charges among churned customers.
* Correlation heatmap to visualize overall feature relationships.

#### Business Implications & Recommendations
* Promote Long-Term Contracts: Incentivize customers to choose 1- or 2-year contracts to increase retention.
* Target High-Monthly-Charge Customers: Offer value bundles, discounts, or premium support to reduce churn among expensive customers.
* Improve Fiber Optic Service Experience: Investigate reasons for churn and enhance service quality or pricing for fiber optic users.
* Monitor Payment Methods: Provide alternative or discounted payment options for customers using electronic checks.
* Engage Senior Citizens: Tailor customer support and billing options to senior customers to reduce churn.

### Conclusion

This analysis offers actionable insights by highlighting the factors influencing customer churn. Using these insights, the company can design focused retention campaigns, optimize pricing models, and improve customer satisfaction — leading to lower churn rates and stronger customer loyalty.

#### Technical Details

* Libraries Used: pandas, numpy, seaborn, matplotlib, scikit-learn

* Preprocessing: Label Encoding, One-Hot Encoding, Data Cleaning

* Visualizations: Bar plots, Count plots, KDE plots, Correlation heatmaps

* Correlation Analysis: Pearson correlation coefficients with churn target
