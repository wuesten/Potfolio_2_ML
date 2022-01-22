<h1><center>«Portfolio-Exam Part II» </center></h1>
<h2><center>MADS-ML </center></h2>
<h3><center>Author: Tom Wüsten </center></h3>



### Introduction
This paper deals with the topic of marketing campaigns in the banking sector. It specifically examines a Portuguese bank whose aim is to sell a product over the phone. This product is a term deposit (deposit in a financial institution with a specific maturity date). The aim of this work is to create a machine learning model that predict the success of a subscriben for a term deposit. The first step in creating a machine learning model is to analyse the data and do a data exploration. The data exploration investigated whether certain age groups, jobs or the number of calls are conspicuously concluding a term deposit. In order to find the best possible machine learning algorithm, different algorithms are compared with each other.

#### Dataset Licence
CC BY 4.0 <br>

### Dataset Information:

There are several datasets for this marketing campaign of the bank. I choosed the dataset bank-additional.csv because it has only 10% of the dataset bank-additional-full.csv. The reason is to keep the run time of the notebook low. The reduced dataset contains 4119 instances with 21 attributes, where each instance describes a phone call between a bank employee and a bank customer.
All following information about the attributes are copied from uci machine learning repository. [[1]](#100) <br>
##### bank client data:
1 - age (numeric) <br>
2 - job : type of job (categorical: 'admin.','blue-collar','entrepreneur','housemaid','management','retired','self-employed','services','student','technician','unemployed','unknown') <br>
3 - marital : marital status (categorical: 'divorced','married','single','unknown'; note: 'divorced' means divorced or widowed) <br>
4 - education (categorical: 'basic.4y','basic.6y','basic.9y','high.school','illiterate','professional.course','university.degree','unknown') <br>
5 - default: has credit in default? (categorical: 'no','yes','unknown') <br>
6 - housing: has housing loan? (categorical: 'no','yes','unknown') <br>
7 - loan: has personal loan? (categorical: 'no','yes','unknown') <br>
#####  related with the last contact of the current campaign:
8 - contact: contact communication type (categorical: 'cellular','telephone') <br>
9 - month: last contact month of year (categorical: 'jan', 'feb', 'mar', ..., 'nov', 'dec') <br>
10 - day_of_week: last contact day of the week (categorical: 'mon','tue','wed','thu','fri') <br>
11 - duration: last contact duration, in seconds (numeric). Important note: this attribute highly affects the output target (e.g., if duration=0 then y='no'). <br>
Yet, the duration is not known before a call is performed. Also, after the end of the call y is obviously known. <br>
Thus, this input should only be included for benchmark purposes and should be discarded if the intention is to have a realistic predictive model.
#####  other attributes:
12 - campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact) <br>
13 - pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means client was not previously contacted) <br>
14 - previous: number of contacts performed before this campaign and for this client (numeric) <br>
15 - poutcome: outcome of the previous marketing campaign (categorical: 'failure','nonexistent','success') <br>
#####  social and economic context attributes
16 - emp.var.rate: employment variation rate - quarterly indicator (numeric) <br>
17 - cons.price.idx: consumer price index - monthly indicator (numeric) <br>
18 - cons.conf.idx: consumer confidence index - monthly indicator (numeric) <br>
19 - euribor3m: euribor 3 month rate - daily indicator (numeric) <br>
20 - nr.employed: number of employees - quarterly indicator (numeric) <br>

#####  Output variable (desired target):
21 - y - has the client subscribed a term deposit? (binary: 'yes','no') <br>

![alt text](https://github.com/wuesten/Potfolio_2_ML/output/main/test.png?raw=true)
