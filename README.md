Fraud Detection Model
📌 Project Overview
This project focuses on detecting fraudulent financial transactions using machine learning techniques. The dataset contains 744 hours (30 days) of simulated transaction data, with various transaction types such as CASH-IN, CASH-OUT, DEBIT, PAYMENT, and TRANSFER.
The goal is to build a model that maximizes fraud recall while minimizing false positives, providing actionable insights for real-time fraud prevention.

📂 Dataset Description
Columns:

step – Unit of time in hours (1 step = 1 hour)

type – Transaction type

amount – Transaction amount in local currency

nameOrig / nameDest – IDs of sender and receiver

oldbalanceOrg / newbalanceOrig – Sender’s balance before & after transaction

oldbalanceDest / newbalanceDest – Receiver’s balance before & after transaction

isFraud – Fraudulent transaction flag

isFlaggedFraud – Flag for illegal attempts (e.g., >200k transfer)

🔍 Exploratory Data Analysis (EDA)
Analyzed transaction types and amounts for fraud patterns

Visualized distribution of transaction amounts and balances

Identified that TRANSFER and CASH-OUT types are most associated with fraud

Engineered new features like balance differences and merchant flags

🛠️ Technologies Used
Python – Pandas, NumPy, Matplotlib, Seaborn

Machine Learning: Scikit-learn, LightGBM

Evaluation Metrics: Precision, Recall, F1-score, ROC AUC

⚙️ Model Development Process
Data Cleaning: Removed identifiers (nameOrig, nameDest) to avoid data leakage

Feature Engineering: Created balanceDiffOrig, balanceDiffDest, and merchant flag variables

Encoding: One-hot encoded transaction type

Model Training: Tested Logistic Regression, Random Forest, and LightGBM

Evaluation: Selected LightGBM for its high recall and robust performance

📈 Model Performance (Example Results)
Model	Precision (Fraud)	Recall (Fraud)	F1-Score (Fraud)	ROC AUC
Logistic Regression	0.85	0.78	0.81	0.96
Random Forest	0.92	0.85	0.88	0.98
LightGBM	0.94	0.91	0.92	0.99

💡 Key Insights
Fraud is highly correlated with TRANSFER and CASH-OUT transactions.

Sudden large balance drops in sender accounts and big spikes in receiver accounts are strong indicators of fraud.

Real-time detection should prioritize recall to avoid missing fraudulent activities.
