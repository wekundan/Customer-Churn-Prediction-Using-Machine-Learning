# 📊 Customer Churn Prediction Using Machine Learning

A telecom company wants to identify customers who are likely to churn (i.e., stop using their services). This project uses machine learning models to accurately predict churn, with a focus on **high recall** to minimize customer loss.

---

## 📁 Dataset Overview

- **Source:** Telco customer data
- **Total Records:** 7032 customers
- **Target:** `Churn` (Yes/No → converted to 1/0)
- **Features:** Customer demographics, account info, service usage

---

## 🎯 Objective

To build a churn prediction model that:
- Predicts whether a customer will churn
- Optimizes **recall** to reduce missed churners
- Compares performance of multiple ML models

---

## 🧹 Data Preprocessing

- Removed non-numeric characters from `TotalCharges`
- Converted `TotalCharges` to float
- Handled categorical variables with **One-Hot Encoding**
- Normalized numerical columns (`StandardScaler`)
- Removed `customerID` (non-informative)
- Used `train_test_split` with `stratify=y` (80/20)

---

## 🧠 Models Trained

| Model                     | Accuracy | Recall (Churn) | Precision (Churn) | F1-Score (Churn) |
|---------------------------|----------|----------------|--------------------|------------------|
| Logistic Regression       | 73%      | **0.80** ✅     | 0.49               | **0.61** ✅      |
| Random Forest (tuned)     | 76%      | 0.76           | **0.54**           | 0.63             |
| XGBoost                   | 73%      | 0.78           | 0.50               | 0.61             |

> **Logistic Regression with class_weight='balanced'** was chosen as the final model due to the best trade-off between simplicity and high recall.

---

## ✅ Final Model: Logistic Regression

- `class_weight='balanced'` to address class imbalance
- High recall ensures **fewer missed churners**
- Transparent and explainable

---

## 📊 Evaluation Metrics

- Confusion Matrix
- Precision, Recall, F1-Score
- ROC-AUC Score
- Feature Importance via model coefficients

---

## 🔍 Feature Importance (Top Drivers)

| Feature              | Impact     |
|----------------------|------------|
| Contract (Month-to-Month) | High Risk |
| Tenure               | Negative   |
| Paperless Billing    | Positive   |
| MonthlyCharges       | Positive   |

---

## 📌 Business Takeaways

- Customers with **month-to-month contracts**, **high monthly charges**, and **low tenure** are most at risk.
- Proactively targeting these customers with offers or loyalty plans can reduce churn significantly.

---

## 🚀 Future Improvements

- Tune decision thresholds to optimize precision/recall trade-off
- Use SHAP values for model interpretability
- Deploy as a web app or API for real-time predictions

---

## 🛠️ Tech Stack

- Python
- Pandas, NumPy
- Scikit-learn, XGBoost
- Matplotlib, Seaborn
- Jupyter Notebook

---

## 📂 Project Structure

```text
📦 Customer_Churn_Prediction
├── Customer churn Pred model.ipynb
├── README.md
├── churn_data.csv
├── models/
│   └── logistic_model.pkl

```
---
## 🙋‍♂️ Author

**Kundan Yadav**  
Aspiring Data Analyst / ML Enthusiast  
🔗 [LinkedIn](linkedin.com/in/kundan-yadav-6057b2323)  
📫 [Email](mailto:wekundan@gmail.com)


## ⭐ If you found this helpful, feel free to star the repo!

