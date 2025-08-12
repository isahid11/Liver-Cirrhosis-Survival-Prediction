# Liver-Cirrhosis-Survival-Prediction

# 🩺 Liver Cirrhosis Survival Prediction – SIG720 Task 4C

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)
![License](https://img.shields.io/badge/License-Academic-green.svg)

> Machine Learning project for predicting the survival status of patients with **Primary Biliary Cirrhosis** using clinical data.

---

## 📄 Project Overview
This project is part of **Deakin University’s SIG720** course.  
The aim is to predict the **survival status** of liver cirrhosis patients using **17 clinical features** from the **Mayo Clinic PBC Study** (1974–1984).  

The target variable `Status`:
- **0** – Death (D)  
- **1** – Censored (C)  
- **2** – Censored due to Liver Transplantation (CL)  

We built, evaluated, and compared three supervised machine learning models, addressed class imbalance, and analyzed feature importance to support clinical interpretation.

---

## 📊 Dataset
- **Source:** [Cirrhosis Patient Survival Prediction Dataset – UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/878/cirrhosis+patient+survival+prediction+dataset-1)  
- **Records:** 418 patients  
- **Features:** 17 (mix of categorical and continuous)  
- **Goal:** Predict survival status from patient clinical measurements.

---

## 🔄 Workflow

### 1️⃣ Data Preprocessing
- **Missing values handling**:  
  - Continuous → Mean imputation  
  - Categorical → Mode imputation  
- **Encoding**: Label Encoding for categorical features  
- **Train-Test Split**: 80:20 with stratified sampling

### 2️⃣ Model Development
- Models tested:
  - Logistic Regression
  - Random Forest
  - K-Nearest Neighbors (KNN)
- Metrics: **Accuracy** & **Macro F1 Score**
- Validation: 5-Fold Stratified Cross-Validation

### 3️⃣ Class Imbalance Handling
- Applied **SMOTE (Synthetic Minority Over-sampling Technique)**

### 4️⃣ Feature Importance Analysis
- Random Forest Feature Importance
- Decision Tree Feature Importance

### 5️⃣ Model Selection
- **Logistic Regression** chosen for balanced performance and interpretability

---

## 📈 Results Summary

| Model               | Accuracy (Before SMOTE) | Macro F1 (Before SMOTE) | Accuracy (After SMOTE) | Macro F1 (After SMOTE) |
|---------------------|-------------------------|--------------------------|------------------------|------------------------|
| Logistic Regression | 0.7874                  | 0.5897                   | 0.7262                 | 0.5621                 |
| Random Forest       | 0.8083                  | 0.5761                   | 0.7738                 | 0.5381                 |
| KNN                 | 0.6646                  | 0.4442                   | 0.5238                 | 0.4434                 |

**Final Model Performance – Logistic Regression (Test Set)**  
- **Accuracy:** 0.7024  
- **Macro F1 Score:** 0.5449  

---

## 🩻 Key Clinical Predictors
From feature importance analysis, the top predictors were:
- **N_Days**
- **Bilirubin**
- **Prothrombin**
- **Age**
- **Copper**

These features ranked highly in both Random Forest and Decision Tree analyses, confirming their clinical relevance.

---

📌 Future Improvements
* Test advanced models (XGBoost, LightGBM)

* Incorporate additional patient data from other studies

* Deploy as an interactive clinical decision support tool

📜 License
This project is for academic purposes under Deakin University SIG720 coursework.
