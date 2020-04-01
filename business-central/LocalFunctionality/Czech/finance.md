---
title: Finance - Czech Local Functionality | Microsoft Docs
description: This section describes Czech local functionality for Finance.
author: v-pejano

ms-service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: CZ, Czech, Finance, Posting
ms.date: 04/01/2020
ms.reviewer: v-pejano
ms.author: v-pejano
---

# Finance

In the Czech Republic, there are specific [!INCLUDE[prodshort](../../includes/prodshort.md)] features that you can use to track and manage your finances.

## Corrections Posting (Red Storno)

According to legal requirements, costs and revenues are usually posted only to either the debit or the credit side of a G/L account. Companies in Eastern Europe usually enforce accounting policies to post certain inventory and GL transactions as corrections. The reason for this is that auditors and revenue authorities conduct accounting controls against this rule.  

The purpose of the feature is:  
- To allow the accounting manager to enforce corrective posting on desired G/L accounts  
- To allow the accounting manager to enforce corrective posting in inventory postings (negative transfer entries, expected costs posting)  
- To allow the accounting manager to enforce corrective posting of canceling in fixed assets  
- To allow the user to enforce corrective posting with one click (in G/L, inventory, and job postings)  

## Statutory Company Information

Many documents are circulating within and outside company structures. The minimum necessary requirements of such documents are set by local legislations. It is possible to divide such requirements roughly into three groups:
- Company officials' names must be present on some internal and external documents.
- Document footers – The majority of external documents must contain basic company information in document footers, usually in the company’s partner language.
- Registration numbers must be visible in internal and external documents.

This feature allows users to define company officials and designate them as General Manager, Accounting, and Finance Managers for usage in internal and external documents.

Users can define document footers in different languages. Such footers can be used in different reports and documents.

Additional company registration numbers and other registration information can be stored on the **Company Information** page and used in documents.

## Internal Financial Documents

Users perform general ledger operations and must have the possibility to print documents for these operations with layout in compliance with the legal requirements. Users also want to print a document for posted general ledger operations.

For the reasons above, this feature provides the following reports:
- General Journal – Test Report - used to print documents from G/L journals
- General Ledger Document Report - used to print posted general ledger operations

## Accounting Output Documents  

In order to comply with the legislation, reporting features, and local reporting practices of Czech companies, this feature provides the following reports:
- General Journal
- General Ledger
- Accounting Sheets
- Turnover report by Global Dimension
- Open G/L Entries to date
- Inventory Account to date
- Joining Bank Account Adjustment
- Joining G/L Account Adjustment
- G/L VAT Reconciliation
- All payments on hold
- Open Customer Entries at date
- Open Vendor Entries at date
- Fiscal Year Balance – standard report adjusted
- Trial Balance by Period – standard report adjusted

## Account Schedule Feature

As one of the most extensively used features for analysis and reporting, Eastern European countries often ask for the following improvements of the standard Account Schedules feature:

- Common list of expressions – A common list of expressions contains named lines that can be used in formulas of all account schedules. This is done by defining one of the account schedules as a common list of expressions called a Shared Account Schedule.
- Saving results (current state) of analysis – This improvement allows users to store results of analysis done by using account schedules, modification of results, and retrieval of results later on.
- Formulas drill-down – This improvement allows users to drill down on the results of formulas. Drill-down is now accessible for Totalling type formulas. Drilling down on the result of the formula shows the user a new page containing the list of elements used to calculate the results and their description.
- Additional data sources – Apart from being able to perform analysis on GL entries, the user can perform analysis on VAT, customer, vendor, and value entries.

## Statutory Statements

Companies must create financial statements according to the Accounting Law 563/1991. They must create the balance sheet and the profit and loss statement.
This feature provides the following reports:

- Balance Sheet
- Income Statement

These reports use the Account Schedule feature with the statement structure defined.

The **Acc. Schedule Name** table contains this new field in the Czech version:
- **Acc. Schedule Type** – Balance Sheet or Income Statement option

The **Acc. Schedule Line** table contains these new fields in the Czech version:
- **Row Correction** – links to another line for balance sheet setup
- **Assets/Liabilities Type** – Assets or Liabilities for Balance Sheet setup
- **Calc** – Always, Never, When positive, When Negative options

The balance sheet and the profit and loss statements are often prepared in Excel file templates with the necessary design for statement printout. Users want to map defined account schedules to prepared Excel templates.

For the reasons above, this feature provides the new setup of Excel templates and statement file mapping. Based on this setup, users can export account schedule data to Excel files.

## WIP Extended Posting

The Czech legal Work in Progress (WIP) posting scheme includes the following new general ledger accounts:
- Consumption Account
- Change in Inventory of WIP Account
- Change in Inventory of Product Account  

This feature allows you to correctly perform Czech WIP and production posting. It is therefore possible to set up a combination of location and inventory posting group for the accounts Consumption, Work in Progress, Change of Semi-finished Product, Change of Product.

This new posting scheme is used in the following transactions:
- Consumption posting in the consumption journal
- Posting the costs of capacities in the output journal
- Finishing orders and automatic production reporting

## Additional Finance Features

Use the following table to learn more about the additional finance features that are available for the Czech Republic.


| Topic                                                     | Description                                                  |
| :-------------------------------------------------------- | :----------------------------------------------------------- |
| [Year Closing Operations](year-close-operations.md)                        | To comply with accounting legislation at the end of the fiscal year, certain account books must be closed or opened. |
| [General Ledger Entries Application](general-ledger-entries-application.md)                                    | Apart from application of Customer and Vendor Ledger Entries, a new functionality of General Ledger Entries Application has been introduced. Application of General Ledger Entries is typically used to allow companies to work with temporary and transfer accounts in the General Ledger. |
| [Exchange Rate Updating](exchange-rate-update.md)                                    | Possibility to automatically update currency exchange rates from the external service provided by the ČNB (Czech National Bank). |

## See Also
[Czech Local Functionality](czech-local-functionality.md)
