# Aurora Bank Data Dictionary

This document describes the structure of the Aurora Bank datasets used in the Hackathon.

You will receive four CSV files:

- `customers.csv`
- `accounts.csv`
- `loans.csv`
- `transactions.csv`

All data is fictional and anonymised. Some fields are intentionally a bit messy. You are expected to make sensible cleaning and modelling decisions as part of the challenge.

---

## 1. customers.csv

Grain: one row per customer.

| Column              | Type      | Description                                                                                   |
|---------------------|-----------|-----------------------------------------------------------------------------------------------|
| `customer_id`       | string    | Unique identifier for each customer.                                                          |
| `first_name`        | string    | Customer first name.                                                                          |
| `last_name`         | string    | Customer surname.                                                                             |
| `age`               | integer   | Customer age in years.                                                                        |
| `region`            | string    | Broad geographic region for the customer, for example North, Midlands, South, London.        |
| `segment`           | string    | High level customer segment, for example Student, Professional, Family, Retired.             |
| `join_date`         | date      | Date the customer first joined Aurora Bank (YYYY-MM-DD).                                     |
| `marketing_channel` | string    | Primary channel through which the customer was acquired, for example Online Ads, Branch.     |

Note: Some values in `age` and `region` may be missing or inconsistent.

---

## 2. accounts.csv

Grain: one row per account.

| Column            | Type      | Description                                                                                 |
|-------------------|-----------|---------------------------------------------------------------------------------------------|
| `account_id`      | string    | Unique identifier for each account.                                                         |
| `customer_id`     | string    | The customer who owns this account.                                                         |
| `account_type`    | string    | Type of account, for example Current, Savings, Mortgage.                                   |
| `opened_date`     | date      | Date the account was opened (YYYY-MM-DD).                                                  |
| `is_active`       | boolean   | Indicates whether the account is currently active (`true` or `false`).                     |
| `overdraft_limit` | numeric   | Agreed overdraft limit for the account, usually relevant for current accounts only.        |
| `current_balance` | numeric   | Current account balance. Positive for credit, negative for overdrawn balances or mortgages.|

Note: Some accounts may be inactive or have zero overdraft limits.

---

## 3. loans.csv

Grain: one row per loan or mortgage.

| Column             | Type      | Description                                                                                           |
|--------------------|-----------|-------------------------------------------------------------------------------------------------------|
| `loan_id`          | string    | Unique identifier for each loan.                                                                      |
| `customer_id`      | string    | The customer who took out the loan.                                                                  |
| `product_type`     | string    | Type of lending product, for example Mortgage, Interest Loan, Payday Loan.                           |
| `approved_amount`  | numeric   | The principal amount approved for the loan.                                                           |
| `term_months`      | integer   | Length of the loan term in months.                                                                    |
| `interest_rate`    | numeric   | Annual interest rate for the loan, expressed as a percentage.                                        |
| `application_date` | date      | Date the loan was applied for (YYYY-MM-DD).                                                           |
| `status`           | string    | Status of the loan, for example Approved, Declined, In Arrears.                                      |

Note: Values vary by product type. Some records may be declined or in arrears.

---

## 4. transactions.csv

Grain: one row per transaction on eligible accounts (mainly current and savings accounts).

| Column             | Type      | Description                                                                                           |
|--------------------|-----------|-------------------------------------------------------------------------------------------------------|
| `transaction_id`   | string    | Unique identifier for each transaction.                                                               |
| `account_id`       | string    | The account this transaction belongs to.                                                              |
| `date`             | date      | Date of the transaction (YYYY-MM-DD).                                                                 |
| `amount`           | numeric   | Transaction amount. Positive values represent money in, negative values money out.                    |
| `transaction_type` | string    | High level type of transaction, for example Card Payment, Salary, Cash Withdrawal, Fee, Transfer.     |
| `channel`          | string    | Channel used for the transaction, for example Mobile, Web, Branch.                                   |
| `merchant_category`| string    | Category for where or what the spend or income relates to, for example Groceries, Utilities, Income. |

Note: Some `channel` values and other text fields may contain minor inconsistencies or missing values.

---

## General notes

- `customer_id` links customers to accounts and loans.
- `account_id` links accounts to transactions.
- Dates are provided in ISO format (YYYY-MM-DD).
- You may need to clean, standardise and join these datasets before building your analysis or tool.

You are free to make reasonable assumptions when cleaning and joining the data. Document any rules or assumptions you apply.
