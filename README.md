# Credit_Card_Churn_Analytic

Customer retention is cruicial in different businesses as aquiring new customers is often more costly than keeping existing customers. In this project, the aim is to predict if existing customers of a bank will leave its credit card services. Before this a customer leave, the bank can take proactive action so that the customers are continue the credit card service with the bank.

In this project a prediction model is developed to predict if a customer will churn based on customers' age, gender, tenure etc (refer to the following sections for more information). 

## Code and Resources Used

**Python Version:** 3.7 <br>
**Packages:** numpy, pandas, seaborn, matplotlib, sklearn <br>
**IDE:** Google Colab <br>
**Dashboard Software:** Google Data Studio <br>
**Dataset:** https://www.kaggle.com/sakshigoyal7/credit-card-customers 

## Data Gathering

The dataset used in this project can be downloaded from Kaggle (link as shown above). It is about bank credit card customer churn, focusing on customer retention program to identify/predict if an existing customer will churn so that the bank can take necessary actions to retain the customer to continue with the credit card service. This dataset consist of 10127 rows and 14 features. The information of the dataset includes: <br>
* Customers, existing and churned
* Demograhpic info - age, marital status, number of dependent, education level and income
* Credit card account information - (transcation count, transaction amount, revolving balance) in the past 12 months, tenure and credit limit

One thing to take note is that the dataset is with imbalance sample where 8700 records are existing customers and 1627 records are churned customers. 

## Data Cleaning

Based on the given dataset, it is ready to use for analysis. 

## EDA

#### Heatmap of correlation between the features 
![](/images/1.BCA_heatmap.png)
<br>Based on the heatmap, it can be seen that the correlation between Customer_Status_code with Credit_Limit Total_Trans_Amt (RM), Total_Trans_Ct and Total_Revolving_Bal (RM) are with negative assosciation (<0). For Total_Revolving_Bal (RM) and Total_Trans_Ct, the relationships with Customer_Status_code are considered high (the lower the values, the higher the possibility a customer will churn). <br> As for the rest of the variables, there are with positive association with Customer_Status_Code. However, the values are closer to zero, which means there is no linear relationship with Customer_Status_code.   

#### Dataset Information 
![](/images/2.BCA_cust_info.png) 

<br> Based on the findings, it can be seen that 
* there is total of 10127 records
* number of existing customer (8500, 83.93%) is higher than attrited customer (1627, 16.07%)
* number of female customer (5358) is ihigher than male (4769)
* 2732 customers are with 3 dependents, followed by 2655 customers having 2 and 1838 customers with 1 dependent. 1574 customers with 4 dependents, 904 customers without dependent and 424 customers with 5 dependents. The range of dependent is 0 to 5
* there are 4 marital status which are Married (4687), Single (3943), Unknown (749) and Divorced (748) 
* there are 4 card categories (4 credit card products), Blue, Gold, Silver and Platinium. 9436 (93.18%) customers are with Blue card, followed by 555 (5.48%)customers with Silver and 116 (1.15%) customers with Gold cards. Platinium card holder is the least, which is 20 (0.18%) customers. Blue card is the main income stream as compared to the rest of the cards.

#### Annual Income Distribution
![](/images/3.BCA_income.png) 
<br> There are 3561 customers with < RM40K annual income. This is followed by 1790 customers with RM40 - RM60k, 1535 customers with RM80 - RM120k, 1402 customers with RM60k - RM80k and the least, 727 customers with > RM120k annual incomes. There are 1112 customers with unknown annual income (may be dependent of a principal card holder). 

#### Annual Income Distribution
![](/images/4.BCA_education.png)
<br> 3128 customers are with Bachelor qualification, 2013 customers with High School qualification, 1519 uneducated, 1013 with college qalification, 516 with post-graduate and 451 with Doctorate qualification. 

#### Annual Income Distribution
![](/images/5.BCA_tenure.png)
<br> Tenure of 36 months is extremely high as compared with the rest (2463 customers). This may due to the bank has lauched a new credit card or offering attractive free gift upon credit card application at the point of time. <br> Other than that, tenures of the customers are spreaded in between 13 to 56 months and mostly with 24 to 48 months of tenures.

#### Annual Income Distribution
![](/images/6.BCA_credit_limit.png)
<br> Based on the graph, it can be seen that the higher the credit limit, the lower the number of customers. However, there is a high number of customer with about RM34000 credit limit.
