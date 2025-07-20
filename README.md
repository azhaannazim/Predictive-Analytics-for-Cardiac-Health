# Predictive Analytics for Cardiac Health

## Project Overview

This project develops a machine learning model to predict the presence of heart disease based on a patient's medical parameters. The model is trained on the well-known UCI Cleveland Heart Disease dataset and leverages an ensemble approach to achieve high accuracy and reliability.

## Table of Contents

1.  [Problem Definition](#problem-definition)
2.  [Data](#data)
3.  [Methodology](#methodology)
4.  [Results & Evaluation](#results--evaluation)
5.  [Visualizations](#visualizations)
6.  [How to Use](#how-to-use)
7.  [Future Enhancements](#future-enhancements)

## Problem Definition

Given the clinical parameters of a patient, can we develop a machine learning model to accurately classify whether that person has heart disease?

## Data

The data is sourced from the [UCI Cleveland Heart Disease dataset](https://archive.ics.uci.edu/dataset/45/heart+disease). While the full database contains 76 attributes, this project uses the commonly cited subset of 14 features for modeling.

### Key Features

-   `age`: Age of the patient
-   `sex`: Gender of the patient (1 = male; 0 = female)
-   `cp`: Chest pain type
-   `trestbps`: Resting blood pressure
-   `chol`: Serum cholesterol
-   `fbs`: Fasting blood sugar > 120 mg/dl
-   `restecg`: Resting electrocardiographic results
-   `thalach`: Maximum heart rate achieved
-   `exang`: Exercise-induced angina
-   `oldpeak`: ST depression induced by exercise relative to rest
-   `slope`: Slope of the peak exercise ST segment
-   `ca`: Number of major vessels colored by fluoroscopy
-   `thal`: Thalassemia type
-   `target`: Diagnosis of heart disease (1 = yes, 0 = no)

## Methodology

The project followed a structured machine learning workflow:

1.  **Exploratory Data Analysis (EDA)**: The dataset was analyzed to understand feature distributions, identify correlations, and visualize relationships between variables and the target. A correlation matrix was used to assess multicollinearity and feature relevance.

2.  **Model Selection**: Three baseline classification models were trained and evaluated:
    -   Logistic Regression
    -   K-Nearest Neighbors (KNN)
    -   Random Forest Classifier

3.  **Hyperparameter Tuning**: `RandomizedSearchCV` was used to efficiently search for the optimal hyperparameters for the Logistic Regression and Random Forest models, which were the top-performing baseline models.

4.  **Ensemble Modeling**: To enhance predictive performance, a **`VotingClassifier`** was implemented. This ensemble model combines the strengths of the tuned Logistic Regression and Random Forest models, using a 'soft' voting strategy to average their predicted probabilities, leading to a more robust and accurate final model.

## Results & Evaluation

The final ensemble model (`VotingClassifier`) demonstrated a significant improvement over the baseline models, achieving a final test accuracy of **87%**.

The detailed performance metrics are shown in the classification report below:

| Metric         | Class 0 (No Disease) | Class 1 (Has Disease) | Weighted Avg |
| :------------- | :------------------- | :-------------------- | :----------- |
| **Precision** | 0.90                 | 0.84                  | 0.87         |
| **Recall** | 0.84                 | 0.90                  | 0.87         |
| **F1-Score** | 0.87                 | 0.87                  | 0.87         |
| **Support** | 32                   | 29                    | 61           |

A **Recall of 0.90** for predicting the presence of heart disease (Class 1) is a key result, as it indicates the model is highly effective at correctly identifying patients who have the condition, minimizing the risk of false negatives.

## Visualizations

Key visualizations from the analysis include:

-   **Correlation Matrix Heatmap**: To show the relationships between all features in the dataset.
-   **ROC Curve**: Demonstrating the model's performance across different classification thresholds. The final model achieved a high Area Under the Curve (AUC).
-   **Feature Importance Plot**: Highlighting the most influential medical parameters for predicting heart disease, derived from the Logistic Regression model's coefficients.
-   **Model Performance Comparison**: A bar chart comparing the accuracy of the baseline models.

## How to Use

To replicate this analysis, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/azhaannazim/Predictive-Analytics-for-Cardiac-Health.git](https://github.com/azhaannazim/Predictive-Analytics-for-Cardiac-Health.git)
    ```
2.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
3.  **Run the Jupyter Notebook:**
    Open and run the `predictive-analytics-for-cardiac-health.ipynb` notebook in a Jupyter environment.

## Future Enhancements

-   **Advanced Models**: Explore more complex models like XGBoost, LightGBM, or CatBoost, which often yield state-of-the-art results on tabular data.
-   **Feature Scaling**: Implement feature scaling (e.g., `StandardScaler`) within a `Pipeline` to see if it further improves model performance, especially for Logistic Regression.
-   **Deployment**: Deploy the final trained model as a simple web application using Flask or Streamlit to allow for real-time predictions.
