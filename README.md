# Credit Card Customer Churn Prediction

This project aims to predict customer churn for a credit card company using machine learning. By analyzing various customer attributes, the objective is to identify which customers are more likely to churn and provide actionable insights for business retention strategies. Models implemented include Logistic Regression, Random Forest, Gradient Boosting, and XGBoost, evaluated for performance and predictive accuracy.

## Table of Contents
1. [Project Overview](#project-overview)
2. [Data Collection](#data-collection)
3. [Exploratory Data Analysis](#exploratory-data-analysis)
4. [Feature Engineering](#feature-engineering)
5. [Model Training & Evaluation](#model-training--evaluation)
6. [Predictions on New Data](#predictions-on-new-data)
7. [Conclusion and Business Insights](#conclusion-and-business-insights)
8. [Limitations and Future Work](#limitations-and-future-work)

---

## Project Overview
The primary goal of this project is to predict which customers are more likely to churn based on demographic, financial, and behavioral features, including **credit score, age, balance,** and **estimated salary**. The analysis demonstrates that **age** is the most significant predictor of churn, followed by **product number** and **active membership status**.

## Data Collection
Data for this project was sourced from [Kaggle's Bank Customer Churn dataset](https://www.kaggle.com/datasets/gauravtopre/bank-customer-churn-dataset/data).

## Exploratory Data Analysis
During the exploratory phase:
- **Age** and **credit score** were identified as key differentiators between churners and non-churners.
- There is a slight gender imbalance, with more female churners than male churners. However, further analysis showed that this may be sample bias rather than a significant predictor.
- Churn likelihood does not vary strongly with **balance** or **estimated salary**, suggesting lifestyle factors, rather than financials, may influence churn.

## Feature Engineering
- **Encoding**: Categorical features such as **country** and **gender** were one-hot encoded.
- **Target Variable**: The target feature, `churn`, was analyzed against all numeric and categorical attributes.
- **Correlations**: Age showed the strongest correlation with churn, indicating potential for age-based segmentation in customer retention strategies.

## Model Training & Evaluation
### Logistic Regression
- Achieved an accuracy of **79%** but limited recall on identifying churn cases.

### Random Forest
- Initial accuracy: **87%**.
- After hyperparameter tuning, accuracy slightly decreased due to possible overfitting, but cross-validation confirmed model stability.
- Feature importance highlighted **age** as the most impactful feature.

### Gradient Boosting & XGBoost
- **Gradient Boosting** provided strong class separation but showed confidence in predicting only the majority class.
- **XGBoost** accuracy: **88%**, with improved handling of class imbalance.

### Final Model Selection
Based on evaluation metrics, Random Forest and XGBoost emerged as the best models, balancing accuracy and interpretability.

## Predictions on New Data
Sample predictions on new customer data indicate that age and active membership status heavily influence churn likelihood. Both Random Forest and XGBoost provided consistent predictions on test cases, showing the models’ robustness.

## Conclusion and Business Insights
Key business insights from this analysis include:
- **Age-Based Churn Propensity**: Age is a significant churn predictor, suggesting that targeted retention strategies should focus on younger customers who show higher churn tendencies.
- **Proactive Engagement Strategies**: Retention initiatives could involve loyalty programs for older customers and more flexible product options for younger demographics.
- **Enhanced Customer Segmentation**: Age-based customer segmentation enables more precise marketing and retention efforts.

## Limitations and Future Work
This project faced limitations, such as:
- **Age Distribution Bias**: The dataset skews towards the 20-50 age range, particularly around 30-40. This bias may overstate age’s influence on churn.
- **Generalization Potential**: The model’s applicability across broader demographics requires additional validation and potentially rebalanced age groups.

Future work will focus on addressing these limitations by:
1. Exploring alternative sampling techniques for balanced age representation.
2. Experimenting with other machine learning algorithms or feature engineering techniques to enhance generalization.
