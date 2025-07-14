# Customer-Churn-Prediction

🎯 Objective

The goal of this project was to predict customer churn for a bank using a real-world dataset. Churn refers to customers closing their accounts or stopping the use of services. By accurately identifying customers at risk of churn, banks can take proactive steps to improve retention, reduce loss, and increase customer lifetime value.


---

📊 Data Overview

Dataset: 10,000 bank customer records

Target: Exited (1 = churned, 0 = retained)

Features: Demographics, account activity, credit score, balance, products held, etc.



---

🔎 Key Insights from EDA & Correlation

The churn rate was around 20%, indicating class imbalance.

From the correlation heatmap, Age showed the highest positive correlation with Exited (0.29), suggesting older customers are more likely to churn.

IsActiveMember had a negative correlation with churn (-0.16), indicating inactive customers are more likely to leave.



---

🔬 Modeling Approach

Performed data preprocessing including:

Dropping ID-like columns

One-hot encoding for Gender and Geography

Scaling numerical features


Baseline Model: RandomForestClassifier

Applied SMOTE to address class imbalance

Compared baseline model vs. SMOTE-resampled model



---

📈 Model Results Summary

Model	Accuracy	Recall (Churn)	F1 (Churn)	AUC

Baseline RandomForest	87%	0.47	0.58	0.71
RF + SMOTE	84%	0.59	0.59	0.74
XGBoost + SMOTE	85%	0.57	0.61	0.747 ✅


The best-performing model was XGBoost with SMOTE, which improved recall and AUC while keeping accuracy stable.

This means the model could catch more at-risk customers without significantly increasing false positives.



---

🧠 Feature Importance & SHAP Insights

From the feature importance chart, the top churn drivers were:

Age (most important)

EstimatedSalary

Balance

CreditScore

NumberOfProducts


SHAP interaction plots confirmed that:

Higher age and certain credit score ranges significantly impact churn risk.

Interactions between features (e.g., Age and CreditScore) further influence decisions.




---

✅ Final Conclusion

This project demonstrates how machine learning and explainable AI can effectively predict customer churn in the banking sector. Using XGBoost + SMOTE, the final model achieved:

85% Accuracy

0.747 ROC AUC

0.61 F1-Score for Churn Class


Key insights revealed that older, inactive customers with high balance and fewer product holdings are most at risk of leaving. The model's interpretability using SHAP allows for targeted business strategies, such as:

Personalized re-engagement for inactive but valuable customers

Cross-sell offers to single-product holders

Loyalty benefits for senior or high-value customers
