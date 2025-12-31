This repository contains practical SQL mini-projects designed to demonstrate real-world Business Analysis, Data Analysis, Reconciliation, Capital Markets, and Data Governance skills.
All examples are based on banking and financial services use cases,commonly encountered in enterprise environments.

1. Bank Transaction Reconciliation
Business Objective
Ensure consistency between core banking transactions and ledger records by identifying mismatches and missing entries.

Tables
bank_transactions(transaction_id, account_no, amount, txn_date)
ledger_transactions(transaction_id, account_no, amount, txn_date)

SQL – Amount Mismatch Identification

SELECT 
    b.transaction_id,
    b.account_no,
    b.amount AS bank_amount,
    l.amount AS ledger_amount
FROM bank_transactions b
JOIN ledger_transactions l
    ON b.transaction_id = l.transaction_id
WHERE b.amount <> l.amount;


