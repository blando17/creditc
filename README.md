# Credit Card Fraud Detection 💳🔍

This project focuses on detecting fraudulent credit card transactions using a logistic regression model. The system classifies transactions as either *normal* or *fraudulent* based on anonymized and scaled transaction features.

##  Dataset

The dataset used is `creditcard.csv` and contains:
- **11,958 rows** (after removing missing values)
- **30 features** including anonymized PCA components (`V1` to `V28`), `Time`, `Amount`, and the `Class` label.

### Features:
- Time, Amount
- V1 to V28 (PCA transformed features)

### Target:
- `Class`
  - 0 → Normal Transaction
  - 1 → Fraudulent Transaction

##  Workflow

### 1. **Data Collection & Cleaning**
- Loaded the dataset using `pandas`
- Removed rows with missing values
- Verified class distribution (highly imbalanced)

### 2. **Data Preparation**
- Split features (`X`) and labels (`y`)
- Used `train_test_split` with stratification (80% train, 20% test)

### 3. **Model Training**
- Used **Logistic Regression** from scikit-learn
- Trained on the preprocessed dataset

### 4. **Evaluation**
- **Training Accuracy**: 99.87%
- **Testing Accuracy**: 99.75%
- Though accuracy is high, precision-recall metrics are crucial in real fraud detection due to class imbalance.

### 5. **Prediction System**
- Built a system to predict a single transaction’s fraud status from feature values
- Returns:
  - **"Fraudulent Transaction"** if prediction is 1
  - **"Normal Transaction"** if prediction is 0

## Libraries & Tools

- Python
- NumPy, Pandas
- Scikit-learn (LogisticRegression, accuracy_score, train_test_split)

##  Challenges

- Highly imbalanced data (Normal >> Fraud)
- Real-world deployment would benefit from techniques like:
  - SMOTE (Synthetic Minority Over-sampling)
  - Anomaly Detection
  - Precision/Recall trade-off tuning

##  How to Run

1. Load `creditcard.csv` into your environment
2. Run the preprocessing steps to clean the data
3. Train the logistic regression model
4. Use the prediction system to detect fraud in new transaction data

##  Conclusion

This project demonstrates the effectiveness of logistic regression in identifying fraudulent transactions when data is properly preprocessed and managed. Further enhancement with advanced techniques would increase reliability in production.
