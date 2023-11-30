# &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;E-commerce Customer Churn

# # Business Problem
**Context:**<br>
&emsp;&emsp;&emsp;Referring to the BRI website, `Electronic commerce or e-commerce` is a buying and selling transaction process which in practice is carried out online via electronic media. According to Laudon & Laudon, e-commerce is a business-to-business transaction that occurs through an internet network intermediary. In the world of commerce, e-commerce offers many changes. The buying and selling process no longer requires face-to-face meetings like in conventional stores. Sellers and buyers only need to process transactions online. Currently the means of e-commerce are not only through telephone and television, but now more often use the internet. With the existence of e-commerce, of course it becomes easier for customers to carry out shopping transactions so that customers also have the possibility of being able to shop more, which also provides more benefits for e-commerce.

&emsp;&emsp;&emsp;From this explanation, it can be seen that customers have a very important role in e-commerce activities, so e-commerce needs to think about how to ensure customers have `a satisfying shopping experience`. If customers feel they are not getting this experience, these customers have the potential to leave the business. Of course, `there are other factors` that can make customers abandon e-commerce. Therefore, e-commerce owners need to analyze and predict whether customers will stay or leave the business or what we can call the customer churn rate.

&emsp;&emsp;&emsp;`Customer churn`, or `attrition`, is the rate at which clients choose not to purchase more (or no longer use) a company's products or services. Customer churn occurs when customers `stop consuming` a brand or product. They stop and no longer buy or use the products and services. Therefore, any business must pay full attention to this one measure. This measure is important because it can affect the company's profitability and growth. Losing loyal customers is certainly a source of sadness for your product. Not only that, you also lose a steady source of income and have to `incur greater costs` to acquire new customers who can replace the lost customers. In fact, acquiring new customers is 5 times more expensive than retaining existing customers, and making new customers loyal is also 16 times more expensive. So, a strategy is needed to stop customer churn or lose customers and retain the customers you already have, because they are the main source of business revenue.

&emsp;&emsp;&emsp;In this project, it is assumed that the client is an online retail company (E-commerce) who wants to know which customers will churn. By using predictions made from machine learning, it is hoped that clients can classify which customers will churn and which customers will not so that they can approach customers who are predicted to churn to offer several promotions in order to retain these customers to continue shopping at e-commerce.

&emsp;&emsp;&emsp;From several references that I have read, predicting customer churn can be done by looking at customer churn patterns, namely simply dividing the number of customers lost by the total customers of your business over a certain period of time. Then multiply the result by 100% to form a percentage value. Divide the number of lost customers by the total number of original customers to see the percentage. The following is the Churn Rate formula:

`Churn Rate = (Number of lost customers/total number of customers from the beginning of the period) x 100%`

&emsp;&emsp;&emsp;After getting the churn rate value, a churn rate is obtained where this value will be monitored over a period so that a trend pattern can be obtained which can provide insight into future churn rate predictions.

&emsp;&emsp;&emsp;However, this method is `only used to predict the churn rate`, while the way to `personally predict whether a customer will churn or not is still lacking`. This is why machine learning is needed which can be used to predict whether a customer will churn or not so that e-commerce can take preventive action so that the customer does not churn.

&emsp;&emsp;&emsp;After obtaining predictions about customers who might churn, the e-commerce party can provide action in the form of notifications or promo e-mails so that customers will be interested in shopping at the e-commerce site again.

`Target :`
- `0 :` Customer who will not churn
- `1 :` Customer who will churn

**Metric Evaluation:**

![Alt text](https://cdn-images-1.medium.com/max/800/1*_JY_jxfndH8oBI3clamifA.png "Confusion Matrix")

Type 1 error: `False Positive (FP)`<br>
Consequences: Potential reduction in profits obtained from stock sales due to promotional target errors

Type 2 error: `False Negative (FN)`<br>
Consequences: Customers stop buying stock items in e-commerce

In the customer churn problem, `both consequences are important`. `Precision is important` because it measures the model's accuracy in identifying customers who are likely to churn. High precision means the model correctly identifies customers who are likely to churn, which is important for taking proactive action to prevent churn. `Recall is also important` because it measures the model's ability to identify all customers who are likely to churn. High recall means the model correctly identified all customers who are likely to churn, which is important to ensure that no customers who are likely to churn are missed. 

Therefore, both precision and recall are important in the churn customer problem in machine learning. So the appropriate evaluation metric to use in this case is the `F-score` because it can ensure that the model we choose has balanced recall and precision values. Based on the consequences, what we will do as much as possible is to create a model that can `minimize customer churn` from e-commerce, but `does not consider promotional target errors` because it is considered `a strategy to attract new customers or increase sales`. So we want to minimize `False Negatives` as much as possible. So the main evaluation score metric used in this project will be the `F2-score` because it `prioritizes recall over precision`, making it more appropriate for situations where minimizing false negatives is the main concern.

# # Dataset Understanding:
| Attribute | Data Type | Description |
| --- | --- | --- |
| Tenure | `float64` | Tenure of a customer in the company |
| WarehouseToHome | `float64` | Distance between the warehouse to the customer’s home |
| NumberOfDeviceRegistered | `int64` | Total number of devices is registered on a particular customer |
| PreferedOrderCat | `object`  | Preferred order category of a customer in the last month |
| SatisfactionScore | `int64`   | Satisfactory score of a customer on service |
| MaritalStatus | `object`  | Marital status of a customer |
| NumberOfAddress | `int64`   | Total number of added on a particular customer |
| Complaint | `int64`  | Any complaint has been raised in the last month |
| DaySinceLastOrder | `float64` | Day since last order by customer |
| CashbackAmount | `float64` | Average cashback in last month |
| Churn | `int64` | Churn flag |

# # Conclusion & Recomendation

## Model Evaluation

![image](https://github.com/VeeA1/Purwadhika-Capstone-Project-3-Machine-Learning/assets/95554664/7aff8a35-30d0-4ced-a710-5c74e8ed22f5)

Based on the results of the classification report from the final model that has been implemented, it can be seen that using this model can predict `87%` of customers who will not churn and `84%` of customers who will churn. (looking at the recall). Therefore, there is still a possibility that customers will churn but are predicted by machine learning as not churning, namely around `13%`. This can be seen from the confusion matrix which is depicted from the results of prediction testing on test data where there are still `17 customers` who are predicted not to churn but will actually churn. However, from a business perspective, the task is appropriate, where the machine learning model formed will minimize the total of False Negatives, where the False Negative value is slightly smaller than the False Positive, namely `72 customers`. These 72 customers will later be considered as potential additional profits.

We can save the implemented model using the pickle library to be used as a prediction model in the future

## Feature Importance

![image](https://github.com/VeeA1/Purwadhika-Capstone-Project-3-Machine-Learning/assets/95554664/24408c6b-e698-4f95-8126-5e0c8f61a68e)

**Analysis:**

Looking at the feature engineering that has been carried out, there are a total of `13 variables` that are features as the main components in machine learning this time. From these 13 features, we can look for `feature importance` to find out `the relative importance` of each feature in the dataset when building a prediction model where the score is calculated using the model we previously determined, namely Random Forest.The following is an analysis of the search results for feature importance.
- From the bar plot that has been created, we get the order of feature importance from the machine learning component used, where the most important feature that determines whether a customer will churn is `Tenure`, followed by `CashBackAmount`, and other else.

- For `Tenure`, insight can be drawn where a customer's length of time using e-commerce services can influence whether the customer will churn or not

- For `CashbackAmount`, insight can be drawn where the amount of cashback received by a customer can influence whether the customer will churn or not

- To see positive or negative influences we can use `SHAP`

## Shap

![image](https://github.com/VeeA1/Purwadhika-Capstone-Project-3-Machine-Learning/assets/95554664/a54860e3-fe0c-4d6f-9806-b9bc2f51edd0)

`SHAP (SHapley Additive exPlanations)` is a method for explaining machine learning model predictions. SHAP is based on game theory and uses the concept of Shapley values to calculate the contribution of each feature to the prediction. SHAP values are a local measure of feature importance. That is, SHAP values only describe how the feature contributes to the prediction for one particular example. SHAP values can be positive or negative, depending on whether the feature increases or decreases the prediction.
By using shap, the following analysis can be presented from the display according to the plot analysis of several machine learning features.

- On tenure, if the customer's tenure in using e-commerce services is `longer`, machine learning will tend to predict that the customer `will not churn (0)`. On the other hand, if the customer's tenure in using e-commerce services is only `short`, machine learning will tend to predict customer `will churn (1)`

- On `Complain`, If a customer `ever files` a complaint, machine learning will tend to make predict that the customer `will churn (1)`. Conversely, if a customer `never files` a complaint, machine learning will tend to make predict that the customer `not churn (0)`. 

- On `CashbackAmount`, `the more cashback` a customer receives, the machine learning will tend to predict that the customer `will not churn (0)`. Conversely, if the customer receives `less cashback`, machine learning will tend to predict customer `will churn (1).`

- On `NumberOfAddress`, `the more address listed` by a customer, the machine learning will tend to predict that the customer `will churn (1)`. Conversely, `the less address listed` by a customer, machine learning will tend to predict customer `not churn (0).`

- On `DaySinceLastOrder`, `the longer period of last order` by a customer, the machine learning will tend to predict that the customer `will churn (1)`. Conversely, `the shorter period of last order` by a customer, machine learning will tend to predict customer `not churn (0).`

- On `MaritalStatus`, if the marital status of the customer is `single`, the machine learning will tend to predict that the customer `will churn (1)`. Conversely, if the marital status of the customer is `married`, the machine learning will tend to predict that the customer `not churn (0)`.

## Recomendation

Finally, there are several things that can be done to develop the project and model even better, including the following.

1. The features that used by machine learning can be `reduced` according to the `correlation value` of the feature with the target of machine learning to `reduce overfitting` produced by the model, where the features that are reduced can be features that have the `lowest correlation value`. Apart from that, you can also binning the `Tenure, WarehouseToHome, DaySinceLastOrder, and CashbackAmount` values into categorical form to avoid indications of model `underfitting`.

2. Experiment with the model again using a `different` `model` and `different` `sampling` where the parameters used are the `best parameters` that suit the business problem being worked on, namely customer churn
