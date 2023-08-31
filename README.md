# Credt-Card-Fraud-Detection

While touring a new city a few days ago, I misplaced my wallet. I did not realize it then, but I woke up to notifications about spending over $2500 at around 4AM. I blocked my credit cards right then and had all the transactions canceled and refunded. I assumed it should be pretty straightforward that a guy who does not make a transaction of over $700 at a time would not complete a transaction of $2500 out of the blue. This activity should have been enough reason to block the transaction. This experience brought my attention to credit card fraud.

Context: 
Credit card companies must be able to recognize fraudulent credit card transactions so that customers are not charged for items that they did not purchase. At the same time, a credit card company should not be blocking your card over a transaction that you may have made yourself. We will try to understand these challenges in this notebook.

About the dataset:
The dataset contains transactions made by credit cards in September 2013 by European cardholders. This dataset presents transactions in two days, with 492 frauds out of 284,807 transactions. The dataset is highly unbalanced; the positive class (frauds) accounts for 0.172% of all transactions. It contains only numerical input variables resulting from a PCA transformation. Unfortunately, due to confidentiality issues, original features and more background information about the data have not been provided. Features V1 through V28 are the principal components obtained with PCA. The only features not transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount. Feature 'Class' is the response variable, and it takes value 1 in case of fraud and 0 otherwise.

My approach is divided into the following sections:

Exploratory data analysis - check missing values, class distribution, feature correlation 
Extreme outlier detection & removal - identify extreme outliers and cap their values
Data preparation - normalize unscaled features and perform train-test split
Random Undersampling - undersample to get a 1:1 ratio of fraud to non-fraud cases
SMOTE (Oversampling) - oversample to get a 1:1 ratio of fraud to non-fraud cases
Model implementation on Test Data - run Logistic Regression, KNN, SVM, Decision Trees

Here are some visualizations:

![image](https://github.com/0nkarkhanolkar/SBA-Loan-Default-Analysis/assets/98197574/5930c0e0-f003-41ce-9df0-4c60aab5367d)

![image](https://github.com/0nkarkhanolkar/SBA-Loan-Default-Analysis/assets/98197574/a4693abb-c995-46fa-928a-ff728afaec34)

![image](https://github.com/0nkarkhanolkar/SBA-Loan-Default-Analysis/assets/98197574/0f774ebe-cbea-4ab6-a4a3-c3988a9297da)

![image](https://github.com/0nkarkhanolkar/SBA-Loan-Default-Analysis/assets/98197574/034847a4-2caa-4a04-ac27-480dcd42ba3e)
