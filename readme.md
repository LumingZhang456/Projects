# Analyzing Prosper Loan Data
## by Luming Zhang


## Dataset

This data set contains 113,937 loans with 81 variables on each loan, including loan amount, borrower rate (or interest rate), current loan status, borrower income, and many others.

This [data dictionary](https://docs.google.com/spreadsheets/d/1gDyi_L4UvIrLTEC6Wri5nbaMmkGmLQBk-Yx3z0XDEtI/edit#gid=0) explains the variables in the data set.


## Summary of Findings

At first, I assumed features like 'CreditGrade', 'BorrowerAPR', 'ProsperRating', 'IncomeRange', 'DebtToIncomeRatio', 'LoanStatus' and 'EmploymentStatus' might suppport the investigation.

For the __Univariate Exploration__, I analyzed variables __CreditGrade__, __BorrowerAPR__, __DebtToIncomeRatio__, __ProsperRating__, __LoanStatus__ and __EmploymentStatus__. The distribution of __CreditGrade__ and __ProsperRating__ are normally distributed. The distribution of __DebtToIncomeRatio__ is highly skewed because of outliers. There are not too many data between ratio 1.5 and 10. After removing the ourliers, we can see that this distribution is right skewed. And the median is near 0.2. It means that most of loans were given to borrowers whose debt is 5 times more than their income.

For the __Bivariate Exploration__, I analyzed correlation between each two variables. From the correlation scatter plot and heatmap, we can see that __ProsperRating (numeric)__ is highly correlated with __BorrowerAPR__ and __BorrowerRate__. __BorrowerAPR__ and __BorrowerRate__ have the highest correlation between each other. At the begining, I assumed that __'DebtToIncomeRatio'__ maybe have impact on loan inerest. However, from the plots, we see that the correlation coefficient between __'DebtToIncomeRatio'__ and __BorrowerRate__ is nearly __0__, which means that there is no correlation between these two variables. By analyzing the relationship between __ProsperRating__ and __EmploymentStatus__, level __C__ of __ProsperRating (Alpha)__ has the most count of loans in __employed__ and __self-employed__ groups. However, for __Full-time__ group, __rating A__ has the most count of loans. This should be an interesting finding.

For the __Multivariate Exploration__, I analyzed two groups of variables, which are __CreditScore__ and __BorrowerAPR__. __ProsperRating__ and __BorrowerAPR__ with categorical level __Term__. With the change of credit grade, we observed that the trend of __BorrowerAPR__ goes down. The average __BorrowerAPR__ of credit grade __A__ is much less than the __BorrowerAPR__ of credit grade __HR__. This means that high risk borrowers has a high APR than safe borrowers. For the second group of variables, we obtained the overall trend of __BorrowerAPR__ is decreasing with the __ProsperRating__ goes up, which means that borrowers with high __ProsperRating__ would have lower APR. By observing the __Term__ of each group, We can see that for low prosper rating borrowers, they likely have 12 months loan with higher APR and 60 months loan with lower APR. And for high prosper rating borrowers, they likely have 60 months loan with higher APR and 12 months loan with lower APR.


## Key Insights for Presentation

For the presentation, I pay attention on something interesting than the general findings. For example, 'for low prosper rating borrowers, they likely have 12 months loan with higher APR and 60 months loan with lower APR. And for high prosper rating borrowers, they likely have 60 months loan with higher APR and 12 months loan with lower APR.'. And I also focus on the relationship between __BorrowerAPR__ and other variables. Because I want to investigate the impact of other variables on __BorrowerAPR__.