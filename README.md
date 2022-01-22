<h1><center>«Portfolio-Exam Part II» </center></h1>
<h2><center>MADS-ML </center></h2>
<h3><center>Author: Tom Wüsten </center></h3>



### 1. Introduction
This paper deals with the topic of marketing campaigns in the banking sector. It specifically examines a Portuguese bank whose aim is to sell a product over the phone. This product is a term deposit (deposit in a financial institution with a specific maturity date). The aim of this work is to create a machine learning model that predict the success of a subscriben for a term deposit. The first step in creating a machine learning model is to analyse the data and do a data exploration. The data exploration investigated whether certain age groups, jobs or the number of calls are conspicuously concluding a term deposit. In order to find the best possible machine learning algorithm, different algorithms are compared with each other.

### 2. Dataset Licence
CC BY 4.0 <br>

### 3. Dataset Information:

There are several datasets for this marketing campaign of the bank. I choosed the dataset bank-additional.csv because it has only 10% of the dataset bank-additional-full.csv. The reason is to keep the run time of the notebook low. The reduced dataset contains 4119 instances with 21 attributes, where each instance describes a phone call between a bank employee and a bank customer.
All following information about the attributes are copied from uci machine learning repository. [[1]](#100)<br>
#### 3.1. Attribute Information
1 - age (numeric)<br>
2 - job : type of job (categorical: 'admin.','blue-collar','entrepreneur','housemaid','management','retired','self-employed','services','student','technician','unemployed','unknown')<br>
3 - marital : marital status (categorical: 'divorced','married','single','unknown'; note: 'divorced' means divorced or widowed)<br>
4 - education (categorical: 'basic.4y','basic.6y','basic.9y','high.school','illiterate','professional.course','university.degree','unknown')<br>
5 - default: has credit in default? (categorical: 'no','yes','unknown')<br>
6 - housing: has housing loan? (categorical: 'no','yes','unknown')<br>
7 - loan: has personal loan? (categorical: 'no','yes','unknown')<br>
8 - contact: contact communication type (categorical: 'cellular','telephone')<br>
9 - month: last contact month of year (categorical: 'jan', 'feb', 'mar', ..., 'nov', 'dec')<br>
10 - day_of_week: last contact day of the week (categorical: 'mon','tue','wed','thu','fri')<br>
11 - duration: last contact duration, in seconds (numeric). Important note: this attribute highly affects the output target (e.g., if duration=0 then y='no').<br>
Yet, the duration is not known before a call is performed. Also, after the end of the call y is obviously known. <br>
Thus, this input should only be included for benchmark purposes and should be discarded if the intention is to have a realistic predictive model.<br>
12 - campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact) <br>
13 - pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means client was not previously contacted)<br>
14 - previous: number of contacts performed before this campaign and for this client (numeric)<br>
15 - poutcome: outcome of the previous marketing campaign (categorical: 'failure','nonexistent','success')<br>
16 - emp.var.rate: employment variation rate - quarterly indicator (numeric)<br>
17 - cons.price.idx: consumer price index - monthly indicator (numeric)<br>
18 - cons.conf.idx: consumer confidence index - monthly indicator (numeric)<br>
19 - euribor3m: euribor 3 month rate - daily indicator (numeric)<br>
20 - nr.employed: number of employees - quarterly indicator (numeric)<br>
21 - y - has the client subscribed a term deposit? (binary: 'yes','no')<br>

### 4. Data Exploration
The figure 1 shows the distribution of all numerical features. It can be seen that the column age, duration, campaign, pdays and previous got outliers. The feature age will later discussed in the next plot. The feature duration will later be dropped because the influence of this feature is high to the result, also the information about the duration is not known before the call. The feature campaign will be discussed later in the plot Relationship between marketing campaigns and subscribing of contracts. The features shows that the median is around 1000 that means that the most clients has the same value. This feature will further inspected. The last feature with outliers is the feature previous. This feature  previous decribed how many times a client is called before the campaign. This information gains that max nr of 6 is a reasonale numer of previous calls. There is no need to delete outliers. <br>
<br>
<img src="/output/numerical_features.png" alt="Alt text" title="Optional title">

#### 4.1. Relationship between age and subscribing of contracts
For data analysis, the feature age in relation to contract conclusion is to be examined.  In order to present the data in a more meaningful way, I have sorted the data into age groups. Since there is not as much data for customers over 60 years of age, these customers were sorted into one group. <br>
In Figure 2, the first subplot examines the age structure and the second subplot the age groups with regard to the conclusion of a contract. It can be seen that the majority of customers are in the age group 30-39 , followed by the age group 40-49 and 50-59. The smallest number of customers are in the age group 60+ and 18-19. <br>
The second subplot shows that the rate of contract conclusion is approximately the same for almost all age groups. The exception is the 60+ age group, which clearly stands out with a contract conclusion rate of over 35%. This high rate may also be due to the fact that the number of customers is significantly lower than in the other age groups. <br>
<br>
<img src="/output/age_versus_subcribes.png" alt="Alt text" title="Optional title">

#### 4.2. Relationship between job and subscribing of contracts
The next analysis will look at the relationship of jobs in relation to contract completions. <br>
Figure 3 shows in the two subplots the different jobs of the customers and the conclusion of contracts in relation to the job. From the first subplot, it can be seen that the bank divides the clients into 12 job categories. The categories do not necessarily have to represent an occupation - see retired, unknown or student. Furthermore, it is clear that the majority of customers are admin, blue-collar or technician. <br>
In the second subplot, it becomes clear that the job categories student and retired stand out in terms of contract conclusions. This may be due to the fact that very little data exists on these types. However, it is also evident that the job types admin and technician also have high completion rates and there is lot of data is available on these job types. <br>
<br>
<img src="/output/job_versus_subcribes.png" alt="Alt text" title="Optional title">

#### 4.3. Relationship between marketing campaigns and subscribing of contracts
As a final analysis, I would like to look at the number of calls in the marketing campaigns versus the number of contracts signed.  <br>
In Figure 4, the number of calls per marketing campaign is related to the number of contracts signed. In the first subplot, the number of calls in the marketing campaign is examined. This shows that most of the bank's customers are called 1-3 times in a marketing campaign. However, a few customers were also contacted significantly more often. These are summarised under Miscellaneous.  <br>
The second plot contrasts the number of calls with the number of contracts signed. In general, a similar completion rate can be observed for the number of calls 1-4. In addition, a drop in completion rates can then be seen up to call number 11. For higher numbers of calls, a very high success rate of contracts can be seen. These results can be seen as exceptions, as there is very little data for these call numbers. As a conclusion, it can be seen that the success rate of 12% of contract conclusions is applicable for 88% of the customers. <br>
<br>
<img src="/output/marketing_versus_subcribes.png" alt="Alt text" title="Optional title">
### 5. Results
The `evaluation_df` dataframe shows the best result of each classifier with the best hyperparameter. The best results were achieved for the balanced decision tree and balanced random forest. The F1 scores of 0.43 for the balanced decision tree and 0.44 balanced random forest are significantly better compared to the random baseline of 0.109. Figure 11 shows a very good comparison of the results of all classifiers. The goal of the classifier to have the highest possible true positive rate was achieved most successfully with the balanced random forest.  There is a drastic difference in the result when adjusting the inbalanced data using the RandomOversamler. For the SVM, no test with balenced data could be carried out because the test would have taken too long. This could be tried to be trained in the cloud to get a comparison with the other classifiers. <br>
The next steps to increase the success of the bank and to achieve a higher sales quota in terms of financial products are to carry out a customer segmentation. Data exploration has shown that different professions buy more financial products on average. These customers could be called more often and special offers could be made in an attempt to achieve a higher sales quota. The next step in improving the machine learning model is to customise the models for the different customer segmentations. Furthermore, the model can be improved by using more data. For this model, only 10% of the initial data was used. The model could then be trained in the cloud to use a higher computing power.<br>
<br>
<img src="/output/results.png" alt="Alt text" title="Optional title">

### 6. References

[1]<a id='100'></a>      Dua, D. and Graff, C. (2019). UCI Machine Learning Repository [https://archive.ics.uci.edu/ml/datasets/bank+marketing](https://archive.ics.uci.edu/ml/datasets/bank+marketing)
