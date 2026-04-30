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

Heart failure is a serious condition with a high risk of mortality. Being able to identify high-risk patients early can help doctors make better treatment decisions.

In this project, we use clinical data to build machine learning models that predict whether a heart failure patient will die during the follow-up period. We compare different models to see which one performs best.

Besides prediction, we also look at which clinical features (such as age, ejection fraction, and serum creatinine) are most related to mortality risk.

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

- Checked for missing values and data inconsistencies  
- Verified binary variables (e.g., diabetes, smoking) were correctly encoded  
- Applied feature scaling for models that require it (e.g., Logistic Regression, SVM)  
- Performed train-test split with stratification to preserve class distribution  

### 2. Exploratory Data Analysis (EDA)  

- Examined distributions of key clinical variables  
- Compared feature values between survival and death groups  
- Visualized relationships using correlation heatmaps  
- Identified potential patterns such as higher mortality in certain clinical ranges  

### 3. Feature Engineering  

- Removed redundant or highly correlated features where necessary  
- Prepared data for different models (scaled vs non-scaled versions)  

### 4. Model Development  

We implemented and compared multiple models:

- Logistic Regression (baseline model)  
- Support Vector Machine (SVM)  
- Random Forest  
- Tuned Random Forest (using GridSearchCV for hyperparameter tuning)  

### 5. Model Evaluation  

We evaluated models using:

- Accuracy  
- Precision  
- Recall (especially important for detecting high-risk patients)  
- F1-score  
- ROC-AUC  

In this process, we focus on improving the recall rate to reduce the risk of missing high-risk patients.

### 6. Interpretation  

- Compared model performance and trade-offs  
- Examined which model best identifies high-risk patients  
- Interpreted results in a clinical context  


## Final Results  

We evaluated four models: Logistic Regression, SVM, Random Forest, and Tuned Random Forest.

| Model | Accuracy | Death Recall | ROC-AUC |
|------|---------|-------------|---------|
| Logistic Regression | 0.80 | 0.579 | 0.855 |
| SVM | 0.72 | 0.526 | 0.856 |
| Random Forest | 0.85 | 0.632 | 0.910 |
| Tuned Random Forest | 0.83 | 0.684 | 0.899 |

Among these models, the Tuned Random Forest achieved the highest Death Recall (0.684), which is the most important metric for this task.

Although the standard Random Forest achieved the highest ROC-AUC (0.910), the Tuned Random Forest provides a better balance between Recall and overall performance.


## Conclusion
In this project, we constructed and compared various machine learning models with the aim of utilizing clinical data to predict the likelihood of mortality among heart failure patients during the follow-up period.

Among all the models evaluated, the tuned Random Forest model demonstrated the best performance, proving most effective at identifying patients at high risk of mortality.

Overall, our results demonstrate that machine learning can serve as an effective tool to assist clinicians in identifying high-risk patients at an earlier stage, thereby supporting the formulation of more optimized treatment decisions.


## Limitations  

- The dataset is relatively small (~300 samples), which may limit model generalizability  
- The model is trained on a single dataset and may not generalize well to other populations  



## Tools and Libraries  

- Python  
- Pandas  
- NumPy  
- Scikit-learn  

Version control and collaboration are managed through GitHub.


## Repository Structure  
- `heart_failure_clinical_records_dataset.csv`  
  Raw dataset used for analysis  

- `eda.ipynb`  
  Exploratory Data Analysis (data overview, distributions, correlations)  

- `feature_engingeering.ipynb`  
  Data preprocessing and feature preparation  

- `modeling.ipynb`  
  Training machine learning models  

- `model_comparison.ipynb`  
  Model evaluation, tuning, and comparison  

- `README.md`  
  Project documentation  
