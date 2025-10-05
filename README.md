# Mobile Transaction Fraud Prediction

## Project Overview
Mobile financial fraud is a growing threat, causing financial losses and eroding trust. This project aims to develop a **high-precision, real-time machine learning model** to detect fraudulent transactions, enhancing security and providing actionable insights into fraud patterns.

## Objective
- Develop a real-time fraud detection system for mobile financial transactions.  
- Leverage **Exploratory Data Analysis (EDA)** and advanced machine learning techniques to accurately identify fraudulent activities.  
- Enhance financial security, minimize losses, and provide insights into fraud patterns and risks.

## Problem-Solving Approach
1. Reading and Understanding the Data  
2. Data Exploration  
3. Feature Engineering  
4. Data Inspection / Cleaning / Transformation  
5. Exploratory Data Analysis (EDA)  
6. Data Preparation (Train/Test Split)  
7. Multiple Model Building & Hyperparameter Tuning  
8. Model Evaluation

## Dataset Description
| Column | Description |
|--------|-------------|
| step | Unit of time in hours |
| type | Transaction type (CASH-IN, CASH-OUT, DEBIT, PAYMENT, TRANSFER) |
| amount | Transaction amount in local currency |
| nameOrig | Customer initiating the transaction |
| oldbalanceOrg | Initial balance before the transaction |
| newbalanceOrig | New balance after the transaction |
| nameDest | Recipient of the transaction |
| oldbalanceDest | Recipient's initial balance |
| newbalanceDest | Recipient's new balance |
| isFraud | Indicates if the transaction is fraudulent |

## Exploratory Data Analysis (EDA)
- **Fraud Distribution:** 89.8% non-fraudulent, 10.2% fraudulent — significant class imbalance.  
- **Transaction Type Distribution:** "Payment" most frequent (~50%), "Transfer" & "Cash Out" less frequent.  
- **Amount vs Type:** "Transfer" and "Cash Out" have higher values; smaller amounts for "Payment" and "Debit".  
- **Fraud vs Non-Fraud Amounts:** Fraud mostly in smaller amounts; high-value transactions rarely fraudulent.  
- **Balance Changes (Origin & Destination):** Non-fraud follows expected patterns; fraudulent transactions show irregularities and deviations.

## Data Preprocessing
- **Encoding Categorical Variables:** Converted 'Type' column to numeric using mapping/one-hot encoding.  
- **Dropping Irrelevant Columns:** 'step', 'nameOrig', 'nameDest' removed as they do not contribute to fraud prediction.

## Model Selection & Evaluation
- **Algorithms Used:** Logistic Regression, Logistic Regression (SMOTE), Random Forest, Gradient Boosting, XGBoost, AdaBoost, Voting Classifier.  
- **Performance Summary (Random Forest / AdaBoost / XGBoost):**  
  - True Positives: 221–225  
  - False Positives: 4–9  
  - False Negatives: 5–10  
  - True Negatives: 1990–1995  
  - **AUC:** 0.98–1.00  
  - High precision, recall, and F1-score, indicating excellent fraud detection capabilities.

## Key Results
- **Precision:** 96%  
- **Recall (Sensitivity):** 97%  
- **Accuracy:** 99.23%  
- **F1-Score:** 99.23%  
- **ROC AUC:** 99.64%  

> The model reliably detects fraudulent transactions with minimal false positives and false negatives, reducing financial losses and safeguarding users.

## Repository Structure
- `notebooks/fraud_prediction.ipynb` → Jupyter Notebook with full code  
- `data/Fraud_Analysis_Dataset.csv` → Original dataset  
- `docs/` → Any presentations or supporting files (optional)

## Conclusion
AdaBoost demonstrates **remarkable performance** for mobile transaction fraud prediction. High training and testing accuracy with minimal gaps indicate strong generalization. Key metrics (Precision, Recall, F1-Score, ROC-AUC) confirm the model's reliability and effectiveness in real-world fraud detection scenarios.
