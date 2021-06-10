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

#### Tenure with the Bank (Monthly)
![](/images/5.BCA_tenure.png)
<br> Tenure of 36 months is extremely high as compared with the rest (2463 customers). This may due to the bank has lauched a new credit card or offering attractive free gift upon credit card application at the point of time. <br> Other than that, tenures of the customers are spreaded in between 13 to 56 months and mostly with 24 to 48 months of tenures.

#### Credit Limit Distribution
![](/images/6.BCA_credit_limit.png)
<br> Based on the graph, it can be seen that the higher the credit limit, the lower the number of customers. However, there is a high number of customer with about RM34000 credit limit.

#### Total Revolving Balance (Past 12 Months) Distribution
![](/images/7.BCA_revol_bal.png)
<br> 

#### Total Transcation Amount (Past 12 Months) Distribution
![](/images/8.BCA_tran_amt.png)
<br> Based on the graph, it can be seen that most of the transcations are in between RM500 to RM5000. There are also two groups of customers with transcation amount in between RM7000 to RM10000 and RM12500 to RM117500.

#### Total Transcation Count (Past 12 Months) Distribution
![](/images/9.BCA_tran_cnt.png)
<br> Based on the finding, it can be seen that most of the customers are making 20 to 120 transactions per year. 

#### Existing and Attrited Customer vs Gender
![](/images/10.BCA_ex_vs_churn.png)
<br> Female tend to churn as compared to male customer. 960 female, 57.16% ahd 697 male, 42.84% had churned. 

#### Existing and Attrited Customer vs Number of Dependent
![](/images/11.BCA_ex_vs_churn_dependent.png)
<br> 

#### Existing and Attrited Customer vs Education Level
![](/images/12.BCA_ex_vs_churn_edu.png)
<br> Based on the graph,
* Customer with Graduate qualification is with the highest churn rate, 29.93%
* Doctorate qualification is with the lowest churn rate, 5.84%

#### Existing and Attrited Customer vs Marital Status
![](/images/13.BCA_ex_vs_churn_marital.png)
<br> Marital status of Married and Single are more likely to churn (709, 43.58% and 668, 41.06%, respectively), as compared with marital status of unknown (129, 7.93%) or divorced (121, 7.44%). 

#### Existing and Attrited Customer vs Income Category
![](/images/14.BCA_ex_vs_churn_income.png)
<br> Based on the graph,
* Annual income that is less than RM40k is with the highest churn rate, 37.61%, 612 customers
* 7.74%, 126 of the churners are with at least RM120k annual income.
* The higher the annual income, the less likely a customer will churn.

#### Existing and Attrited Customer vs Card Category
![](/images/15.BCA_ex_vs_churn_cardcat.png)
<br> Churned customers mainly from Blue card holder. May look into the campaign that can retain this group of customer. <br>
93.36% with Blue card, 5.04% with Silver card, 1.29% with Gold card and 0.31% with Platinum card.

#### Distribution of Customer\'s Credit Limit for Different Card Types
![](/images/16.BCA_ex_vs_churn_card_details.png)
<br> Based on the graphs, it can be seen that Blue card holders with credit limit of less than RM5000 are more likely to churn. <br> Besides, customers are more likely to churn with credit limit in between RM30000 to RM35000, regardless of the card types.

#### Distribution of Customer\'s Total Revolving Balance (RM) in the Past 12 Months
![](/images/17.BCA_ex_vs_churn_revol.png)
<br> Based on the graph, it is found that revolving balance of less than RM500 and above RM2300 are likely to churn. <br> For those with revolving balance less than RM500, the churn may due to they would like to go for other bank with better benefit. As for revolving balance of more than RM2300, this may due to other bank is providing a lower interest rate for outstanding balance transfer benefit.

#### Distribution of Customer\'s Total Transaction Amount (RM) in the Past 12 Months
![](/images/18.BCA_ex_vs_churn_tranAmt.png)
<br> Based on the graph, the lower the total transcation amount pear year, the more likely a customer will churn. Customers with RM2500 (or less) total transaction amount are more likely to churn. Most of the customers are with RM5000 (or less) total transaction amount per year.

#### Distribution of Customer\'s Total Transaction Count in the Past 12 Months
![](/images/19.BCA_ex_vs_churn_tranCnt.png)
<br> Based on the graph, it can be seen that customers with a lower transcation count (80 transcations) in the past 12 months are more likely to churn. 

#### Distribution of Customer\'s Credit Limit
![](/images/20.BCA_ex_vs_creditlim.png)
<br> Based on the graph, it can be seen that customers with credit limit that are less than RM10000 are more likely to churn. The number of churn customers are higher if the credit limit is RM5000 and below. <br> Besides, there are also a group of customers with credit limit in between RM30000 to RM35000 have churned.

#### Distribution of Customer\'s Age
![](/images/21.BCA_ex_vs_age.png)
<br> Bsaed on the finding, it can be seen that customers with the ages of 35 to 60 are tend to churn. Less churner before age of 35 may due to the customers are still new and would like to stay with the bank for some period to enjoy the privillage. For the age after 60, there are also less churner as the customers may face difficulties in applying new credit card with other bank. 

#### Distribution of Customer\'s Tenure in Monthly Basis
![](/images/22.BCA_ex_vs_tenure.png)
<br> As for the tenure, there is a lot of customers with tenure of 36 months. This may due to the bank was offering a good promotion/benefit at the point of time of application. Also, the number of churners with tenure of 36 months are also high. Based on the finding, it shows that most of the churned customers are with RM5000 (or less) credit limit. 

#### Distribution of Customer\'s Credit Limit With 36 Months Tenure
![](/images/23.BCA_ex_vs_creditlim_36tenure.png)
<br> 

#### Distribution of Customer\'s Tenure in Years
![](/images/24.BCA_ex_vs_tenureYear.png)
<br> Based on the graphs, it can be seen that 72.77% of the churners are with tenure of 3 years, followed by 28.83% with 2 years tenure, 8.48% with 4 years tenures and 6.02% with 1 year tenure. <br> Besides, it is suprise that tenure month of 36 is with the highest number of customer. This may due to the bank provides attractive promotion of benefits to the applicants who applied to the bank at the point of time.

#### Total Transaction Amount vs Total Transaction Count
![](/images/25.BCA_tranAnt_vs_transCnt.png)
<br> Based on the graph, it further supports earlier finding, where the lower transaction count and total transaction amount per year the higher the chance a customer will churn.

#### Distribution of Total Transaction Count (pass 12 months) based on Number of Dependent
![](/images/26.BCA_tranCnt_vs_dependent.png)

#### Distribution of Total Transaction Amount (pass 12 months) based on Number of Dependent
![](/images/27.BCA_tranAmt_vs_dependent.png)
<br> Based on the findings, it can be seen that customers with 2-3 dependents are making higher transcation as compared to 0-1 and 4-5 dependents. However, the customers with 100 transcation counts (or less than RM11,000 total transaction amount) or lesser are tend to churn, regardless of the number of dependents. 

#### Distribution of Credit Limit based on Gender
![](/images/28.BCA_limit_vs_gender.png)
<br> Based on the finding, it can be seen that the churn of a customer does not affected by the credit limit and the gender. However, female customers are with a lower credit limit as compared with male customers.

## Model Building

Prior to the model building, the data that is with non numeric type (Customer_Status) has to be converted to numeric value. **LabelEncoder** from **sklearn.preprocesing** is used to accomplish the conversion task. Besides that, **MinMaxScaler** from **sklearn.preprocesing** is also used to scale the values of Credit_Limit, Total_Revolving_Bal (RM), Total_Trans_Amt (RM) and Total_Trans_Ct into range of 0 to 1. Reason being this feature is measured at different scale and do not contribute equally in model training and may ended with creating a bias. <br> 

**train_test_split** from **sklearn.model_selection** is also used to separat the dataset into training and testing set of data. In this project, 80% of the dataset is used as training set and the remaining 20% is used as testing set. <br>
Three models have been selected: <br>
* LogisticRegression
* RandomForestClassifier
* SVC
* KNeighborsClassifier  

Also, we will first develop a machine learning model by using the imbalace data. Results generated will be observed. Then, another model will be developed and trained by using balanced data that treated by Under-Sampling, Random-Over Sampling and SMOTE methods.

## Performane Evaluation

#### Machine Learning Models with Imbalance Data Sample 
Performance of the model as follows: <br>
* LogisticRegression - 86.36%
* **RandomForestClassifier - 92.53%**
* SVC - 92.43%
* KNeighborsClassifier - 83.16%

![](/images/29.model_performance_basic.png)

Based on the result, RandomForestClassifier is able to produce the best accuracy score, which is 92.53%. However, the value for the recall and R1 are extremely low (for Logistic Regression (less than 40%) and KNeighborsClassifier (less than 10%)). 

![](/images/33.LR_report.png)
![](/images/34.RF_report.png)
![](/images/35.SVC_report.png)
![](/images/36.kNeigh_report.png)

#### Machine Learning Models with Synthetic Minority Oversampling Technique (SMOTE) in Treating Imbalance Data Sample

Performance of the model as follows: <br>
* LogisticRegression - 81.82%
* **RandomForestClassifier - 91.70%**
* SVC - 91.49%
* KNeighborsClassifier - 63.91%

![](/images/31.model_performance_SMOTE.png)

Based on the results, Random Forest classifier is the model that able to provide the best accuracy score, which is 91.70%.

![](/images/41.LR_report_us_smote.png)
![](/images/42.RF_report_smote.png)
![](/images/43.SVC_report_smote.png)
![](/images/44.kNeigh_report_smote.PNG)

Based on the results produced by the 4 models after applying SMOTE to the imbalance data sample, it can be seen that there is a slight decreaes in term of the accuracy (all still with at least 80% accuracy except for KNeighborClassifier - 63.91%). However, all the recall and f1-score are with at least 80% in predecting if a customer will continue or cancel the credit card service, except for KNeighborClassifier model. 

In this project, accuracy and recall are both important. With low recall value, high False Negative prediction, i.e, predicted a customer that will leave as a loyal customer, the conseqence can be very bad to the bank as higher cost is needed to acquire new customer than maintaining existing customer. 

Hence, treating imbalance data sample is important. In this case, **RandomForestClassifier model** gives the best performance, where all the precision, recall and f1-score are with at least 90%. 
