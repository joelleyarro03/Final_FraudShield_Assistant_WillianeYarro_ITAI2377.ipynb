# FraudShield: Credit Card Fraud Detection System

**Author:** Williane Yarro  
**Course:** ITAI2377  
**Project:** Credit Card Fraud Detection using Machine Learning

## 📋 Project Overview

FraudShield is an advanced credit card fraud detection system that leverages machine learning algorithms to identify potentially fraudulent transactions. The system analyzes transaction patterns and features to distinguish between legitimate and fraudulent activities with high accuracy.

## 🎯 Features

- **Multi-Model Approach**: Implements and compares multiple ML algorithms:
  - Logistic Regression
  - Decision Tree
  - Random Forest
  - Gradient Boosting

- **Comprehensive Analysis**:
  - Exploratory Data Analysis (EDA)
  - Feature importance analysis
  - Model performance comparison
  - ROC curve visualization
  - Confusion matrix analysis

- **Production-Ready**:
  - Model serialization for deployment
  - Scalable preprocessing pipeline
  - Performance metrics tracking

## 🚀 Getting Started

### Prerequisites

- Python 3.8 or higher
- pip package manager
- Jupyter Notebook

### Installation

1. Clone the repository:
```bash
git clone https://github.com/joelleyarro03/Final_FraudShield_Assistant_WillianeYarro_ITAI2377.ipynb.git
cd Final_FraudShield_Assistant_WillianeYarro_ITAI2377.ipynb
```

2. Install required dependencies:
```bash
pip install -r requirements.txt
```

3. Launch Jupyter Notebook:
```bash
jupyter notebook
```

4. Open `FraudShield_Credit_Card_Detection.ipynb` and run the cells.

## 📊 Dataset

The system uses a synthetic credit card transaction dataset that simulates real-world fraud patterns. The dataset includes:
- Transaction amount
- Transaction time
- Multiple anonymized features (V1-V10)
- Binary classification target (0: Legitimate, 1: Fraud)

## 🔧 Usage

### Running the Analysis

1. Open the Jupyter notebook
2. Execute cells sequentially to:
   - Load and explore the data
   - Preprocess features
   - Train multiple models
   - Evaluate and compare performance
   - Generate predictions

### Making Predictions

```python
import joblib

# Load the trained model and scaler
model = joblib.load('fraudshield_model.pkl')
scaler = joblib.load('fraudshield_scaler.pkl')

# Prepare new transaction data
new_transaction = [[amount, time, v1, v2, v3, v4, v5, v6, v7, v8, v9, v10]]
new_transaction_scaled = scaler.transform(new_transaction)

# Predict
prediction = model.predict(new_transaction_scaled)
probability = model.predict_proba(new_transaction_scaled)[:, 1]

print(f"Fraud Prediction: {'Fraud' if prediction[0] == 1 else 'Legitimate'}")
print(f"Fraud Probability: {probability[0]:.2%}")
```

## 📈 Model Performance

The system evaluates models based on:
- **Accuracy**: Overall correctness
- **Precision**: Fraud detection accuracy
- **Recall**: Fraud detection coverage
- **F1-Score**: Balanced performance metric
- **ROC-AUC**: Classification quality

## 🛡️ Key Components

### 1. Data Preprocessing
- Feature scaling using StandardScaler
- Train-test split with stratification
- Handling imbalanced classes

### 2. Model Training
- Multiple algorithm implementation
- Cross-validation support
- Hyperparameter optimization ready

### 3. Evaluation
- Comprehensive metrics
- Confusion matrix analysis
- ROC curve visualization
- Feature importance ranking

### 4. Deployment
- Model serialization
- Scaler persistence
- Production-ready predictions

## 📝 Project Structure

```
Final_FraudShield_Assistant_WillianeYarro_ITAI2377.ipynb/
│
├── FraudShield_Credit_Card_Detection.ipynb  # Main notebook
├── requirements.txt                          # Python dependencies
├── README.md                                 # Project documentation
├── fraudshield_model.pkl                    # Trained model (generated)
└── fraudshield_scaler.pkl                   # Feature scaler (generated)
```

## 🔍 Results

The FraudShield system achieves:
- High fraud detection rate
- Low false positive rate
- Strong overall accuracy
- Balanced precision and recall

Detailed results and visualizations are available in the notebook.

## 🚀 Future Enhancements

- [ ] Real-time transaction processing
- [ ] API endpoint for predictions
- [ ] Advanced feature engineering
- [ ] Deep learning models
- [ ] Automated model retraining
- [ ] A/B testing framework
- [ ] Dashboard for monitoring

## 📚 Dependencies

- pandas: Data manipulation
- numpy: Numerical computing
- scikit-learn: Machine learning algorithms
- matplotlib: Data visualization
- seaborn: Statistical visualization
- joblib: Model serialization
- jupyter: Interactive notebook environment

## 👥 Contributing

This is an academic project for ITAI2377. For questions or suggestions, please contact the author.

## 📄 License

This project is created for educational purposes as part of the ITAI2377 course.

## 🙏 Acknowledgments

- Course: ITAI2377
- Instructor: [Course Instructor]
- Institution: [Educational Institution]

---

**Last Updated:** December 2025  
**Version:** 1.0.0
