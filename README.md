# Fraud Detection Using Machine Learning

This project implements a machine learning solution to detect fraudulent financial transactions using a real-world dataset containing over 6 million records. The goal is to identify key risk factors and predict fraud with high accuracy using a robust and interpretable model.

## Dataset

- Transactions simulated over 30 days (1 hour = 1 step, 744 steps total)
- Contains various types of financial activities: `CASH-IN`, `CASH-OUT`, `DEBIT`, `PAYMENT`, and `TRANSFER`
- Each transaction includes account balances, type, amount, and fraud labels

## Features Used

- `step`: Time unit of the transaction
- `type`: Type of transaction (encoded)
- `amount`: Transaction amount
- `oldbalanceOrg`, `newbalanceOrig`: Sender balances before and after transaction
- `oldbalanceDest`, `newbalanceDest`: Receiver balances before and after transaction
- `errorOrig`, `errorDest`: Engineered features representing balance inconsistencies

## Target Variable

- `isFraud`: 1 if the transaction is fraudulent, 0 otherwise

## Tools & Technologies

- Python
- Pandas, NumPy, Matplotlib, Seaborn
- Scikit-learn
- XGBoost
- SHAP (Explainability)

## Model

The model is built using XGBoost, chosen for its performance on structured tabular data and ability to handle class imbalance effectively.

### Evaluation Metrics

- Accuracy: 100%
- Precision: 100%
- Recall: 100%
- F1-Score: 100%
- ROC AUC: 0.9983

### Confusion Matrix

|              | Predicted: 0 | Predicted: 1 |
|--------------|--------------|--------------|
| Actual: 0    | 5999         | 1            |
| Actual: 1    | 8            | 2456         |

## Key Findings

- Fraudulent activities are primarily found in `TRANSFER` and `CASH_OUT` transaction types.
- Fraud often involves large amounts and inconsistent account balances.
- Accounts with zero or very low balances before and after transactions are more likely to be involved in fraud.

## Prevention Recommendations

- Implement real-time fraud scoring models
- Auto-flag transactions over a defined threshold (e.g., 200,000)
- Apply multi-factor authentication for high-risk transactions
- Monitor unusual balance behavior and transaction timings

## Conclusion

This project demonstrates the development of a fraud detection model with high performance and practical applicability. The combination of engineered features and explainable AI ensures interpretability and robustness for deployment in financial environments.


