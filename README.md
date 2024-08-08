# credit-risk-classification

# Purpose of the Analysis
The goal of this analysis was to leverage historical lending data from a peer-to-peer lending service to create a model that predicts whether a loan will be classified as healthy or high-risk.

************************
# Financial Information and Prediction Goals
The dataset used for this model contained over 77,000 data points, featuring the following seven attributes:

- Loan Size: The amount requested by the borrower.
- Interest Rate: The cost of borrowing expressed as a percentage.
- Borrower's Yearly Income: The annual income of the borrower.
- Debt-to-Income Ratio: The borrower's total debt compared to their income.
- Number of Accounts: The total number of credit accounts held by the borrower.
- Derogatory Marks: Negative items on the borrower’s credit report (e.g., bankruptcies, defaults).
- Total Debt: The total amount of debt the borrower has.

Using these features, the model aims to determine whether a loan is healthy or high-risk. This allows lenders to adjust the loan size and interest rate offered to align with the prediction of a healthy loan. For instance, if a borrower requests a $15,000 loan and the model consistently predicts it as high-risk, the lender might deny the loan. However, if reducing the amount to $10,000 results in a healthy prediction, the lender could offer that lower amount instead of outright denying the loan. An effective model will help reduce the number of defaulted loans.

********************
# Stages of the Machine Learning Process
Data Splitting: The dataset was randomly divided into training and testing sets, with 75% of the data used for training and 25% for testing.

Model Training: A Logistic Regression model was created using the training data with the LogisticRegression function from sklearn.linear_model.

Prediction: The model was applied to the testing dataset to predict loan statuses.

Model Evaluation: The model's performance was assessed using three functions from sklearn.metrics:

- Calculating the balanced accuracy score
- Generating a confusion matrix
- Printing a classification report

*********************************
# Results

Accuracy: The balanced accuracy score was 95%, calculated using the balanced_accuracy_score function from the sklearn.metrics library. This score is lower than the overall accuracy score of 99%, reflecting the dataset's imbalance, which contains significantly more healthy loans than high-risk loans. The model excels at predicting healthy loans, resulting in a higher accuracy score. Both scores indicate strong confidence in the model’s predictions, with a 95% reliability overall.

Precision: The classification report indicated a precision of 1.00 for healthy loan predictions, meaning that the model is correct almost every time it identifies a loan as healthy. In contrast, the precision for high-risk loans was 0.85, suggesting that 15% of loans predicted as high-risk may actually be healthy. This highlights a significant risk of denying good loans based solely on the model's predictions.

Recall: The recall for healthy loans was 0.99, indicating that the model accurately identifies 99% of actual healthy loans. The recall for high-risk loans was 0.91, meaning that 91% of actual high-risk loans were correctly predicted.

# Summary

Lenders must consider whether to rely entirely on the model's predictions. They should evaluate if the cost of erroneously denying 15% of healthy loans is justified by the model's ability to correctly identify 91% of high-risk loans. This assessment should include a review of their current lending decisions to compare performance.

Overall, lenders can trust the model’s predictions when it classifies a loan as healthy. Therefore, I recommend using the model’s predictions for approving loans, while suggesting that they review additional factors for loans identified as high-risk before making a final decision.



