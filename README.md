# Credit Risk & Loan Default Analysis | Power BI Portfolio

![Page 1 - Executive Summary](images/Executive-Summary.png)

## Project Introduction

Use Power BI, Power Query, and DAX to analyze credit risk and loan default data, identify major default risk drivers, and support credit risk monitoring and lending decisions.

## Data Source

- Kaggle: Credit Risk Dataset
- Link: https://www.kaggle.com/datasets/laotse/credit-risk-dataset
- Key fields: person_age, person_income, person_emp_length, person_home_ownership, loan_amnt, loan_int_rate, loan_grade, loan_intent, loan_percent_income, cb_person_default_on_file, loan_status

## Tools

Power BI Desktop, Power Query, DAX

## Analysis Process

1. Data cleaning using Power Query.
2. Create age groups, income groups, loan amount groups, DTI groups, and default labels.
3. Create DAX measures for loan amount, default rate, average interest rate, and default amount ratio.
4. Create three report pages: Executive Summary, Risk Driver Analysis, and Detail Drillthrough.
5. Add a What-If parameter to simulate interest rate changes and analyze their impact on loan portfolio risk.

## Key DAX Measures

```DAX
Total Loans = COUNTROWS('credit_risk_dataset')

Total Loan Amount = SUM('credit_risk_dataset'[loan_amnt])

Default Loan Amount = CALCULATE([Total Loan Amount], credit_risk_dataset[loan_status]=1)

Default Rate =DIVIDE([Default Loans Amount],[Total Loans])

Average Interest = AVERAGE('credit_risk_dataset'[loan_int_rate])

Default Amount Ratio = DIVIDE([Default Loan Amount], [Total Loan Amount])

```

## Report Pages

### Page 1: Executive Summary

![Page 1](images/Executive-Summary.png)

### Page 2: Risk Driver Analysis

![Page 2](images/Risk-Driver-Analysis.png)

### Page 3: Detail Drillthrough

![Page 3](images/Drtail-Drillthrough.png)

## Key Insights 

1. Loan grade is strongly related to default risk: default rates generally increase from Grade A to Grade G.

2. Default rates vary significantly by loan purpose: VENTURE and DEBTCONSOLIDATION generally have higher default rates than EDUCATION and MEDICAL.

3. Higher DTI is associated with higher risk: borrowers with a higher `loan_percent_income` (the share of income used for the loan) generally have higher default rates.

4. Borrowers with a previous default history have higher risk: customers with `cb_person_default_on_file = Y` (a previous default recorded on file) have a noticeably higher default rate than those with `N` (no previous default recorded).

5. Home ownership status is related to default risk: borrowers who RENT generally have higher default rates than those who OWN or have a MORTGAGE.

## Business Recommendations

1. Apply tighter risk controls to customers with **Grade G loans, high DTI, and low income**.
   
2. For **VENTURE** and **DEBT CONSOLIDATION** loans, consider higher interest rates or lower credit limits to compensate for elevated risk.
   
3. Strengthen income and asset verification for **renters without property ownership**.
   
4. Use **What-If analysis** to simulate how interest rate adjustments affect defaulted loan amounts and support pricing decisions.

## Key Insights 

1. Loan grade is strongly related to default risk: default rates generally increase from Grade A to Grade G.

2. Default rates vary significantly by loan purpose: VENTURE and DEBTCONSOLIDATION generally have higher default rates than EDUCATION and MEDICAL.

3. Higher DTI is associated with higher risk: borrowers with a higher `loan_percent_income` (the share of income used for the loan) generally have higher default rates.

4. Borrowers with a previous default history have higher risk: customers with `cb_person_default_on_file = Y` (a previous default recorded on file) have a noticeably higher default rate than those with `N` (no previous default recorded).

5. Home ownership status is related to default risk: borrowers who RENT generally have higher default rates than those who OWN or have a MORTGAGE.

## Business Recommendations

1. Apply tighter risk controls to customers with **Grade G loans, high DTI, and low income**.
   
2. For **VENTURE** and **DEBT CONSOLIDATION** loans, consider higher interest rates or lower credit limits to compensate for elevated risk.
   
3. Strengthen income and asset verification for **renters without property ownership**.
   
4. Use **What-If analysis** to simulate how interest rate adjustments affect defaulted loan amounts and support pricing decisions.



## Power BI File

Power BI source file available in the `pbix` folder.

## Author

- Name: Lingxi Li
- GitHub: lingxiquq-cpu
