Bank Customer Churn Analysis
Project Overview
This project analyzes customer churn behavior using SQL and Power BI dashboards.
The goal was to identify key drivers of customer churn and provide business insights for retention strategies.
Dashboards were designed to allow interactive filtering based on:
Gender
Geography

🛠 Tools Used
SQL
Power BI
Power BI Service

📂 Dataset Features
Customer Id
Geography
Age
Balance
Credit Score
Salary
Products Used
Activity Status
Churn Status

💻 SQL Analysis
Churned Customers by Geography
select geography, count(customer id) as churned_customers 
from bank_data
where exited=1 
and geography in ('France','Germany','Spain')
group by geography;

Average Balance in Germany
select geography, avg(balance) 
from bank_data
where geography='Germany'
group by geography;

Tenure Distribution
select tenure, count(customerid) as customer_tenure
from bank_data
group by tenure
order by tenure desc;

Product Usage Distribution
select numofproducts, count(customerid) as products_used
from bank_data
group by numofproducts;

Active vs Inactive Members
select
sum(case when isactivemember=1 then 1 else 0 end) as active_members,
sum(case when isactivemember=0 then 1 else 0 end) as inactive_members
from bank_data;

🔎 Key Insights
Churn varies by geography.
Single product customers show higher churn risk.
Inactive customers are more likely to leave.
Tenure influences customer loyalty.

🚀 Recommendations
Improve engagement for inactive customers.
Promote cross-selling strategies.
Implement region-specific retention campaigns.
Improve onboarding experience for new customers.

