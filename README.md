# Predictive Analytics for Cardiac Health

## Project Overview

This project aims to predict whether a person has heart disease based on various medical parameters. The dataset used for this project is sourced from the UCI Cleveland repository.

## Table of Contents

1. Problem Definition
2. Data
3. Evaluation
4. Features
5. Modeling
6. Experimentation
7. Results
8. Visualisations

## Problem Definition

The objective is to develop a machine learning model that can predict the presence of heart disease in a patient based on medical parameters.

## Data

The data is sourced from the [UCI Cleveland Heart Disease dataset](https://archive.ics.uci.edu/dataset/45/heart+disease). It includes 76 attributes, but the commonly used subset includes 14 attributes.

## Evaluation

The primary metric for evaluating the model is accuracy, but other metrics like precision, recall, F1-score, and ROC-AUC are also considered to ensure a comprehensive evaluation. Feature Imporatance was also
evaluated to determine the importance of each feature on the accuracy of the model.

## Features

The dataset contains the following key features:

- `age`: Age of the patient
- `sex`: Gender of the patient
- `cp`: Chest pain type
- `trestbps`: Resting blood pressure
- `chol`: Serum cholesterol
- `fbs`: Fasting blood sugar
- `restecg`: Resting electrocardiographic results
- `thalach`: Maximum heart rate achieved
- `exang`: Exercise-induced angina
- `oldpeak`: ST depression induced by exercise relative to rest
- `slope`: Slope of the peak exercise ST segment
- `ca`: Number of major vessels colored by fluoroscopy
- `thal`: Thalassemia
- `target`: Diagnosis of heart disease (0 = no, 1 = yes)

### Exploratory Data Analysis (EDA)

EDA includes descriptive statistics, visualizations like histograms and box plots, and correlation analysis to identify relationships between features and the target variable. 
**Correlation Coefficients of the features of the dataset**:
<img width="816" height="623" alt="Screenshot 2025-07-20 at 12 08 11 PM" src="https://github.com/user-attachments/assets/76f418db-e33d-4e0b-b8c8-9138872b7cc7" />

## Modeling

The following models were considered:

- Logistic Regression
- Random Forest
- k-Nearest Neighbors

Extensive model hyperparameter tuning was conducted using grid search and cross-validation to find the best hyperparameters for the chosen model. Ensembling techniques were also explored.
The final model was chosen based on performance metrics and hyperparameter tuning which is Logistic Regression.


## Experimentation

It involves greater research and understanding of the dataset in order to achieve a success rate of say 95%. Extensive experimentation is done with different parameters and feautures based on research in order
to gain such levels of accuracy. As this is a begineers project, this part was skipped.

## Results

The final model achieved an accuracy of 82.49%. Below are some key performance metrics:

- **Accuracy**: 82.49%
- **Precision**: 81.22%
- **Recall**: 89.09%
- **F1-score**: 84.81%
- **ROC-AUC**: 92%


### Visualizations

- **ROC Curve**:
-  <img width="601" height="434" alt="Screenshot 2025-07-20 at 12 02 44 PM" src="https://github.com/user-attachments/assets/f4493b25-4ee4-43fc-b4e0-ea5b6328ae17" />
- **Feature Importance**:
- <img width="601" height="534" alt="Screenshot 2025-07-20 at 12 04 54 PM" src="https://github.com/user-attachments/assets/0061ff0f-92dd-444a-8eef-55ccbcf16a3c" />
- **Scores**:
- <img width="605" height="565" alt="Screenshot 2025-07-20 at 12 05 40 PM" src="https://github.com/user-attachments/assets/4c3b59b4-d8d9-47dc-b75e-6f2e5092642a" />
