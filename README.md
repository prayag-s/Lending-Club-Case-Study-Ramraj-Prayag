# Lending Club Case Study

   <p align="right">By Ramraj Vasudevan and Prayag Sanjay</p>

## Problem Statement
1.	 A consumer finance company that specialises in lending various types of loans to urban customers must decide for loan approval based on the applicant’s profile. Two types of risks are associated.
    - Loss of business if applicant likely to repay loan.
    - Loss of finance if applicant NOT likely to repay loan.
## Data Set
2.	 Past loan applicants’ data and whether they ‘defaulted’ or not.
## Aim
3.	 To identify patterns which indicate if a person is likely to default.
## Understanding of Case
### Introduction.  
4.  A loan decision by a bank is dependent upon various factors. It evolves through various stages. In the current lending club case study, an understanding of the process would provide insights into the loan decision which is crucial in determining the attributes that contribute to the type of loan . 
### Loan Stages.  
5.  Loan is a crucial decision by financial institutions. Depending upon institutions, there are different stages in the process. For the purpose of this case study, we have divided these into four stages: -
    - Customer information and verificatoin stage.
    - Loan decision stage.
    - Loan monitoring and control stage and
    - Loan termination stage.
### Customer Information and Verification Stage.   
6.  Information of different attributes of customer and its due verification is an important first step in loan decision. The attributes to be considered include the following: -
    - Annual income (annual_inc), 
    - Identity and address information (addr_state, zip_code)
    - Ongoing debt (dti), 
    - Stability of income for the future including
      - Earliest credit line compared to issue date; difference between issue_d and earliest_cr_line), 
      - Length of employment (emp_length)
    - Loan amount applied for (loan_amnt)
    - Purpose of loan (purpose)
    - Home ownership status (home_ownership), showing collateral capability for loan.
    - The number of delinquencies (delinq_2yrs and mths_since_last_delinq)
    - The credit quality of the borrower (open_acc, pub_rec, pub_rec_bankruptcies, revol_bal, revol_util, total_acc and inq_last_6mths and last_credit_pull_d)
    - Verification status.
### Loan Decision Stage.  
7.  The decisions taken as a resut of the outcome of processing the above information include the following: - 
    - Amount to be funded (funded_amnt)
    - Interest rate (int_rate)
    - Loan period (term)
    - Loan grade (grade)
    - Installment amount (installment)
###	Loan Monitoring and Control Stage.  
8.  In this stage factors that provide information on loan continuity can be considered. These include: -
    - Outstanding Principal amount (out_prncp)
    - Outstanding principal investor (out_prncp_inv)
    - Last payment amount (last_pymnt_amnt) Last payment date (last_pymnt_d)
### Loan Termination Stage.
9.  The termination stage information provides the quality of a loan. These include: -
    - Loan status (loan_status)
    - Total recoveries (recoveries)
    - Total payments including principal, interest and investor share (total_pymnt, total_pymnt_inv, total_rec_prncp, total_rec_int, total_rec_late_fee and collection_recovery_fee)
## Results Expected
10.  Well commented Python file (Ramraj_Prayag.ipynb) mentioning the following in comments or markdown text: -
     - Insights
     - Observations
11.  Presentation covering: -
     - Problem statement
     - Analysis approach
12.  Explanation of univariate, bivariate analysis etc in business terms.
13.  Include visualisations and summarise most important results.
14.  Submit GitHub repository with link of files.
15.  Write a README.md for the above repository.

## Concept and Approach
### Concept
   - Loan Stages.  Our concept of determining loan default will flow from the stages of loan. The loan decision stage is an important stage. The loan company considers all background information including customer and verification information to arrive at the most important factor.
   - Key Factors in Stages
     - In our case study, we determine that this factor is the *installment* amount. This amount incorporates all necessary information pertaining to the customer’s information and determines of her/ his capability to repay the loan and therefore arrive at the amount to be funded. However, installment amount needs to be matched with income debt to arrive at an indicator for loan capacity.

### Approach. 
  #### EDA.  
   - Based on the available data, as part of EDA, the first step is to clean, correct missing values and data manipulation. We will analyse data using univariate, bivariate    and multi variate analyses. Metrics will be derived for business, type and data driven approaches. Finally, we will check the effect of these metrics and analyses to determine whether or not a loan would default.
  #### Key Indicator.  
   - In the dataset, the loan status is the key indicator. It indicates whether the loan has defaulted, currently running or fully paid. To categorise loan, we need to look at those cases that have either defaulted or fully paid. So, current loans can be disregarded. We will delete all rows with loan status as ‘Current’.
  #### Metrics
   - Having determined *installment*  as our key factor in the decision stage, we will derive metrics based on this. Installment will be matched with debt to arrive at this metric. In cases of house and vehicle loan, debt to income ratio is considered and in other cases, revolving utilisation rate is considered . Therefore, the ratio of installment amount to annual income added with debt to income ratio (*dti*) or revolving utilisation rate would provide an indication of the limit of loan capacity of a borrower.  The *revol_util* field in the instance case is the amount of credit the borrower is using. So, the debt part is *100 – revol_util*. The total debt percentage is representative of the loan grade. The derived metric of installment income percentage along with dti and revolving utility rate can be used as another set of metrics.
   - Prior proceeding to this calculation, we will investigate the data driven metric of length of credit history to verify if it has any bearing on the loan quality.
   - The number of accounts held by a borrower is also an important information. A ratio between open accounts and total accounts can be used as a metric.
   - The next stage is the monitoring of the loan. During this stage, the factors taken into account are the outstanding amounts and the last payment date. Since the last payment date can be either before or after the term completion, this information could provide some indication to the loan status. 
   - At the loan termination stage, the ratio of total amounts recovered to funded amount could provide insight to the loan quality. 


## Summary
16.  The data was cleaned and checked for consistencies. As part of Exploratory Data Analysis, different forms of analysis were carried out.
17.  Different variables were investigated for its relationships. Effect of attributes with each other were examined. Relevant plots were generated for explaining the same. Data analysis was undertaken using business concept. Necessary metrics aimed at data and business concepts were generated and analysed. These include: -
     - Length of Credit History
     - Foreclosure Period
     - Ratio of open account to total account
     - Instalment to income percentage
     - Instalment to debt to income percentage
     - Instalment to revolving utility rate percentage
18.  Key indicators bearing universal effect on the data were discovered by deriving various metrics. These provided limiting values that can be used to classify loans.

## Conclusion
19.  The loan status is the key indicator of loan and customer attributes and their combinations.
20.  The loan grade is a key guiding factor that shows the manner in which loan decisions are made.
21.  Other categorical variables were used to verify results obtained against loan grade.
22.  Key metrics. The following are the key metrics that provide various limits to decide grant of loan:
     - Ratio of open account to total account
     - Instalment to income percentage
     - Instalment to debt to income percentage
23.  In all the above metrics, values against fully paid loan status are the determining levels. Cases where values are higher than these levels are highly likely to default.
24.  Other metrics including Length of credit history, foreclosure period and instalment to revolving utility rate percentage had little significance in determining loan quality.
