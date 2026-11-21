# **Predicting Biomedical Variables Without PCA**

## **Project Overview**
This project focuses on predicting key biomedical variables while preserving the interpretability of the original dataset features. We intentionally avoid **Principal Component Analysis (PCA)** to maintain direct links between predictions and clinically meaningful variables, which is essential in biomedical applications.

---

## **Target Variables**
The following key biomedical variables are predicted in this study:

1. **Age**: Patient's age.
2. **Charges**: Medical expenses associated with the patient.
3. **WBLC**: White Blood Cell Count.
4. **Creatinine**: Creatinine levels, an indicator of kidney function.

---

## **Why Not Use PCA?**
We avoid PCA for the following reasons:
1. **Interpretability**: PCA transforms features into principal components, losing direct interpretation of original variables. In biomedical applications, understanding feature importance is crucial.
2. **Potential Loss of Information**: PCA can discard components containing small yet relevant signals.
3. **Linear Assumptions**: PCA assumes linear relationships, which may fail to capture the complexity of biomedical data.
4. **Preserving Domain Knowledge**: The original features have clinical significance. Avoiding PCA allows the predictions to be linked directly to meaningful biomedical variables.

By opting for this approach, we ensure that the predictions are not only powerful but also interpretable, which is critical in real-world healthcare applications.

---

## **Regression Model Comparison**

This study compares the performance of multiple regression models, both linear and non-linear, to determine the most suitable model for predicting the target variables.

### **Implemented Models**
The models are categorized into two main groups: **Linear** and **Non-Linear** models.

#### **Linear Models**
Linear models assume a linear relationship between features and the target variable. These models are simple but effective when relationships are linear.

1. **Linear Regression**: Standard least-squares method.
2. **Quantile Regression**: Models different quantiles of the target variable.
3. **Polynomial Regression (Degree=2)**: Extends linear regression with polynomial features.
4. **Linear SVR**: Support Vector Regression with linear kernels.
5. **SGD Regression**: Linear regression based on stochastic gradient descent.
6. **Theil-Sen Regression**: Robust linear model using median estimators.
7. **RANSAC Regression**: Linear regression that handles outliers.
8. **Huber Regressor**: Robust linear model that reduces the influence of outliers.

#### **Non-Linear Models**
Non-linear models capture complex relationships in the data.

1. **SVR (Support Vector Regression)**: Uses kernels for non-linear relationships.
2. **NuSVR**: A variant of SVR with an additional parameter controlling support vectors.
3. **Decision Tree Regression**: Non-linear model based on hierarchical splits of the feature space.
4. **Nearest Neighbor Regression**: Uses the nearest neighbors' data for prediction.

---

## **Evaluation Metrics**
The models are evaluated using the following metrics:

- **Coefficient of Determination (R^2)**: Measures the proportion of variability in the target explained by the model.
- **Adjusted \(R^2\)**: Adjusts \(R^2\) for the number of predictors.
- **Mean Absolute Error (MAE)**: The average of the absolute differences between predicted and actual values.
- **Mean Squared Error (MSE)**: The average of the squared differences between predicted and actual values.
- **Mean Absolute Percentage Error (MAPE)**: Measures prediction accuracy as a percentage.
- **Root Mean Squared Error (RMSE)**: The square root of MSE, providing error in the same units as the target variable.

---

## **Preprocessing Steps**

To ensure effective model training, the following preprocessing steps were performed:

1. **Encoding Categorical Variables**: 
   - Categorical variables are converted into numerical values using **one-hot encoding** (`pd.get_dummies`).
   
2. **Data Normalization**:
   - Features are scaled using **StandardScaler** to ensure compatibility with models like KNN and SVR.

3. **Data Splitting**:
   - The dataset is divided into **training**, **validation**, and **test** sets using a **70/10/20 split** strategy. We apply a **stratified k-fold approach** with 10 folds, splitting data into 5 external and 2 internal folds for robust evaluation.

---

## **Overfitting Evaluation**
To assess overfitting in models, we analyze the relationship between training and validation errors. By examining the evolution of complexity and adjusted \(R^2\), we can identify when a model begins to overfit and loses its ability to generalize.

---

## **Feature Reduction and Information Loss**
During feature reduction, we observe a **constant information loss of 3.125%** for each feature removed, features has ben normalized previously. This metric serves as a guideline to balance model complexity and performance.

---

## **Study Approach**
![Regression Analysis](IMAGES/Regression%20Analysis%20copy.png)

To analyze the models, we focus on those that, by default, do not suffer from significant underfitting or overfitting issues. However, we also investigate underfitting and overfitting in two models to gain deeper insights.

---

## **Analysis of Complexity in Decision Tree Regression Models**

### **Project Overview**
In this part of the project, we focus on the **Decision Tree Regression Model** to analyze its complexity and overfitting behavior. Decision Trees tend to overfit, so this section explores how hyperparameters affect model performance.

---

### **Study Objective**
The primary goal is to understand the impact of **overfitting** and **underfitting** in Decision Tree models, specifically how hyperparameters influence these behaviors. We aim to find a balance between overfitting and underfitting for practical implementation.

---

### **Key Hyperparameters**
1. **min_samples_leaf**: Minimum samples required to be in a leaf node.
2. **max_depth**: Maximum depth of the tree.

These hyperparameters determine the tree's structure and influence its complexity.

---

### **Analysis of Overfitting and Underfitting**
We use a **three-dimensional space** (R³) to analyze the relationship between:

- **min_samples_leaf**
- **max_depth**
- **Error or Explained Variability** (measured by training and validation error).

The complexity of these interactions requires advanced mathematical and statistical techniques to assess:

1. **Gradients**: Used to observe performance trends with respect to hyperparameters.
2. **Euclidean Norm**: Measures the distance between training and validation errors.
3. **Pearson Correlation**: Measures the linear relationship between training and validation errors.

---

### **Conclusions**
The analysis highlights how **model complexity** affects overfitting. By adjusting **min_samples_leaf** and **max_depth**, we can control the model’s complexity and improve its generalization ability.
