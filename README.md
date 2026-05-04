# Student Pass/Fail Prediction based on Alcohol Consumption

## Project Overview

This project uses data collected from Portuguese secondary school students enrolled in a Mathematics course. The goal is to predict whether a student will pass or fail their final exam (`G3 >= 10` = Pass) based on demographic, social, and lifestyle features — including alcohol consumption habits.

**Dataset:** `student-mat.csv` — 395 students, 33 features 
**Source:** https://www.kaggle.com/datasets/uciml/student-alcohol-consumption

**Method:** Binary Classification (Pass / Fail)  
**Final Model:** Random Forest Classifier  
**Evaluation Metrics:** Accuracy, Precision, Recall, F1-Score, AUC-ROC

**Key Question:** Can lifestyle and demographic factors. Such as alcohol consumption, study time, and family background. Reliably predict whether a student will pass their math course?



**Workflow:** 
1. Data Wrangling
Drop leakage columns. G1, G2, G3. Including intermediate grades would allow our model to reach accuracy of about 90%, which would lead to overfitting/leakage as these columns would not be available at prediction time.

2. Exploratory Data Analysis
Visualize Pass/Fail distribution.
Visualize Alcohol Consumption vs Pass Rate.
Visualize our Key Predictors based on Outcome.
Parental Education vs Pass Rate
Correlation matrix of our features.

3. Modeling
Used a test split of 80/20.
Set up baseline accuracy using DummyClassifier. Ability to blindly select pass.
Set up two models to search for a better performer against the baseline. Logistic Regression and RandomForest.

4. Evaluation
Used Model AUC scores and f1-scores to note the best performing model against the baseline.
Then extracted the best performing features.


**Results:**
Train:
Baseline Accuracy: 67.1%
Logistic Regression Accuracy: 65.8% AUC: 0.593
RandomForest Accuracy: 69.6% AUC: 0.642

Test:
Classification Report — Random Forest (Test Set):
              precision    recall  f1-score   support
    Fail (0)       0.55      0.42      0.48        26
    Pass (1)       0.75      0.83      0.79        53
    accuracy                           0.70        79
   macro avg       0.65      0.63      0.63        79
weighted avg       0.68      0.70      0.68        79


Top Features:
failures, absences, goout (going out with friends), age, fedu (father's education), Walc (weekend alcohol consumption) and health.

<img width="884" height="684" alt="download-7" src="https://github.com/user-attachments/assets/5ca682cf-42c8-4c1e-a0ce-1892ceff5e1b" />





  
