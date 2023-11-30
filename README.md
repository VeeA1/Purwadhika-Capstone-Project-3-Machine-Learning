<p style="text-align: center;"> <font size=16>E-commerce Customer Churn</font></p>
----

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
