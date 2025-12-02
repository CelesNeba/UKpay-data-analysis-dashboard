# Title: UKPay: A Digital Wallet System

#### Project Objective: Create a simplified version of a digital wallet system tailored to the UK market. The project will simulate essential features like peer-to-peer transfers, utility bill payments, merchant payments, and transaction tracking. I will work on SQL for database design and querying, Python for analytics and backend logic.


### 📂 Cleaned dataset
▪ [ View Merchants Dataset](https://github.com/CelesNeba/UKpay-data-analysis-dashboard/blob/main/ukpay_merchants.csv)

▪[ View Transactions Dataset](https://github.com/CelesNeba/UKpay-data-analysis-dashboard/blob/main/ukpay_transactions.csv)

▪[ View Users Dataset](https://github.com/CelesNeba/UKpay-data-analysis-dashboard/blob/main/ukpay_users.csv)


#### Phase 1: Database Design and SQL Implementation

#### Objective: Design a relational database to store transaction details, user profiles, and services.


####	Define tables for:
   
o	Users: UserID, Name, Email, Phone, Balance, RegistrationDate.

o	Transactions: TransactionID, UserID, RecipientID, Amount, Type (P2P, Utility, Merchant), Date.

o	Merchants: MerchantID, MerchantName, Category, Location.

o	UtilityPayments: PaymentID, UserID, UtilityType (Electricity, Gas, Water), Amount, Date.


####	Write SQL queries to:

o	Retrieve monthly transaction summaries for each user.

o	Identify top-performing merchants based on transaction volume.

o	Calculate the average utility bill amount per user.


#### Python Analytics

Objective: Analyze transaction data for user insights and backend functionality.
#### Steps:

	Load data from the database into Python using libraries like pandas and sqlalchemy.
   
####	Perform analytics:

o	Identify the most frequent transaction type for each user.

o	Calculate the growth in total transactions month-over-month.

o	Create user segmentation based on transaction frequency and average transaction size.

####	Simulate backend logic:
o	Deduct balances for successful transactions.
o	Generate reminders for users with low balances.
o	Provide insights into spending patterns using Python visualizations (matplotlib, seaborn).


## Phase 3: Data Visualization

Objective: Build dashboards to visualize trends and insights.

Tool: Power BI 

Steps:
1.	Import the data processed in Python into the visualization tool.

2.	Create dashboards:

o	User-level dashboard showing individual spending trends, transaction categories, and balance history.

o	Merchant-level dashboard displaying transaction volume, revenue, and top customers.

o	Overall system performance dashboard showing metrics like total transactions, active users, and revenue trends.

	Include interactive filters to analyze data by date range, user demographics, and transaction types.

	Below is UKpay dashboard to show the following KPIs 

o	Individual spending trends, transaction categories, and balance history.

o	Transaction volume, revenue, and top customers.

o Total transactions, active users, and revenue trends.

o Interactive filters to analyze data by date range, user demographics, and transaction types.




![UK Pay Dashboard Screenshot](https://github.com/CelesNeba/UKpay-data-analysis-dashboard/raw/main/UKpay%20dashboard%20Screenshot.png)




### My recommendation to stakeholders

Based on the UKPay data analysis, I recommend that stakeholders focus on enhancing user engagement and merchant partnerships. Prioritize strategies to increase active users, such as targeted promotions and improving user experience, while also incentivizing merchant participation to grow transaction volume and overall revenue trends.



  











