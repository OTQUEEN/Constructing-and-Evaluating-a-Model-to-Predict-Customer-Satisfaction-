# Constructing-and-Evaluating-a-Model-to-Predict-Customer-Satisfaction-
Machine Learning Modeling - A Decision Tree Model with tunned hyperparameter 

## Introduction

The data for this project includes survey responses from 129,880 customers. It includes data points such as class, flight distance, and in-flight entertainment, among others. In a previous activity, you utilized a binomial logistic regression model to help the airline better understand this data. In this activity, your goal will be to utilize a decision tree model to predict whether or not a customer will be satisfied with their flight experience. 

## Business objective
**1.** Predicting whether a future customer would be satisfied with their services given previous customer feedback about their flight experience. 

**2.** Construct and evaluate a model to determine which features are most important to customer satisfaction.

## Scope of work

1.  Importing packages and loading data
2.  Exploring the data and completing the cleaning process
3.  Building a model to determine which features are most important to customer satisfaction:
    * Knowing that Decision trees require no assumptions regarding the distribution of underlying data and don't require scaling of features though it's susceptible to overfitting.
     In this work, I would like to use Decision Tree Model to determine the features of most important for customer satisfaction.
4.  Tuning hyperparameters using `GridSearchCV`. Using hyperparameter tuning and grid search to ensure this prevent overfitting in the model.
5.  Evaluating a decision tree model using a confusion matrix and various other plots

![image](https://github.com/user-attachments/assets/cd93d51f-499a-4db8-934a-3de96f9a7eb7)

![image](https://github.com/user-attachments/assets/6a8f2a20-abb8-4cda-a299-78175054c818)

## Data exploration, data cleaning, and model preparation

In this section, I will be preparing the data to be suitable for decision tree classifiers. This includes: 

*   Exploring the data
*   Checking for missing values
*   Encoding the data
*   Renaming a column
*   Creating the training and testing data

### Explore the data

Checking the data type of each column. **Not forgetting that decision trees expect numeric data.** 

![image](https://github.com/user-attachments/assets/7604c3ea-f56f-4558-9bae-40d50757ed42)

The count shows that there are 71087 satisfied customers and 58793 dissatisfied customers. Indicating that 54.7 percent (71087/129880) of customers were satisfied. 
This value can be compared during the decision tree's model on the matrix accuracy.

### Check for missing values
Having in mind that, the sklearn decision tree implementation does not support missing values. Hence checking for missing values in the rows of the data is important.

![image](https://github.com/user-attachments/assets/c5d3cd71-9db4-48a4-b2a5-7fe6755f04a5)

There are 129880 rows and 22 columns as features in the dataset. Since the 393 missing rows represent a small percentage of the entire dataset,
would like to drop these rows with missing values and assign the DataFrame a new name.

![image](https://github.com/user-attachments/assets/68962223-8c82-44c6-948a-8dcfa0f0778a)
![image](https://github.com/user-attachments/assets/b70dbf28-6ef5-4eb1-8ed1-c443ab0af951)
![image](https://github.com/user-attachments/assets/117eb88f-0186-4d9d-a7de-9f772cf3415e)
![image](https://github.com/user-attachments/assets/153e71a9-8e7a-43e0-94e9-96c567c39fd0)

From the confusion matrix, there are a high proportion of true positives and true negatives, where the matrix accurately predicted that the customer would be satisfied or dissatified, respectively.

The matrix also had a relatively low number of false positives and false negatives. Indicating that, the matrix innacurately predicted that the customer would be satisfied or dissatified, respectively.

![image](https://github.com/user-attachments/assets/dfa6051e-73ea-4ddd-84f5-f141781238b0)
![image](https://github.com/user-attachments/assets/8181bef0-6f8b-4958-a3b3-64081a82a4db)

### Hyperparameter tuning

In a decision tree model, knowing that the tree has a potential of growing further without knowing the limit. 
An intruduction of tuning the model will help increase the model performance by determing the best values for hyperparameters `max_depth` and `min_samples_leaf` using grid search and cross validation will help determine how far the tree should grow.
![image](https://github.com/user-attachments/assets/6a11f7d5-81e3-4198-bec6-993027e77a56)

### Determine the "best" decision tree model's accuracy, precision, recall, and F1 score

Print out the decision tree model's accuracy, precision, recall, and F1 score. This task can be done in a number of ways. 
![image](https://github.com/user-attachments/assets/1a6d8153-7d15-421a-bfc8-2575c46b2ae2)

The F1 score for the decision tree that was not hyperparameter tuned is 0.940940 whiles the F1 score for the hyperparameter-tuned decision tree is 0.945422. Though ensuring that overfitting doesn't occur is necessary for some models, however hyperparameter tunning didn't make a meaningful difference in improving this model.

![image](https://github.com/user-attachments/assets/3d8de066-bebb-4ba8-bc13-3f287a2f3335)

## Conclusion and Recommendation
**In summary:**
*   The decision tree model accurately predicted satisfaction of over 94 percent of the time.  
* Precision score shows that the model predicted over 95% positives that are truly positive. This indicates that out of the total number of customers that claimed to be satisfied, over 95% are trualy satisfied.  

* The Recall score also shows that the actual positives that the model correctly identified is over 93%. This score helps the Airline not waste their resources trying to improve the customer experience of an already satisfied customer.
*   The confusion matrix is also useful as it shows a similar number of true positives and true negatives indicating a higher probabaility of the model predicting accurately. 
*   The visualization of the decision tree and the feature importance graph both suggest that `'Inflight entertainment'`, `'Seat comfort'`, and `'Ease of Online booking'` are the most important features in the model.

**Recommendation:**
*  Customer satisfaction is highly tied to `'Inflight entertainment'`, `'Seat comfort'`, and `'Ease of Online booking'`. Improving these experiences should lead to better customer satisfaction. 
*  The success of the model suggests that the airline should invest more effort into model building and model understanding since this model semed to be very good at predicting customer satisfaction. 







