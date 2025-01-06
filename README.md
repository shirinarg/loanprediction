# Loan Approval Prediction

# Problem Statement
In the field of financial lending, accurately predicting borrower risk and determining loan approval status are crucial for both lenders and borrowers. Traditional evaluation methods can be slow and may lack the necessary objectivity to effectively gauge risk. This project seeks to develop a classification model that can evaluate a borrower's eligibility for loan approval. By utilizing historical data and classification techniques, the objective is to improve decision-making processes and ensure equitable access to credit.

# Data Preparation
1. Data Acquisition. For this project, we are using the Financial Risk for Loan Approval dataset from Kaggle, which provides a comprehensive collection of data related to loan applications, including applicant details and loan outcomes. The dataset is accessible at Kaggle's dataset page: https://www.kaggle.com/datasets/lorenzozoppelletto/financial-risk-for-loan-approval.
2. Data Cleaning. Handling missing values - Using df.isna().sum()function, we have validated that the dataset does not consist of any missing values.
3. Encoding Categorical Variables. Converted categorical variables (e.g., applicant gender, marital status) into numerical representations using one-hot encoding and label encoding.

# Model Evaluation
Below is a summary of each model's performance on the validation sets before and after the hyperparameter tuning. 
We chose to look at both the accuracy and precision metric as they are standard metrics used in classification problems. As the data set is partially imbalanced, containing around 75% loan rejections and 25% of loan approvals, the precision score will give a good idea of the amount of positive results correctly predicted. We still choose accuracy as our main metric as we aim to understand whether a person is likely to get approved or rejected for a loan and if it is more common to be rejected, then the model should reflect that. 

| Model                    | Before Tuning Hyper-parameters |                 | After Tuning Hyper-parameters |                 |
|--------------------------|--------------------------------|-----------------|-------------------------------|-----------------|
|                          | Accuracy Score                 | Precision Score | Accuracy Score                | Precision Score |
| Logistic Regression      |                                | 0.93            |                               | 0.94            |
| Extra Trees Classifier   | 0.92                           | 0.66            | 0.75                          | 0.00            |
| Random Forest Classifier | 0.93                           | 0.82            | 0.76                          | 0.00            |
| XGBoost                  | 0.95                           | 0.87            | 0.96                          | 0.90            |
| Ensemble Learning        | N/A                            | N/A             | 0.95                          | 0.70            |

Looking at the scores of precision and accuracy, for the Extra Trees and Random Forest classifiers, we saw the performance decrease after tuning the hyperparameters. This is likely due to overfitting happening when the optimal hyperparameters are chosen based on the training data causing the models to not generalize well on new unseen data. 
The logistic regression and XGBoost models performed the best on the data before and after the tuning. On their own, these 2 models performed well on unseen data.  
When we used ensemble learning, we were able to create another model that performed as well as our 2 best models and significantly better than our 2 weakest classifiers. 

# Conclusion
In conclusion, this project successfully established a predictive framework for assessing the loan approval status of applicants. By utilizing classification models, we demonstrated the ability to accurately evaluate the eligibility of loans.
This predictive model will serve to streamline the approval process of a loan for both borrowers and lenders. Future augmentations of this model can use the inclusion of more diverse datasets by incorporating other parameters such as economic conditions and real-time risk assessments. Overall, this project contributes to the advancement of predictive analytics in the financial lending sector, enabling efficiency and equity in loan approvals.
