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
