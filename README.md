# CS439_Project

## Early Prediction of Heart Failure Outcomes Using Clinical Indicators  


## Course Information  

Rutgers University – New Brunswick  
CS439 Introduction to Data Science  
Spring 2026  


## Team Members  

- Zhitong Guo (zg259)  
- Hongyu Shi (hs1208)  


## Project Overview  

Heart failure is a serious cardiovascular condition associated with high mortality rates.  
Early risk prediction can assist clinicians in identifying high-risk patients and improving treatment strategies.

This project aims to build and evaluate machine learning models to predict whether a patient with heart failure will experience a death event during the follow-up period using clinical health indicators.

In addition to predictive performance, we focus on identifying which clinical features contribute most significantly to mortality risk.


## Research Question  

Can clinical measurements and health conditions accurately predict whether a heart failure patient will experience a death event during follow-up?


## Dataset  

**Source:** Kaggle – Heart Failure Clinical Data  
**Link:**  
https://www.kaggle.com/datasets/andrewmvd/heart-failure-clinical-data  

The dataset contains clinical records of patients diagnosed with heart failure.  
Each row represents one patient observation.

### Target Variable  

- `DEATH_EVENT`  
  - 1 = Patient died during follow-up  
  - 0 = Patient survived  

### Key Features  

- Age  
- Anemia status  
- High blood pressure  
- Diabetes  
- Smoking status  
- Ejection fraction  
- Serum creatinine  
- Serum sodium  
- Platelets count  
- Follow-up time  

The dataset contains approximately 300 patient records and a mix of continuous and binary variables.


## Project Workflow  

### 1. Data Cleaning and Preprocessing  

- Checking for missing or inconsistent values  
- Encoding binary categorical variables  
- Scaling continuous variables if necessary  
- Detecting outliers in clinical measurements  
- Train-test split

### 2. Exploratory Data Analysis (EDA)  

- Summary statistics  
- Feature distribution visualization  
- Correlation analysis  
- Comparison between survival and death groups  

### 3. Feature Engineering  

- Evaluating multicollinearity  
- Selecting relevant predictors  
- Considering interaction effects if appropriate  

### 4. Model Development  

Models to be implemented:

- Logistic Regression (baseline)  
- Decision Tree  
- Random Forest  
- (Optional) XGBoost  

### 5. Model Evaluation  

Performance metrics:

- Accuracy  
- Precision  
- Recall  
- F1-score  
- ROC-AUC  

Cross-validation will be used to improve reliability and reduce overfitting due to the relatively small dataset size.

### 6. Interpretation  

- Feature importance analysis  
- Clinical interpretation of risk factors  
- Comparison of model trade-offs  


## Tools and Libraries  

- Python  
- Pandas  
- NumPy  
- Scikit-learn  

Version control and collaboration are managed through GitHub.


## Repository Structure  
