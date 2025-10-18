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

