# Banking-data-classification-model
Insights on Banking data for efficient marketing campaigns

**1. Problem Statement**

A banking dataset has been provided which contains insights for various marketing campaigns run for customers during a specific period. An analysis of the data must be done along with machine learning predictions, in order to provide actionable suggestions. These can help in efficient marketing campaigns resulting in deposit subscription by the customers.

**2. Project Objective**

The objective of the project is to perform data analysis of the given data and to derive useful insights. Further, a classification model can be optimised to predict the deposit subscription efficiently. The above can be performed using feature engineering and supervised machine learning algorithms. And hence, the success of future marketing campaigns can be predicted by the bank using the chosen model.

**3. Data Description** 

The banking dataset used is available as two subsets: train and test data. The 
number of rows in train data is 45211 and in the test data, it is 4521. The 
columns in the whole dataset are seventeen in number. The description of the
columns are as follows:

**Feature Name   -	Description**

_age_	-Age of the customer;
_job_ -	Profession of the customer;
_marital_ -	Marital status of the customer;
_education_ -	Educational qualification of the
customer;
_default_ -	Does the customer have credit in default?;
_balance_ -	Average yearly balance;
_housing_ -	Does the customer have a housing loan?;
_loan_ - Does the customer have a personal loan?;
_contact_ - Contact communication type of the 
customer;
_day_ - Last contact day of the month;
_month_ - Last contact month of the year;
_duration_ - Last contact duration in seconds;
_campaign_ - Number of contacts during campaign;
_pdays_ - Number of days since last contact;
_previous_ - Number of contacts before campaign;
_poutcome_ - Outcome of previous campaign;
_y_ - Has the customer subscribed for a deposit?

Here the y column which answers if the customer has subscribed for a deposit, is the target column or the dependent variable.

**4. Data Pre-processing Steps and Inspiration**
 
The training dataset was loaded as a dataframe using pandas. The number of null values were checked and were found to be none. Next, the outliers were identified but not removed as it impacted the unique values of the poutcome column.

Further, the values of certain features were modified to facilitate analysis. The y column values were converted from yes/no to 1/0 and stored as strings. The month column was converted into integer form.

In the exploratory data analysis phase, the age distribution was visualised as a histogram. A pie chart was used to visualise the unique jobs in the jobs column. Bar plots were used to illustrate the education and marital statuses of the customers. In addition, the poutcome was analysed and found to have high unknown outcomes.

In order to find the relevant features, a correlation map and Variance Inflation Factor (VIF) to detect multicollinearity were used. The age column was removed due to its high VIF since it has the potential to cause noise by its relationship with other features. Also, the day and month columns don’t make sense individually and hence, were not considered for further processing. Then, the same columns were removed in the test dataset too. Before using the algorithms, label encoding was performed for the features.

**5. Choosing the Algorithm for the Project** 

Since the dataset has an identifiable dependent variable, supervised machine learning algorithms can be used. I have used classification algorithms because the target column has two discrete values: Yes or No. The following algorithms were used: Logistic Regression, Decision Tree and Random Forest.

**6. Motivation and Reasons for Choosing the Algorithm** 

The Logistic Regression algorithm was chosen as it can predict a binary outcome occurring, which suits the case of the dependent variable here. Also, it is simple and very efficient. On the other hand, the Decision Tree algorithm can help identify the strategy that is most likely to reach a goal; like a marketing campaign that can lead to more customer deposits. Similarly, Random Forest algorithm with its multiple decision trees, can be used, with an added advantage of being suitable for large datasets.

**7. Assumptions**

The following assumptions were made in order to create the model for the project:

•	Since the age column has a high VIF, it can be removed as a feature for the model.

•	The day and month columns do not have an individual significance and can be removed. Instead, the pdays column with the number of days since last contact, can be considered as a feature.

•	Using all the other features in order would get a higher accuracy with the model.

**8. Model Evaluation and Technique**

The model evaluation methods used were: confusion matrix, accuracy score, precision, recall and f1 score. For the Logistic Regression algorithm, the accuracy was 88.3% and the f1 score was 0.192. The Decision Tree algorithm had a higher accuracy of 86% and a f1 score of 0.397. But the Random Forest algorithm with 1000 estimators gave the highest accuracy of 90.8% and an f1 score of 0.443.

Further, the best hyperparameters for the Random Forest were found using Random Search. But on employing these hyperparameters, the algorithm had zero precision and recall. Hence, the most effective model would be of Random Forest with n_estimators=1000.

**9. Inferences from the Project**

The overall inferences from the data are as follows:

•	Most customers belong to the age bracket of 35-40, with the average age being 40.9. The maximum and minimum ages are 18 and 95, respectively.

•	Blue-collar jobs are the most common among the customers with a count of 9732. Very few have unknown jobs.

•	Most of the bank’s customers are married and very few of them have ‘divorced’ as their marital status.

•	Majority of the customers have finished their secondary education.

•	The average contact duration of the past campaign is 258 seconds.

•	The mean number of days since last contact is 40 and the number of contacts before the current campaign has a low average of 0.58.

•	Finally, the outcomes of previous campaigns are mostly unknown.

The best performing Random Forest model has a precision of 72.8% and hence can give relevant results for customers subscribing for a deposit, among the predictions. But a recall score of 31.9% means that not all relevant outcomes (i.e. a customer subscribing for a deposit) can be predicted by the model.

**10. Future Possibilities**

The future possibilities for this project includes: using day and month columns as relevant features, provided the date of current campaign is known. A model can be optimized for prediction of customers with specific jobs or ones in specific age brackets. This can help in getting accurate predictions and choosing the efficient marketing campaign.

**11. Conclusion**

This project has succeeded in identifying the distribution of relevant features which have been visualised. Also, the major objective of finding a high performing model has been achieved, with the Random Forest model having a 90% accuracy and an appreciable f1 score.

**12. References**

_Supervised Machine Learning_: https://www.ibm.com/in-en/topics/supervised-learning

_Supervised classification models_: https://builtin.com/data-science/supervised-machine-learning-classification

_Variance Inflation Factor_: https://online.stat.psu.edu/stat462/node/180/

_Precision and Recall_: https://builtin.com/data-science/precision-and-recall



