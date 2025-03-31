
# Bank Customer Churn Analysis

## 1. Introduction

Customer retention is a critical concern for banks, as acquiring new customers often costs more than retaining existing ones. This project analyzes factors contributing to customer churn in a bank, aiming to identify patterns and develop predictive models to foresee and mitigate potential churn.

## 2. Dataset Overview

- **Source**: [Kaggle - Bank Customer Churn Dataset](https://www.kaggle.com/datasets/radheshyamkollipara/bank-customer-churn/data)
- **Description**: The dataset comprises 10,000 bank customers, each represented by 17 features and a target variable indicating whether the customer exited the bank.

### 2.1 Features

- **RowNumber**: Index of the row.
- **CustomerId**: Unique identifier for the customer.
- **Surname**: Customer's last name.
- **CreditScore**: Credit score of the customer.
- **Geography**: Country of residence.
- **Gender**: Male or Female.
- **Age**: Age of the customer.
- **Tenure**: Number of years the customer has been with the bank.
- **Balance**: Account balance.
- **NumOfProducts**: Number of bank products used.
- **HasCrCard**: Indicates if the customer has a credit card (1: Yes, 0: No).
- **IsActiveMember**: Indicates if the customer is an active member (1: Yes, 0: No).
- **EstimatedSalary**: Estimated annual salary.
- **Exited**: Target variable (1: Customer left the bank, 0: Customer stayed).
- **Complain**: Indicates if the customer had filed a complaint (1: Yes, 0: No).
- **Satisfaction Score**: Customer's satisfaction rating.
- **Card Type**: Type of card held by the customer.

## 3. Data Exploration and Preprocessing

### 3.1 Data Cleaning

- **Duplicates**: No duplicate entries were found.
- **Missing Values**: The dataset was complete with no missing values.

### 3.2 Data Balance

- **Churn Distribution**: The dataset is imbalanced, with a higher proportion of customers who did not exit compared to those who did.

### 3.3 Unique Values

- **Categorical Features**: Identified unique values in categorical features such as `Geography`, `Gender`, and `Card Type` to understand the diversity within these categories.

### 3.4 Feature Exploration

- **Irrelevant Features**: `RowNumber`, `CustomerId`, and `Surname` were deemed non-informative for predicting churn and were excluded from further analysis.
- **Numerical Features**: Analyzed distributions and relationships of numerical features like `CreditScore`, `Age`, `Balance`, and `EstimatedSalary` with respect to churn.
- **Categorical Features**: Examined the impact of categorical variables on churn rates.

## 4. Exploratory Data Analysis (EDA)

### 4.1 Univariate Analysis

- **Age**: Older customers exhibited lower churn rates.
- **CreditScore**: Higher credit scores correlated with reduced churn.
- **Balance**: Customers with higher balances were less likely to leave.

### 4.2 Bivariate Analysis

- **Geography vs. Churn**: Certain regions had higher churn rates.
- **Gender vs. Churn**: Gender appeared to have a minimal effect on churn.
- **IsActiveMember vs. Churn**: Active members showed significantly lower churn rates.

## 5. Feature Engineering

- **One-Hot Encoding**: Applied to categorical variables (`Geography`, `Gender`, `Card Type`) to convert them into numerical format suitable for modeling.
- **Scaling**: Standardized numerical features to ensure uniformity in model inputs.

## 6. Modeling

### 6.1 Model Selection

Evaluated multiple classification models:

- **Logistic Regression**
- **Decision Tree**
- **Random Forest**
- **Support Vector Machine (SVM)**

### 6.2 Model Evaluation

- **Metrics Used**: Accuracy, Precision, Recall, F1 Score, and Confusion Matrix.
- **Performance**: XGBoost and Random Forest demonstrated superior performance, balancing precision and recall effectively.

## 7. Key Findings

- **Active Membership**: Strongly associated with retention; inactive members had higher churn rates.
- **Age Factor**: Younger customers were more prone to churn.
- **Satisfaction Score**: Lower satisfaction scores were indicative of higher churn likelihood.
- **Balance and Salary**: While higher balances correlated with retention, estimated salary had a less pronounced effect.

## 8. Conclusion

This analysis provided meaningful insights into the key drivers of customer churn. By identifying patterns in demographic, behavioral, and transactional data, the bank can take **proactive steps** to reduce churn and improve customer retention.

### 🔑 Actionable Recommendations

1. **Engage Inactive Customers**  
   Inactive members are significantly more likely to churn. The bank should initiate re-engagement campaigns—such as personalized offers, service reminders, or loyalty incentives—to encourage usage and reinforce relationships.

2. **Target Younger Customers with Tailored Programs**  
   Younger age groups showed higher churn rates. This segment may respond better to mobile-first banking solutions, financial education, gamified saving features, and exclusive offers aimed at their lifestyle and financial goals.

3. **Prioritize High-Risk, Low-Satisfaction Customers**  
   Customers with low satisfaction scores are much more likely to leave. Conduct periodic satisfaction surveys and flag low scorers for follow-up. Offering concierge support or problem resolution teams for this group could boost loyalty.

4. **Promote Products That Increase Customer Stickiness**  
   Encourage use of multiple bank products (e.g., loans, insurance, investment accounts). Customers with more product engagement typically demonstrate lower churn risk.

5. **Monitor Geographic Trends**  
   Churn varies by region. Use this insight to focus regional marketing efforts or review service coverage in high-churn areas.

6. **Predict Churn with ML Models**  
   Leverage predictive models like XGBoost or Random Forest (from this project) to score customers based on churn probability. Use these scores to triage intervention efforts more efficiently.

## 9. Future Work

- **Model Interpretability**: Utilize techniques like SHAP values to better understand model predictions.
- **Class Imbalance Handling**: Apply methods such as SMOTE to address data imbalance.
- **Deployment**: Develop a user-friendly interface for the predictive model to assist bank staff in identifying at-risk customers.

## 10. Repository Structure

```
├── bank_churn_data.csv           # Dataset file
├── bank_churn_analysis.ipynb     # Jupyter Notebook with analysis
├── README.md                     # Project documentation
└── requirements.txt              # List of required packages
```

## 11. How to Use

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/heathclief0402/bank_customer_chrun_pred.git
   ```
2. **Navigate to the Project Directory**:
   ```bash
   cd bank_customer_chrun_pred
   ```
3. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```
4. **Run the Jupyter Notebook**:
   ```bash
   jupyter notebook Bank_churn_prediction_off.ipynb
   ```


