# Title: UKPay: A Digital Wallet System

#### Project Objective: Create a simplified version of a digital wallet system tailored to the UK market. The project will simulate essential features like peer-to-peer transfers, utility bill payments, merchant payments, and transaction tracking. I will work on SQL for database design and querying, Python for analytics and backend logic.


### 📂 Cleaned dataset
▪ [ View Merchants Dataset](https://github.com/CelesNeba/UKpay-data-analysis-dashboard/blob/main/ukpay_merchants.csv)

▪[ View Transactions Dataset](https://github.com/CelesNeba/UKpay-data-analysis-dashboard/blob/main/ukpay_transactions.csv)

▪[ View Users Dataset](https://github.com/CelesNeba/UKpay-data-analysis-dashboard/blob/main/ukpay_users.csv)


### Phase 1: Database Design and SQL Implementation

#### Create database

Create Database ukpay;

####   Create tables

use ukpay;

### users table
CREATE TABLE users (
  UserID INT AUTO_INCREMENT PRIMARY KEY,
  Name VARCHAR(100) NOT NULL,
  Email VARCHAR(255) NOT NULL UNIQUE,
  Phone VARCHAR(30) UNIQUE,
  Balance DECIMAL(10,2) NOT NULL DEFAULT 0.00,
  RegistrationDate DATE NOT NULL
);



#### transactions table

CREATE TABLE Transactions (
  TransactionID BIGINT PRIMARY KEY,
  UserID INT NOT NULL,
  RecipientID INT NULL,   
  Amount DECIMAL(10,2) NOT NULL,
  Type VARCHAR(20) NOT NULL,
  `Date` DATE NOT NULL,
  UtilityType VARCHAR(20) NULL
);



#### merchants table
CREATE TABLE merchants (
  MerchantID INT AUTO_INCREMENT PRIMARY KEY,
  MerchantName VARCHAR(255) NOT NULL,
  Category VARCHAR(100),
  Location VARCHAR(255)
);


#### Utility Payments table

-- I populated 2000+ rows of mock data from python, and push to  UtilityPayments

CREATE TABLE UtilityPayments (        
    PaymentID BIGINT PRIMARY KEY,
    UserID INT NOT NULL,
    UtilityType VARCHAR(20) NOT NULL,
    Amount DECIMAL(10,2) NOT NULL,
    `Date` DATETIME NOT NULL
);

#### Database queries

#### 1. Retrieve monthly transaction summaries for each user
SELECT 
    UserID,
    DATE_FORMAT(`Date`, '%Y-%m') AS YearMonth, -- DATE_FORMAT(Date, '%Y-%m') groups transactions by month
    
    COUNT(*) AS Num_of_ransactions, -- COUNT(*) gives the number of transactions per user per month.
    
    SUM(Amount) AS Total_amount -- SUM(Amount) gives total spending per user per month.

FROM Transactions -- From transactions is the table name

GROUP BY UserID, YearMonth -- GROUP BY tells SQL to aggregate rows that have the same values in the listed columns.

ORDER BY UserID, YearMonth; -- ORDER BY determines how the results are sorted in the output.
                            -- In this case, it would be by UserID (ascending), then by YearMonth (ascending).


## Phase 2: Python Analytics


####  1. Load data from MySQL into Python *****************************

import pandas as pd

from sqlalchemy import create_engine, text

#### MySQL connection

engine = create_engine("mysql+pymysql://fintech:StrongPassword123@localhost/ukpay")

#### Load the Transactions table
with engine.connect() as conn:
    transactions = pd.read_sql("SELECT * FROM Transactions", conn)

#### Preview the data
print(transactions.head())


