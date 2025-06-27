# Fraud Detection Model

This project aims to build a fraud detection system using supervised machine learning, Random Forest. The dataset used consists of financial transaction data containing nominal information, transaction type, and whether the transaction is fraud or not. Dataset used in this model is taken from https://www.kaggle.com/datasets/jainilcoder/online-payment-fraud-detection

---

## Objectives

- Detect fraud transactions automatically
- Overcome data imbalance
- Choose the optimal threshold so that the model is balanced between precision and recall
- Evaluate model performance using relevant metrics for fraud detection

---

## Dataset

- Important features:
- `amount`, `oldbalanceOrg`, `newbalanceOrg`
- `oldbalanceDest`, `newbalanceDest`, `step`
- `type_encoded` (encoding result of `type` feature)
- Target:
- `isFraud` (1 = fraud, 0 = non-fraud)

---

## EDA (Exploratory Data Analysis)

- Handle missing values ​​and categorical encoding
- Correlation analysis with **Pearson** (linear) and **Spearman** (monotonic)
- Feature distribution is visualized with boxplot and correlation heatmap
- Insights from dataset

---

## Handling Imbalanced Data

- Fraud vs non-fraud distribution is very unbalanced
- **SMOTE (Synthetic Minority Oversampling Technique)** technique is used to balance the dataset before training

---

## Model

- Main algorithm: **Random Forest Classifier**
- Trained with SMOTE data
- Default hyperparameters, optimized prediction threshold

---

## Threshold Tuning

- Using Precision-Recall curve against threshold
- Looking for **best threshold** that maximizes F1-score
- Results: the best threshold around 0.95 provides a balance between precision and recall

---

## Evaluation

- **Accuracy:** ~99.97%
- **Precision:** 0.94
- **Recall:** 0.81
- **F1-score:** 0.87
- **Matthews Correlation Coefficient (MCC):** 0.87
- Confusion matrix and classification report provided

---

## 🔍 Model Interpretability

- **Feature Importance** from Random Forest

---

## 🧠 Insights from Correlation

- Pearson: linear correlation between `amount`, `step`, and `isFraud` is weak to moderate
- Spearman: shows non-linear relationships, especially with `oldbalanceOrg`, `newbalanceOrg`
- This indicates that **non-linear relationships are important for fraud detection**

---

## 🛠️ Tools & Libraries

- Python (Pandas, NumPy, Scikit-learn, Imbalanced-learn, SHAP, Matplotlib, Seaborn)
- Jupyter Notebook
