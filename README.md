
# 💳 Credit-Card-Financial-Dashboard
PowerBI Dashboard

## Project Objective
To develop a comprehensive credit card weekly dashboard that provides real-time insights into key performance metrics and trends, enabling stakeholders to monitor and analyze credit card operations effectively.


## 🔹 DAX Queries
 AgeGroup = SWITCH(
 TRUE(),
 'public cust_detail'[customer_age] < 30, "20-30",
 'public cust_detail'[customer_age] >= 30 && 'public cust_detail'[customer_age] < 40, "30-40",
 'public cust_detail'[customer_age] >= 40 && 'public cust_detail'[customer_age] < 50, "40-50",
 'public cust_detail'[customer_age] >= 50 && 'public cust_detail'[customer_age] < 60, "50-60",
 'public cust_detail'[customer_age] >= 60, "60+",
 "unknown"
 )
 
 IncomeGroup = SWITCH(
 TRUE(),
 'public cust_detail'[income] < 35000, "Low",
 'public cust_detail'[income] >= 35000 && 'public cust_detail'[income] <70000, "Med",
 'public cust_detail'[income] >= 70000, "High",
 "unknown"
 )

 week_num2 = WEEKNUM('public cc_detail'[week_start_date])
 Revenue = 'public cc_detail'[annual_fees] + 'public cc_detail'[total_trans_amt] + 'public cc_detail'[interest_earned]
 
 Current_week_Reveneue = CALCULATE(
 SUM('public cc_detail'[Revenue]),
 FILTER(
 ALL('public cc_detail'),
 'public cc_detail'[week_num2] = MAX('public cc_detail'[week_num2]))) 
 
 Previous_week_Reveneue = CALCULATE(
 SUM('public cc_detail'[Revenue]),
 FILTER(
 ALL('public cc_detail'),
 'public cc_detail'[week_num2] = MAX('public cc_detail'[week_num2])-1)


## 📂 Dataset used
- <a href="https://github.com/WajihaKashafAli/E-Commerce-Sales-Dashboard/blob/main/Order.csv">Dataset</a>
- <a href="https://github.com/WajihaKashafAli/E-Commerce-Sales-Dashboard/blob/main/Details.csv">Dataset</a>

## ⚡ Tech Stack

## 🚀 Use Case:

## 🧠 Key Questions (KPIs)


## ⚙️ Process


## 📊 Dashboard
![Dashboard](https://github.com/user-attachments/assets/29303346-b3e9-4555-92c5-b4041c92bdaf)
![Dashboard-1](https://github.com/user-attachments/assets/146733a8-c6b7-4f92-a045-3955ddf7183b)
![Dashboard-2](https://github.com/user-attachments/assets/9f039141-e539-4760-a3b5-7b6c7a1a3be1)
https://github.com/WajihaKashafAli/Credit-Card-Financial-Dashboard/blob/main/Credit_Card_Customer_Report.pdf






## 🔍 Project Insights - Week 53 (31st Dec)
WoW change:
• Revenue increased by 28.8%, 
• Total Transaction Amt & Count increased by 123.54% & 96.59%
• %GT Average of income 110.64%
• Customer count increased by 667.2K

Overview YTD:
• Overall revenue is 57M 
• Total interest is 8M
• Total transaction amount is 46M
• Male customers are contributing more in revenue 31M, female 26M
• Blue & Silver credit card are contributing to 93% of overall transactions
• TX, NY & CA is contributing to 68%
• Overall Activation rate is 57.5%
• Overall Delinquent rate is 6.06%



## 🏁 Final Conclusion:
