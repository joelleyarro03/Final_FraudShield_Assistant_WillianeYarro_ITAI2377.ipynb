# Final_FraudShield_Assistant_WillianeYarro_ITAI2377.ipynb
Credit Card FrauShield

---

# **FraudShield AI Assistant**

### *Credit Card Fraud Detection & Explainable AI System*

**Course:** ITAI 2377 – Implementing a Domain-Specific AI Assistant
**Team:** Williane Yarro • Jemima • Thien

---

## **📌 Overview**

FraudShield is a domain-specific AI assistant designed to detect and explain potential credit card fraud using machine-learning techniques and human-interpretable insights. This project transforms the midterm design into a fully implemented system that preprocesses real transactional data, engineers fraud-related features, trains optimized ML models, and provides an assistant interface for transaction-level risk assessment.

---

## **✨ Key Features**

* **Full ML pipeline**: preprocessing, encoding, scaling, class-balancing with SMOTE
* **Advanced feature engineering**:

  * Customer–merchant distance (Haversine)
  * Spending velocity & transaction gaps
  * Night-time transaction flag
  * Hour-of-day & day-of-week
* **Multiple model implementations**: Logistic Regression, Random Forest, XGBoost
* **Explainable assistant interface** that outputs:

  * Fraud probability
  * Prediction label
  * Human-friendly explanations
* **Evaluation metrics**: Confusion matrix, classification report, ROC–AUC

---

## **📂 Project Structure**

```
FraudShield/
│── FraudShield_AI_Assistant.ipynb   # Main Colab notebook
│── data/                            # Dataset (not included due to size)
│── models/                          # Model artifacts (optional)
│── README.md                        # Project documentation
│── report/                          # Final PDF report
```

---

## **🧠 Methodology**

### **1. Data Preprocessing**

* Removed unnecessary PII columns
* Cleaned timestamps
* Converted categorical → string
* Scaled numerical features
* One-hot encoded categorical variables

### **2. Feature Engineering Highlights**

* **Distance feature:** detects out-of-pattern geographic behavior
* **Velocity feature:** identifies rapid or burst transactions
* **Night indicator:** fraud tends to increase during late hours
* **Temporal patterns:** hourly & weekly behavior

### **3. Model Training**

Three classifiers were trained and compared:

| Model               | Pros                | Cons                       |
| ------------------- | ------------------- | -------------------------- |
| Logistic Regression | Fast, baseline      | Weak on nonlinear patterns |
| Random Forest       | Good recall, robust | High runtime               |
| **XGBoost**         | Best performance    | Requires tuning            |

**Final Model:** XGBoost with optimized parameters.

### **4. Class Imbalance Handling**

Used **SMOTE** to oversample minority fraud cases and improve recall.

---

## **🧪 Evaluation Results**

Key metrics include:

* **Precision / Recall / F1-score**
* **ROC–AUC Score**
* **Confusion Matrix**

The final XGBoost model produced the best overall performance, particularly in detecting rare fraud cases.

---

## **🤖 FraudShield Assistant**

A simple interface built inside the notebook to:

* Accept a transaction
* Predict fraud probability
* Output a label (fraud or legit)
* Provide explainable reasoning

### **Sample Output**

```
---- FraudShield Assistant ----
Risk Score: 0.942 (HIGH FRAUD RISK)
Explanation:
- Transaction at late night
- Customer far from merchant location
- Abnormally high spending velocity
```

---

## **👥 Team Contributions**

### **Williane – Lead Technical Developer**

* Built preprocessing pipeline
* Engineered features
* Implemented ML models
* Built assistant interface
* Major contributor to the technical report

### **Jemima – Data Analysis & Documentation**

* Conducted EDA
* Validated metrics and results
* Contributed to report writing

### **Thien – Research & Organization**

* Researched best practices
* Structured the final report
* Ensured clarity and formatting

---

## **⚙️ Requirements**

This project runs entirely in **Google Colab**.

### Install Dependencies:

```bash
pip install xgboost imbalanced-learn haversine
```

---

## **🚀 How to Run**

1. Open the Colab notebook
2. Upload or mount the dataset
3. Run preprocessing cells
4. Train the models
5. Evaluate metrics
6. Use the FraudShield Assistant at the end of the notebook

---

## **🧩 Future Improvements**

* Deploy model using FastAPI or Flask
* Add SHAP explainability visuals
* Build a web dashboard
* Implement real-time streaming detection

---

## **📚 References**

Full list of academic and technical references is available in the final report.

---

## **📄 License**

This project is for educational purposes under ITAI 2377.

---

If you want, I can also generate:
✔ A **shorter README**
✔ A **more professional GitHub-style README** with badges
✔ A **README with images and diagrams**
