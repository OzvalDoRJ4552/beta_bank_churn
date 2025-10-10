# Beta Bank Churn Prediction
End-to-end churn prediction project for Beta Bank. Built and tuned machine learning models to identify customers likely to leave, using Python, scikit-learn, and imbalanced-learn. Emphasis on data cleaning, feature preprocessing, imbalance correction, and evaluation using F1 and AUC-ROC metrics.




# 🏦 Beta Bank Customer Churn Prediction

## 📘 Project Overview
Beta Bank noticed that some of its customers are leaving, and attracting new clients costs more than retaining existing ones.  
The goal of this project is to **predict customer churn**—whether a client is likely to leave soon—so the bank can take proactive retention steps.

This project uses **machine learning classification models** to identify at-risk customers and evaluate their performance using **F1 score** and **ROC-AUC** metrics.  
The target metric for project approval was **F1 ≥ 0.59**.

---

## 🧩 Dataset Description
The dataset (`Churn.csv`) contains 10,000 customer records with the following features:

| Feature | Description |
|----------|--------------|
| `CreditScore` | Customer credit score |
| `Geography` | Country of residence |
| `Gender` | Male or Female |
| `Age` | Customer age |
| `Tenure` | Years with the bank |
| `Balance` | Account balance |
| `NumOfProducts` | Number of bank products |
| `HasCrCard` | Credit card ownership (1 = yes) |
| `IsActiveMember` | Whether the customer is active (1 = yes) |
| `EstimatedSalary` | Approximate income |
| `Exited` | **Target:** 1 = customer left, 0 = stayed |

---

## ⚙️ Project Steps
1. **Data preparation**
   - Removed ID columns (`RowNumber`, `CustomerId`, `Surname`)
   - Filled missing `Tenure` values with the median
   - One-hot encoded categorical features

2. **Modeling**
   - **Baseline Logistic Regression:** F1 = 0.32, AUC = 0.76  
   - **Balanced Logistic Regression:** F1 = 0.48, AUC = 0.76  
   - **Random Forest (Balanced):** F1 = 0.55, AUC = 0.86  
   - **Threshold tuning (RF, thr=0.30):** F1 = 0.63 (validation), **0.61 (test)**

3. **Evaluation**
   - Final model: **Random Forest Classifier** with `class_weight='balanced'`
   - Final test metrics:  
     - **F1 = 0.605**  
     - **ROC-AUC = 0.857**

---

## 🧠 Key Insights
- Class imbalance (80/20) made logistic regression underperform on churners.
- Balancing class weights and tuning thresholds improved recall dramatically.
- The Random Forest captured nonlinear relationships better, outperforming all other models.
- The model can identify most churners while maintaining good overall accuracy.

---

## 🧾 Technologies Used
- Python 3.10  
- pandas, NumPy, matplotlib  
- scikit-learn  

---

## 🏁 Final Outcome
✅ **Goal achieved:** F1 > 0.59  
✅ **Final Model:** Random Forest (Balanced + Threshold Tuned)  
✅ **Performance:** F1 = 0.605, AUC = 0.857  

This model can help **Beta Bank** focus retention strategies on high-risk customers, reducing churn and improving profitability.

---
## ✍️ Author
**Osvaldo Ramirez**  
Data Science & Machine Learning Bootcamp Student  
📧 Contact: [osvaldorj135@gmail.com]