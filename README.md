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

### 1. Data Inspection and Preprocessing  

- Inspected the dataset using summary statistics and structure checks  
- Verified that the variables were suitable for machine learning analysis  
- Applied feature scaling for models that require it, such as Logistic Regression and SVM  
- Performed train-test split for model development and evaluation  

### 2. Exploratory Data Analysis (EDA)  

- Examined distributions of key clinical variables  
- Compared feature values between survival and death groups  
- Visualized relationships using correlation heatmaps, pairplots, and group comparisons  
- Identified potential patterns such as higher mortality in certain clinical ranges  

### 3. Feature Engineering  

- Applied log transformation to skewed variables such as serum creatinine and creatinine phosphokinase  
- Created age-group features to capture age-related risk patterns  
- Added interaction terms such as age × serum creatinine and ejection fraction × serum creatinine  
- Compared baseline and engineered Logistic Regression models to examine the effect of new features  

### 4. Model Development  

We implemented and compared multiple models:

- Logistic Regression  
- Logistic Regression with PCA  
- Decision Tree (baseline exploration)  
- Support Vector Machine (SVM)  
- Support Vector Machine with PCA  
- Random Forest  
- Tuned Random Forest (using GridSearchCV for hyperparameter tuning)  
- XGBoost  

### 5. Model Evaluation  

We evaluated models using:

- Accuracy  
- Precision  
- Recall, especially for the death class  
- F1-score  
- ROC-AUC  
- Confusion Matrix  
- ROC Curve  

In this process, we focus on improving the recall rate to reduce the risk of missing high-risk patients.

### 6. Interpretation  

- Compared model performance and trade-offs  
- Examined which model best identifies high-risk patients  
- Interpreted Logistic Regression coefficients for engineered features  
- Interpreted results in a clinical context  


## Final Results  

We evaluated Logistic Regression, Logistic Regression with PCA, SVM, SVM with PCA, Random Forest, XGBoost, and Tuned Random Forest.

| Model | Accuracy | Death Recall | ROC-AUC |
|------|---------|-------------|---------|
| Logistic Regression | 0.800 | 0.579 | 0.855 |
| Logistic Regression + PCA | 0.783 | 0.737 | 0.861 |
| SVM | 0.717 | 0.526 | 0.856 |
| SVM + PCA | 0.767 | 0.579 | 0.791 |
| Random Forest | 0.850 | 0.632 | 0.910 |
| XGBoost | 0.850 | 0.632 | 0.850 |
| Tuned Random Forest | 0.833 | 0.684 | 0.899 |

Among all evaluated models, **Logistic Regression with PCA** achieved the highest Death Recall (0.737), which is an important metric for identifying high-risk patients.

At the same time, **Random Forest** achieved the highest ROC-AUC (0.910), showing the strongest overall separability between classes.

The **Tuned Random Forest** remained a strong model with high recall and strong overall performance, making it a competitive option when balancing multiple metrics.


## Conclusion
In this project, we constructed and compared multiple machine learning models to predict mortality risk among heart failure patients using clinical indicators.

The results show that different models offer different strengths. Logistic Regression with PCA achieved the highest death recall, while Random Forest achieved the highest ROC-AUC. Tuned Random Forest also delivered strong and balanced performance across evaluation metrics.

Overall, our findings suggest that machine learning can be a useful tool for early mortality risk assessment, and that the best model choice may depend on whether the main priority is recall or overall classification performance.


## Limitations  

- The dataset is relatively small (~300 samples), which may limit model generalizability  
- The model is trained on a single dataset and may not generalize well to other populations  



## Tools and Libraries  

- Python  
- Pandas  
- NumPy  
- Scikit-learn  
- Matplotlib  
- Seaborn  
- XGBoost  

Version control and collaboration are managed through GitHub.


## Repository Structure  
- `heart_failure_clinical_records_dataset.csv`  
  Raw dataset used for analysis  

- `eda.ipynb`  
  Exploratory Data Analysis (data overview, distributions, correlations)  

- `feature_engingeering.ipynb`  
  Feature engineering experiments and coefficient-based interpretation  

- `modeling.ipynb`  
  Baseline model development using Logistic Regression, Decision Tree, and Random Forest  

- `model_comparison.ipynb`  
  Systematic model comparison, PCA-based experiments, tuning, and final evaluation  

- `README.md`  
  Project documentation  
