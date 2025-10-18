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


  











