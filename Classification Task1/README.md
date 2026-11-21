# Data Analysis and Model Evaluation for the SUPPORT2 Dataset

## Overview
This repository contains the analysis and classification tasks performed on the SUPPORT2 dataset from the UCI Machine Learning Repository. In this project, we aimed to predict various outcomes using machine learning models and evaluate their performance using several metrics.

The target classifications and the steps taken to prepare the data for modeling are outlined below.

## Data Preparation for Classification Tasks

We prepared the data by defining specific target classifications for the predictions. The process involved removing certain variables from the dataset to avoid redundancy and bias, ensuring that the models make accurate predictions based on the features available.

### 1. **Prediction of Death**
   - **Target Variable**: `Death`
   - **Removed Variable**: `hospdead`
   - **Reason**: The `hospdead` variable directly indicates whether the patient died in the hospital, which is closely related to the mortality outcome. Including this would introduce bias into the model as it essentially provides the answer we are trying to predict.

### 2. **Prediction of TypeDzClass (Disease Classification)**
   - **Target Variable**: `TypeDzClass`
   - **Removed Variables**: `ca`, `dzgroup`
   - **Reason**: These variables are strongly correlated with disease classification, and including them would add redundancy or risk data leakage, which would bias the model’s ability to predict the disease class.

### 3. **Prediction of HospDead (Hospital Mortality)**
   - **Target Variable**: `HospDead`
   - **Removed Variable**: `death`
   - **Reason**: Since both `death` and `HospDead` are related to mortality, keeping `death` would give away information the model is supposed to predict, leading to potential bias.

### 4. **Prediction of SFDM2 (Functional Disability)**
   - **Target Variable**: `SFDM2`
   - **Reason**: For this prediction task, all variables in the dataset were retained to provide the model with the most complete information possible. This would enhance the model's ability to predict functional disability accurately.

By carefully tailoring the data preparation for each target variable, we minimize redundancy and potential bias, laying a solid foundation for model training.

## Model Evaluation and Classification Process

For each task, we used multiple classification algorithms and evaluated them using various hyperparameter configurations. The goal was to find the best model for each problem by assessing its performance with key metrics. The following steps were followed:

### 1. **Split Data**
   The data was split into training, validation, and test sets following a 70/10/20 ratio. This split was stratified to preserve the original class distribution in each subset.

### 2. **Classification Algorithms**
   We applied various classification algorithms including, but not limited to:
   - Logistic Regression
   - Decision Trees
   - Random Forests
   - Support Vector Machines (SVM)

### 3. **Hyperparameter Tuning**
   For each algorithm, multiple hyperparameter configurations were tested to determine the best combination for each task. Grid search and Random search techniques were used for this purpose.

### 4. **Model Evaluation Metrics**
   The following metrics were used to evaluate and compare the models:
   - **Confusion Matrix**: Shows the true positives, false positives, true negatives, and false negatives, providing a comprehensive view of model performance.
   - **Accuracy**: The percentage of correct predictions.
   - **Precision**: Measures the proportion of true positive predictions out of all positive predictions.
   - **Recall**: Measures the proportion of actual positive cases correctly identified by the model.
   - **F1 Score**: The harmonic mean of precision and recall, used to balance the trade-off between them.
   - **AUC-ROC**: The Area Under the ROC Curve, which measures the model's ability to distinguish between classes.

### 5. **Selection of the Best Model**
   After evaluating all the models with these metrics, the best performing model was selected for each classification task based on its overall performance, especially in terms of F1 Score and AUC-ROC.

![Data Cleaning Process](IMAGES/DATA%20CLEANED%20(2).png)

## Conclusion

After evaluating different classification algorithms and configurations, we selected the best models for each target variable based on performance metrics. The data preparation steps, particularly the exclusion of certain variables to avoid bias and redundancy, played a crucial role in ensuring that the models performed well. The best models were chosen based on their ability to generalize to unseen data, with emphasis on precision, recall, F1 score, and AUC-ROC.

By following this comprehensive process, we achieved robust and accurate predictive models that can be used for various applications related to patient health outcomes in the SUPPORT2 dataset.


