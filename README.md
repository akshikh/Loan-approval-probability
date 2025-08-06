# Loan-approval-probability

Objective- Create a model that would take variables and predict if a loan is approved = 1 or not apporved = 0 

Result- After analysis we found that- Random forest did the best amongst all. 

<img width="542" height="508" alt="image" src="https://github.com/user-attachments/assets/6fad9b39-e9d8-4c3d-ab00-cbba7310eaa3" />

For the model to not be overfit- Mean CV accuracy < Test accuracy 
we found that here 0.9959 < 0.9988
So model is not over fitting 

Then Precision and Recall is 1 which is perfect and F1 score is also 1. We only got 1 False Negative which is really good accuracy rate. 

_____ Step by step explanation of steps ________

Variables used are-
1. Number of dependents
2. Education
3. Self_employed
4. Income in annum
5. Loan_amount
6. Loan_term
7. Credit_Score
8. Residential_assets_value
9. commercial_assets_value
10. luxury_assets_value	bank_asset_value

Step 1- Data cleaning and processing- 

1. Descriptive Analysis- Started with looking at desciption of the data which included looking at Mean, standard deviation, min and max values for each variable. 

Found that- Income, loan, asset values are very large in comparision to others
Residential asset value minimum is in negative which is suspecious : -100000.00

2. Balance of data- Looked at percentages of different categorical variables. For instance Educated had Graduate (50.22%) and Not Graduate (49.78%)- so balanced dataset
Similarly, Loan status has Approved (62.22) and Rejected (37.78) which was  good enough.

3. Exploratory data Analysis- Wherein I looked at the distributions of different variables to check the distributions.

<img width="547" height="360" alt="image" src="https://github.com/user-attachments/assets/8a68d5ed-08ee-4372-abe4-c8a69759ac07" />

Some of the variables were right skewed which means while most of the values are within the range, some of them are way higher than others likely causing the longer tail. 

Also did Box plots to look at outliers in the dataset. And found outliers which were scaled in later steps. 

<img width="507" height="328" alt="image" src="https://github.com/user-attachments/assets/16260797-9b4e-40f9-95c4-e7a2f0510026" />

Step 2- Data pre processing and feature engineering 

In this step I conducted correlation heatmap to check how each variable is related to each other. Before this I encoded the categorical variables using Label encoders to convert them to quantitative values. 

The first correlation heatmap showed- 
<img width="538" height="343" alt="image" src="https://github.com/user-attachments/assets/41ee6e12-4044-47a5-977f-ce53131f7ec7" />

Here we can see very high correlation between income and loan amount. So instead of keeping both the features, we did feature engineering where we created debt to income ratio = Loan amount / total income

After this when correlation heatmap was plotted we saw significant change- 

<img width="545" height="345" alt="image" src="https://github.com/user-attachments/assets/1276b665-56d9-41aa-a43a-77ea33175986" />

Step - 3 Train Multiple models and evaluate

Once we were done with data cleaning and feature engineering- we started with creating the model. The 4 models that we tested were
1. Logistic Regression (Last)

<img width="506" height="486" alt="image" src="https://github.com/user-attachments/assets/300f52f1-f127-4432-8704-322ffcd108f2" />

2. Decision Tree (Second Best)
   <img width="555" height="493" alt="image" src="https://github.com/user-attachments/assets/11d7abfd-9810-4aa7-bbd2-bf44411eab5b" />

3. Random Forest Classifier (Best)

<img width="530" height="506" alt="image" src="https://github.com/user-attachments/assets/5eb73d2b-5241-4b1d-8c3a-efded72e8546" />

4. XG Boost (3 place)
<img width="530" height="500" alt="image" src="https://github.com/user-attachments/assets/2e7df468-68e2-4e8b-97dc-39d91ebb6f6e" />

## Which model performed better?


So we started with logistic regression which showed the lowest results with 89% accuracy

Decision tree was second last with 99.7% accuracy

Surprisingly XGBoost didnt perform that well with 3 false positives and 3 false negatives.

The best model here was Random Forest which 99.8% accuracy with precision score of 1 showing hiest precision and just one false negative.


### Feature Importance 

<img width="537" height="304" alt="image" src="https://github.com/user-attachments/assets/cb664037-6ae9-4e4b-a4cd-479679d3a12d" />






