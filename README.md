# 💳 AI-Powered Credit Risk Decision System

An end-to-end credit risk decision system that combines machine learning with financial modeling to simulate real-world lending decisions.

![images](https://github.com/NurulIlahiHusnah/-Predict-Credit-Risk-Leanding-Company/assets/125198828/75a79d18-97b1-4a6d-8efa-0a242eaf02c7)

---

## 🎯 Overview

This project goes beyond traditional credit risk modeling by integrating:

- **Probability of Default (PD)** prediction using machine learning  
- **Financial metrics** such as Loss Given Default (LGD) and Expected Loss (EL)  
- A **decision engine** that evaluates both risk and profitability  

👉 The goal is not just to predict risk — but to support **better business decisions**.

---

## 🧠 Key Insight

> Accurate risk prediction alone is not enough.

This project demonstrates that:

- High **LGD (loss rate)** can make even low-risk borrowers unprofitable  
- Lending decisions must consider both **risk (PD)** and **return (profitability)**  
- Business assumptions significantly impact outcomes  

---

## ⚙️ How It Works

### 1. Machine Learning Model
- Logistic Regression with preprocessing pipeline  
- Probability calibration (Isotonic Regression)  
- Output: Probability of Default (PD)

### 2. Financial Modeling
- **EAD (Exposure at Default)** → loan amount  
- **LGD (Loss Given Default)** → adjustable assumption  
- **Expected Loss (EL)**:
  
> EL = PD × LGD × EAD
> - **Expected Profit**: Profit = (1 - PD) × Interest Income - Expected Loss


### 3. Decision Engine

Hybrid approach:

- Approve if **Expected Profit > 0**
- Reject if **high risk or not profitable**

---

## 🖥️ Interactive Dashboard

Built with **Streamlit**, the app allows users to:

- Input borrower profile  
- Adjust LGD (business assumption)  
- View:
- PD (risk)
- Expected Loss
- Expected Profit
- Approval decision  

---

## 📊 Example Output

| Metric | Value |
|------|------|
| PD | 0.21 |
| LGD | 0.70 |
| Expected Loss | 1,500 |
| Expected Profit | 2,300 |
| Decision | APPROVE |

---

## 🧩 Tech Stack

- Python  
- Pandas  
- Scikit-learn  
- Streamlit  

---

## 🚀 Why This Project Matters

Most models stop at prediction.

This project bridges the gap between: **Machine Learning → Business Decision**


It shows how data can be used not only to predict outcomes, but to **drive real, actionable decisions**.

---

## 📌 Future Improvements

- Risk-based pricing strategy  
- Portfolio optimization  
- Real-world deployment (API / cloud)  
- Model comparison (XGBoost, etc.)

---

## Model Validation
At this stage, I evaluated the base model using Logistik Regresion algorithm:

### 1. Calibrartion by Isotonik with Logistik Regresion 
     Confusion Matrik
  
      Test AUC: 0.7049261144988581  
    
    [[36696 252]
     [8356  306]]

               precision    recall  f1-score   support

            0       0.81      0.99      0.90     36948
            1       0.55      0.04      0.07     8662

    accuracy                            0.81     45610
    macro avg       0.68      0.51      0.48     45610
    weighted avg    0.76      0.81      0.74     45610
    
    [0.24650531 0.14909541 0.31878195 ... 0.08514313 0.19254669 0.13777337]

## 📬 Contact

If you're interested in building similar data-driven decision systems, feel free to connect.




