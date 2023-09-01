# Credt-Card-Fraud-Detection

While touring a new city a few days ago, I misplaced my wallet. I did not realize it then, but I woke up to notifications about spending over $2500 at around 4AM. I blocked my credit cards right then and had all the transactions canceled and refunded. I assumed it should be pretty straightforward that a guy who does not make a transaction of over $700 at a time would not complete a transaction of $2500 out of the blue. This activity should have been enough reason to block the transaction. This experience brought my attention to credit card fraud.

Context: 
Credit card companies must be able to recognize fraudulent credit card transactions so that customers are not charged for items that they did not purchase. At the same time, a credit card company should not be blocking your card over a transaction that you may have made yourself. We will try to understand these challenges in this notebook.

About the dataset:
The dataset contains transactions made by credit cards in September 2013 by European cardholders. This dataset presents transactions in two days, with 492 frauds out of 284,807 transactions. The dataset is highly unbalanced; the positive class (frauds) accounts for 0.172% of all transactions. It contains only numerical input variables resulting from a PCA transformation. Unfortunately, due to confidentiality issues, original features and more background information about the data have not been provided. Features V1 through V28 are the principal components obtained with PCA. The only features not transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount. Feature 'Class' is the response variable, and it takes value 1 in case of fraud and 0 otherwise.

My approach is divided into the following sections:
  1. Exploratory data analysis - check missing values, class distribution, feature correlation
  2. Extreme outlier detection & removal - identify extreme outliers and cap their values
  3. Data preparation - normalize unscaled features and perform train-test split
  4. Random Undersampling - undersample to get a 1:1 ratio of fraud to non-fraud cases
  5. SMOTE (Oversampling) - oversample to get a 1:1 ratio of fraud to non-fraud cases
  6. Model implementation on Test Data - run Logistic Regression, KNN, SVM, Decision Trees

Conclusion:
One of the main factors affecting the model's interpretability is the variables' lack of explainability. Since the variables were renamed to V_features (V1 through V28), there is no definitive way to explain how any V_feature affects the probability of fraud. The primary challenge is that the dataset is so heavily skewed (98% fraud v/s 2% non-fraud transaction) that our model will not be able to differentiate between fraud and non-fraud transactions with a high level of precision. A key detail to remember is that 'Accuracy' should not be used as a metric for model evaluation due to the massively skewed nature of our data. To tackle this, I have used Recall and AUC-PR as evaluation metrics (AUC-PR is the Area Under the Precision-Recall Curve). The precision-recall curve is very convenient, as in our case, the positive (fraud) class is more concerning than the negative (non-fraud) class. The undersampled model cannot be relied on (AUC-PR of undersampled dataset = 0.05), but the oversampled model provides a much more reliable solution (AUC-PR of oversampled dataset = 0.75). Hence, we can conclude that the oversampling technique (SMOTE) is much more reliable in identifying fraud. Also, the Logistic Regression model provides us with a respectable Recall score of 0.94, which is essential because it is the metric that will help us try to capture the most fraudulent transactions. Due to the imbalanced nature of the data, many non-fraud transactions could be predicted as fraudulent ones, and utilizing Recall as an evaluation metric addresses this complication.

Here are some visualizations:

![image](https://github.com/0nkarkhanolkar/SBA-Loan-Default-Analysis/assets/98197574/5930c0e0-f003-41ce-9df0-4c60aab5367d)

![image](https://github.com/0nkarkhanolkar/SBA-Loan-Default-Analysis/assets/98197574/a4693abb-c995-46fa-928a-ff728afaec34)

![image](https://github.com/0nkarkhanolkar/SBA-Loan-Default-Analysis/assets/98197574/0f774ebe-cbea-4ab6-a4a3-c3988a9297da)

![image](https://github.com/0nkarkhanolkar/SBA-Loan-Default-Analysis/assets/98197574/034847a4-2caa-4a04-ac27-480dcd42ba3e)
