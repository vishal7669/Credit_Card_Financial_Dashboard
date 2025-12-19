# Credit_Card_Financial_Dashboard

Step 1:Import data to SQL database

1. Prepare csv file.
  
2. Create tables in SQL.

3. import csv file into SQL Step 2:Connect with Mysql database in Power Bi Step 3:3 & 4 column Added in Table in power Bi with DAX Queries.

4. Revenue = 'ccdb cc_detail'[Annual_Fees] + 'ccdb cc_detail'[Total_Trans_Amt] + 'ccdb cc_detail'[Interest_Earned].
   
5. Week_num2 = WEEKNUM('ccdb cc_detail'[Week_Start_Date])

6. AgeGroup = SWITCH(TRUE(),'ccdb cust_detail'[Customer_Age] < 30,"20-30",'ccdb cust_detail'[Customer_Age] >= 30 && 'ccdb cust_detail'[Customer_Age] < 40,"30-40",'ccdb   cust_detail'[Customer_Age] >= 40 && 'ccdb cust_detail'[Customer_Age] < 50,"40-50",'ccdb cust_detail'[Customer_Age] >= 50 && 'ccdb cust_detail'[Customer_Age] < 60,"50-60",'ccdb cust_detail'[Customer_Age] >= 60, "60+","unknown").

7. IncomeGroup = SWITCH(TRUE(),'ccdb cust_detail'[Income] < 35000, "Low",'ccdb cust_detail'[Income] >= 35000 && 'ccdb cust_detail'[Income] <70000, "Med",'ccdb cust_detail'[Income] >= 70000, "High","unknown") Step 4: Some Measure created with Dax Queries.

8. Previous_Week_Revenue = CALCULATE( SUM('ccdb cc_detail'[Revenue]), FILTER( ALL('ccdb cc_detail'), 'ccdb cc_detail'[Week_num2] = MAX('ccdb cc_detail'[Week_num2])-1)).

9. Current_Week_Revenue = CALCULATE( SUM('ccdb cc_detail'[Revenue]), FILTER( ALL('ccdb cc_detail'), 'ccdb cc_detail'[Week_num2] = MAX('ccdb cc_detail'[Week_num2]))).

10. wow_revenue = DIVIDE([Current_Week_Revenue] - [Previous_Week_Revenue],[Previous_Week_Revenue]) Step 5: Then I'm Created Dashboard.

Project Insights-

Week of Week Changes:

Revenue increased by 28.8%,

Overview YTD:

1. Overall revenue is 57M.
2. Total interest is 8M.
3. Total transaction amount is 46M.
4. Male customers are contributing more in revenue 31M, female 26M, Blue & Silver credit card are contributing to 93% of overall transactions.
5. TX, NY & CA is contributing to 68%, Overall Activation rate is 57.5%, Overall Delinquent rate is 6.06%.
