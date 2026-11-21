# Project: SUPPORT2 Dataset Analysis

This repository contains the work carried out within the framework of the **Machine Learning** subject, taught by Professor **Rubén Sánchez Corcuera**. The author of the project is **Francesc Serra**.

---

## Project Description

The main objective of this project is to explore and model the **SUPPORT2** dataset, a dataset used to develop and validate Machine Learning models. This project covers from the initial exploration of the data to the development of advanced models for classification, regression and clustering tasks.

---

## SUPPORT2 Dataset Structure

### Metadata

- **Dataset Purpose:**

- Develop and validate a prognostic model to estimate 180-day survival in hospitalized adults with serious illnesses.
- Compare the model's predictions with previous estimates and medical prognoses.

- **Instances Represented:** Records of critically ill patients admitted to US hospitals.

- **Data Split Recommendations:** A standard split (train-test) or a three-part split (train-validation-test) is suggested.

- **Sensitive Information:** Includes data such as race, gender, income, and education level.

- **Data Sources:** Medical records, personal interviews, and the National Death Index (NDI).

- **Recommended Preprocessing:**

- For missing values, it is suggested to impute data with the following default values:
- **Alb (Albumin):** 3.5
- **Pafi (PaO2/FiO2):** 333.3
- **Bili (Bilirubin):** 1.01
- **Crea (Creatinine):** 1.01
- **BUN (Blood urea nitrogen):** 6.51
- **WBLC (White blood cell count):** 9
- **Urine (Urine output):** 2502

### Timeline

- **Phase I (1989-1991):** Prospective observational study with 4,301 patients.
- **Phase II (1992-1994):** Controlled clinical trial with 4,804 patients, followed by matching to NDI through 1997.

### Inclusion Criteria

Patients from five US medical centers with one of the following conditions:

- Acute respiratory failure, chronic obstructive pulmonary disease, congestive heart failure, liver disease, coma, colon cancer, lung cancer, multiorgan failure with malignancy, or multiorgan failure with sepsis.

---

## Project Objectives

1. **Dataset Exploration:** Understand the characteristics and limitations of the data.
2. **Preprocessing:** Handle missing values ​​and perform necessary transformations.
3. **Modeling:** Train and evaluate prognostic models.
4. **Results Analysis:** Compare the performance of different models and approaches.

---

## Repository Structure

### **1. Data Visualization and Cleaning**

- Exploratory visualization and cleaning processes.
- Relevant files:
- `Data_cleaning.ipynb`
- `Data_Visualization.ipynb`

### **2. Classification Task**

Includes analysis and modeling for different categories:

- Subfolders:
- **2.1. Model Analysis For Death:** Prediction of mortality.
- **2.2. Model Analysis For HospDeath:** Prediction of hospital death.
- **2.3. Model Analysis For TypeDzClass:** Classification of disease types.
- **2.4. Model Analysis For SFDM2:** Analysis related to follow-up interviews.

### **3. Regression Task**

Predictions of numerical variables.

- Subfolders:
- **3.1. Prediction\_Age:** Prediction of age.
- **3.2. Prediction\_WBLC:** Prediction of white blood cell count.
- **3.3. Prediction\_Charges:** Prediction of medical charges.
- **3.4. Prediction\_Creatine:** Prediction of creatinine.

### **4. Clustering Task**

- Categorical and numerical clustering analysis.
- Relevant files:
- `Categorical_DF_Clustering_analysis.ipynb`
- `Numerical_DF_Clustering_Analysis.ipynb`
- Visualizations in the `IMAGES` folder.

### **5. Apriori Task**

- Implementation of the Apriori algorithm for association rule analysis.
- Relevant files:
- `Apriori.ipynb`
- `DataModels_rules.csv`

### **6. General Files**

- **Data:**
- `DataCleaned.csv`: Cleaned data.
- `DataModels_categorical_features.csv`: Categorical features.
- `DataModels_numerical_features.csv`: Numerical features.

---

## Project Execution

### **1. Prerequisites**

To run the project, the necessary libraries are downloaded at the start of each notebook (`ipynb`).

### **2. General Instructions**

- Each most of the tasks includes a specific `README.md` file with additional information.
- Scripts and notebooks are organized by tasks and clearly labeled for ease of use.

