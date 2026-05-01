# Netflix Customer Churn Prediction: End-to-End Machine Learning Pipeline

## Overview

This project builds a complete machine learning pipeline to predict customer churn for a subscription-based streaming platform similar to Netflix.

The goal is to identify users who are most likely to cancel their subscriptions based on engagement behavior, subscription patterns, and demographic attributes. The insights can help improve retention strategies and reduce customer loss.

---

## Methodology

The dataset contains customer-level information, including:

- Engagement metrics (watch hours, login frequency)  
- Subscription details (plan type, monthly fee, number of profiles)  
- Demographics (age, gender, region)  
- Behavioral preferences (device, favorite genre, payment method)  

### Data Preparation

- Data cleaning and consistency checks  
- Transformation of skewed variables using log and Box-Cox methods  
- Feature scaling for model compatibility  
- Encoding categorical variables  
- Feature engineering to capture deeper behavioral patterns  

 These steps improve model performance and reveal underlying user behavior.

---

## Feature Engineering

New features were created to better capture engagement and value perception:

- Watch efficiency (watch time relative to usage)  
- Login-to-watch ratio  
- Fee per profile  

 These features provide stronger signals for predicting churn.

---

## Models Applied

Multiple models were trained and compared:

### 1. Logistic Regression
- Simple and interpretable baseline  
- Strong performance despite linear structure  

---

### 2. Support Vector Machine (SVM)
- Captures non-linear boundaries  
- Performs well but limited in modeling complex interactions  

---

### 3. Random Forest
- Captures non-linear relationships  
- High accuracy and strong generalization  
- Robust against overfitting  

---

### 4. XGBoost
- Best performing model  
- Captures complex feature interactions  
- Highly accurate and stable  

---

## Model Evaluation

Models were evaluated using:

- Accuracy  
- ROC-AUC  
- Cross-validation performance  

### Key Results:

- Logistic Regression: ~90% accuracy  
- SVM: ~91% accuracy  
- Random Forest: ~98% accuracy, ROC-AUC ≈ 0.997  
- XGBoost: ~99.5% accuracy, ROC-AUC ≈ 0.999  

 XGBoost achieved the best performance with excellent generalization.
 
**As a short note** The model achieves very high performance metrics, which are less common in real-world applications. However, this can be explained by the strong behavioral signals present in the dataset, particularly user engagement features such as watch time and login frequency.

To ensure the reliability of these results, additional validation steps were performed, including cross-validation and label randomization tests. These checks confirmed that the model is not affected by data leakage and that the predictive performance reflects genuine patterns in the data.

Overall, the results indicate that customer churn in this dataset is highly predictable based on user behavior.

---

## Model Validation

To ensure reliability:

- Cross-validation confirmed consistent performance  
- Data leakage test (randomized labels) showed no hidden bias  
- Class balance was verified  

High performance reflects real predictive power, not overfitting or leakage.

---

## Model Interpretation

### Feature Importance

- Engagement features dominate:
  - Watch hours  
  - Average watch time per day  
  - Days since last login  

 Viewing behavior is the strongest predictor of churn.

---

### Partial Dependence Analysis

- Low engagement lead to high churn probability  
- Increased activity lead to sharp drop in churn risk  
- After a threshold, additional usage has diminishing impact  

---

### SHAP Analysis

- Confirms engagement as the primary driver  
- Demographics (like age) have minimal impact  
- Interaction effects are limited compared to behavioral features  

---

## Key Findings

- Customer churn is driven primarily by engagement  
- Low activity users are significantly more likely to leave  
- Subscription type and pricing play secondary roles  
- Demographic features have minimal predictive power  

 Behavior matters far more than demographics.

---

## Business Insight 

Based on the result of the test it is recommended to

- Focus retention efforts on low-engagement users  
- Encourage consistent viewing behavior  
- Use personalized recommendations and reminders  
- Identify churn risk early using behavioral signals  

 These strategies can significantly reduce churn and improve retention.

---

## Skills Demonstrated

- Supervised machine learning  
- Model comparison and evaluation  
- Feature engineering and transformation  
- XGBoost, Random Forest, SVM, Logistic Regression  
- Model validation and leakage detection  
- Explainability (feature importance, PDP, SHAP)  
- Translating models into business insights  
