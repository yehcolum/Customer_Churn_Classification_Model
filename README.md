# Customer-Churn-Classification-Model1
# Overview

Are there any predictable patterns that determine churn for the Telecom Company? 

This analysis seeks to classify customers  who leave the service (churn) and determine which levers can be pulled to increase customer retention.

# Business Problem
Customers who leave Telecom's service quickly result in money lost on the customer acquisition and other related costs. This analysis will classify customers who churn and interpret what leads to their departure.

# The Data

Telecom data encompassing 20 variables ranging from state to area code. Ommitted irrelevant variables like phone number.
<img width="212" alt="Screen Shot 2022-07-17 at 11 07 10 AM" src="https://user-images.githubusercontent.com/87211473/179421751-c41bbf38-47a2-4f7b-af4e-31728b468b93.png">

# Modeling and Results

Baseling modeling included Logistic Regression, Decision Tree Classifier, and XGBoost Classifier. XGBoost proved to be the most promising model under the desired metrics of recall and accuracy.

<img width="383" alt="Screen Shot 2022-07-17 at 12 29 51 PM" src="https://user-images.githubusercontent.com/87211473/179421832-c3c77028-4183-4893-98d2-c124db27db82.png">

# Model Refinement

Next step, refining the model through hyperparameter tuning. I used a gridsearch to explore the best parameters for each model. Again, XGBoost produced the best results. The best parameters produced a recall of 0.936 and an accuracy of 0.62.

<img width="392" alt="Screen Shot 2022-07-17 at 12 32 19 PM" src="https://user-images.githubusercontent.com/87211473/179421915-ddea1562-e3f0-4429-876d-b2c00f82daec.png">

Overall, xgboost produced the best recall compared to the other models, missing only 8 churners (false negatives). Even though the xgboost model produced significantly more false positives, this error is not detrimental to the business. Misclassifying non-churners is not a material issue, while misclassifying churners materially hurts the business if those customers leave the service.
Plotting feature importances of our refined model revealed the following:

<img width="879" alt="Screen Shot 2022-07-17 at 11 52 20 AM" src="https://user-images.githubusercontent.com/87211473/179421977-2bd1d89e-c901-4a42-a6be-526a63966659.png">

# Business Recommendations

Our best performing model, XGBoost, identified the following features as most important to predicting churn:

1. Not having an international plan
2. Number of customer service calls
3. Being a MA customer

In accordance with these features I recommend the following business recommendations:

A tailored, automated email flow addressing common pain points to customers with more than 2 customer service calls. The goal of this email campaign is to assuage the most common concerns that customers have so that the likelihood of churn decreases.

A comprehensive investigation of the MA market. First, customers in MA should be sent a survey assessing their level of satisfaction with the service, as well as assessing their pain points and complaints. These survey results should be analyzed to find why MA customers are more likely to churn.

A renewed focus on customers in the international plan segment. Customers with the international plan are less likely to churn. Therefore, I recommend targeting this customer segment with a new marketing campaign designed to bring these higher life time value customers into our network. This should help the company drive revenue growth with better quality customers who spend more and churn less.

# Limitations
Our final algorithm optimized for recall produces false positives at a higher rate than the baseline. This is not a problem for meeting our business goals. However, the false positives may produce inefficiencies at scale, since the model may produce many false positives when used on large data sets.

Problems may include wasted marketing communications and customer annoyance.








