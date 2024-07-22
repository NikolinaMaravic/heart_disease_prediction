# heart_disease_prediction
Implementing ML algorithms to predict whether someone has a heart disease or not, based on given clinical parameters

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Data Preparation](#data-preparation)
- [EDA](#eda)
- [ML Models](#ml-models)
- [Results](#results)

## Project Overview
The main objective of the project was to analyze a dataset consisting of 13 clinical parameters about 303 patients and to develop an appropriate ML model for predicting heart disease based on the given patient data. The first part of the project was devoted to the analysis of available data. Data inspection, preprocessing and visualization were performed. Some interesting insights and patterns emerged from the dataset. The second part of the project referred to the appplication of machine learning techniques such as model training, hyperparameter tuning, model retraining, testing the behaviour of the model on unseen data and performance comparison for several classifiers.  
 
## Dataset
The dataset used is from UCI Machine Learning Repository and is  publicly available [here](https://archive.ics.uci.edu/dataset/45/heart+disease). The dataset consists of clinical measures and parameters for 303 patients. For each subject, 13 clinical features were observed or measured, including age, sex, cp, trestbps, chol, fbs, restecg, thalach, exang, oldpeak, slope, ca, thal. The data is labeled, so that the target field refers to the presence of heart disease in the patient. 

## Data Preparation
In the initial data preparation phase, the following tasks were performed:
1. data loading and inspection
2. checking for missing values
3. checking for categorical features.

## EDA
EDA was performed to explore the dataset and summarize its main characteristics. Performed EDA steps are:
-	univariate analysis – distribution for "continuous" features in both classes was visualized with KDE, whereas for discrete features bar plot was used to show heart disease frequency
-	bivariate analysis – pairwise feature relationships and correlation matrix were visualized in order to reveal highly correlated features
-	normalization – the range of features was varying a lot, so it was standardized with (0, 1) normalization.
  
A few observations obtained through EDA:
-	classes are nearly balanced (138 healthy patients, 165 heart disease)
-	chol and fbs features have the lowest correlation with target variable
- features that are highly dependant with target variable are cp, thalach, exang, oldpeak, slope, ca.

## ML Models
ML models implemented to predict the presence of heart disease based on normalized clinical parameters are: Logistic Regression, k-Nearest Neighbors, Random Forest, and AdaBoost Classifier. First, baseline classification scores were calculated. In order to improve models performance hyperparameter tuning was done using Randomized Search Cross Validation for a wide range of hyperparameters, and then exhaustive search was performed via Grid Search Cross Validation. The models were retrained with the optimal hyperparameteres and tested on unseen data. 

## Results
The classification report, ROC curve, and confusion matrix were used to assess models performance. The classifiers with the highest recall were chosen as the best classifiers. Recall provides a measure of how accurately the model can identify the relevant data (patients with heart disease). High recall might be crucial in medical problems (catching as many diseases as possible), so kNN and Random Forest Classifiers have proven to be the best predictors of heart disease.

![results_heart_disease](https://github.com/user-attachments/assets/753dba0b-cd9d-4a23-ae89-5eef4a16f86a)

