# 🩺 Diabetes Prediction using Logistic Regression

This project builds an interpretable **Logistic Regression** model to predict whether a person has diabetes, using the **Pima Indians Diabetes Dataset**.  
The work includes complete EDA (univariate, bivariate, correlation), preprocessing, class balancing, logistic model development, performance evaluation, and medical insight interpretation.

---

## 📌 Project Objective
The goal is to develop a predictive model that determines the likelihood of diabetes based on:

- Glucose levels  
- BMI  
- Blood pressure  
- Age  
- Insulin & skin thickness  
- Genetic factors (Diabetes Pedigree Function)  
- Pregnancy count

Logistic Regression is selected due to its interpretability and suitability for binary medical classification.

---

## 📁 Dataset Details

- **Source:** Pima Indians Diabetes Dataset (UCI / Kaggle)  
- **Samples:** 768  
- **Features:** 8 medical predictors  
- **Target:** `Outcome` (0 = Non-diabetic, 1 = Diabetic)  
- **Type:** Numerical, structured, small medical dataset  

### Features:
- Pregnancies  
- Glucose  
- BloodPressure  
- SkinThickness  
- Insulin  
- BMI  
- DiabetesPedigreeFunction  
- Age  

### Preprocessing Applied:
- StandardScaler for normalization  
- Stratified train-test split (80/20)  
- Replacing 0’s in medical fields where needed (missing values)  

---

## 🔍 Exploratory Data Analysis (Summary)

### **1. Univariate Findings**
- **Glucose** has the strongest separation between diabetic and non-diabetic cases  
- **BMI**, **Age**, **Pregnancies**, and **DPF** show increasing risk patterns  
- **SkinThickness** and **Insulin** have many zero entries (missing data indicators)  

### **2. Bivariate Insights**
- Diabetic distributions shift toward higher glucose, BMI, DPF, and age  
- Overlap exists in variables like blood pressure  
- Missing values affect insulin and skin thickness relationships  

### **3. Correlation Observations**
- No major multicollinearity → ideal for logistic regression  
- Moderate correlations:
  - Glucose ↔ Diabetes Outcome  
  - Age ↔ Pregnancies  
  - Insulin ↔ SkinThickness  

---

## 🧠 Model Development

- **Algorithm:** Logistic Regression  
- **Solver:** liblinear  
- **Class Weight:** balanced (critical due to class imbalance)  
- **Metrics Evaluated:**  
  - Accuracy  
  - Precision & Recall  
  - F1-score  
  - ROC-AUC  
  - PR-AUC  
  - Confusion Matrix  
  - Learning Curve  

---

## 🎯 Model Performance

| Metric | Score |
|--------|--------|
| Accuracy | 0.75 |
| Precision (Non-diabetic) | 0.84 |
| Recall (Non-diabetic) | 0.81 |
| Precision (Diabetic) | 0.58 |
| Recall (Diabetic) | 0.63 |
| ROC-AUC | 0.82 |
| PR-AUC | 0.69 |

### Interpretation:
- Model performs strongly for medical baseline screening  
- Recall for diabetic class is moderate but improved with class balancing  
- ROC-AUC of 0.82 indicates reliable discriminative ability  

---

## 🧪 Learning Curve Behavior
- Training accuracy starts high and decreases slightly  
- Validation accuracy starts lower and improves gradually  
- Curves do not fully converge → dataset size is limiting  
- Additional data or regularization tuning would improve generalization  

---

## ⭐ Feature Importance (via Random Forest)

| Feature | Importance | Interpretation |
|---------|------------|----------------|
| **Glucose** | ★★★★★ | Strongest predictor |
| **BMI** | ★★★★☆ | Obesity contribution |
| **DPF** | ★★★☆☆ | Genetic risk |
| **Age** | ★★☆☆☆ | Higher age → higher risk |
| Insulin | ★★☆☆☆ | Moderate impact (missing values) |
| Pregnancies | ★☆☆☆☆ | Gestational diabetes link |
| BP / SkinThickness | ★☆☆☆☆ | Least influential |

---

## 💡 Key Insights
- Glucose, BMI, and hereditary factors are dominant diabetes indicators  
- Logistic Regression provides medically interpretable patterns  
- Class imbalance handling significantly improves recall  
- Nonlinear models (Random Forest, XGBoost) could push performance higher  
- Many medical fields include missing values encoded as 0 → preprocessing is essential  

---

## 📦 Results Summary

| Item | Value |
|------|--------|
| Model | Logistic Regression |
| Accuracy | 0.75 |
| ROC-AUC | 0.82 |
| Best Features | Glucose, BMI, DPF |
| Class Balance Method | Weighted LR |
| Dataset Size | 768 samples |

---

## 🧱 Tech Stack
- Python  
- NumPy, Pandas  
- Matplotlib, Seaborn  
- Scikit-learn  
- Statsmodels  
- Jupyter / Colab  

---
