# credit-risk-classification

### Background

In this Challenge, you’ll use various techniques to train and evaluate a model based on loan risk. You’ll use a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

### Instructions

The instructions for this Challenge are divided into the following subsections:

* Split the Data into Training and Testing Sets
* Create a Logistic Regression Model with the Original Data
* Write a Credit Risk Analysis Report

#### Split the Data into Training and Testing Sets

Open the starter code notebook and use it to complete the following steps:

1. Read the `lending_data.csv` data from the Resources folder into a Pandas DataFrame.
2. Create the labels set (`y`) from the “loan_status” column, and then create the features (`X`) DataFrame from the remaining columns.
   **note**A value of 0 in the “loan_status” column means that the loan is healthy. A value of 1 means that the loan has a high risk of defaulting.
3. Split the data into training and testing datasets by using `train_test_split`.

#### Create a Logistic Regression Model with the Original Data

Use your knowledge of logistic regression to complete the following steps:

1. Fit a logistic regression model by using the training data (`X_train` and `y_train`).
2. Save the predictions for the testing data labels by using the testing feature data (`X_test`) and the fitted model.
3. Evaluate the model’s performance by doing the following:
   * Generate a confusion matrix.
   * Print the classification report.
4. Answer the following question: How well does the logistic regression model predict both the 0 (healthy loan) and 1 (high-risk loan) labels?

#### Write a Credit Risk Analysis Report

Write a brief report that includes a summary and analysis of the performance of the machine learning models that you used in this homework. You should write this report as the `README.md` file included in your GitHub repository.

Structure your report by using the report template that `Starter_Code.zip` includes, ensuring that it contains the following:

1. **An overview of the analysis:** Explain the purpose of this analysis.
2. **The results:** Using a bulleted list, describe the accuracy score, the precision score, and recall score of the machine learning model.
3. **A summary:** Summarize the results from the machine learning model. Include your justification for recommending the model for use by the company. If you don’t recommend the model, justify your reasoning.

## Overview of the Analysis

Machine learning techniques are applied to analyze a dataset of historical lending activities from a peer-to-peer lending service, aiming to develop a model that assesses borrowers' creditworthiness.

The analysis considered factors such as loan size, interest rate, borrower income, debt-to-income ratio, number of accounts, derogatory marks, total debt and loan status. A dataset of 77,536 entries was split into training and testing sets.

#### Step 1: 

Data was read into a Pandas dataframe

#### Step 2: 

The data was labeled with the dependent variable (`y`) set as "loan_status," while the independent features (`X`) were assigned to the remaining columns.

#### Step 3:

The dataset was divided into training and testing subsets using the `train_test_split` function from the `sklearn.model_selection` module. This process ensures that the model is trained on one portion of the data and evaluated on a separate, unseen portion to assess its performance.

#### Step 4: 

Using scikit-learn's LogisticRegression module, a logistic regression model was trained on the original dataset and tested to predict whether loans were healthy (0) or high-riskn(1).

#### Results

###### Healthy Loans

* Precision: 100%
* Recall: 100%
* F1-score: 100%
* Support: 18759

###### High-rish Loans

* Precision: 87%
* Recall: 95%
* F1-score: 91%
* Support: 625

###### Overall

* Accuracy: 99%
* Macro Avg: 95%
* Weighted Avg: 99%

## Summary

The dataset exhibits a significant class imbalance, with 18,759 instances of class `0` and only 625 instances of class `1`. To address this, the weighted average metric is used. While the model performs well overall, its precision for class `1` (0.87) indicates some false positives for this minority class. Although the accuracy is very high (0.99), accuracy alone can be misleading in imbalanced datasets. Encouragingly, the F1-score for the minority class (0.91) suggests that the model handles the imbalance reasonably well.

This model is recommended, but to further enhance the performance for the minority class, techniques such as oversampling, undersampling, or adjusting class weights should be considered if improving minority class predictions is a priority.
