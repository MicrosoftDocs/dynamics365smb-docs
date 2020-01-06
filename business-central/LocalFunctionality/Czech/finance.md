---
title: Finance - Czech Local Functionality | Microsoft Docs
description: This section describes Czech local functionality for Finance.
author: v-pejano

ms-service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: CZ, Czech, Finance, Posting
ms.date: 05/15/2019
ms.reviewer: v-pejano
ms.author: v-pejano
---

# Finance

In the Czech Republic, there are specific [!INCLUDE[prodshort](../../includes/prodshort.md)] features that you can use to track and manage your Finance.

## Corrections Posting (Red Storno)

According to legal requirements, costs and revenues are usually posted only to either the debit or the credit side of a G/L Account. Companies in Eastern Europe usually enforce accounting policy to post certain inventory and GL transactions as corrections. The reason for this is that auditors and revenue authorities conduct accounting controls against this rule.  

The purpose of the feature is:  
- To allow the Accounting Manager to enforce corrective posting on desired G/L Accounts  
- To allow the Accounting Manager to enforce corrective posting in Inventory Postings (negative transfer entries, expected costs posting)  
- To allow the Accounting Manager to enforce corrective posting of cancelling in Fixed Assets  
- To allow the user to enforce corrective posting with just one click (G/L, Inventory and Jobs Postings)  

## Statutory Company Information

In the current times, many documents are circulating within and outside company structures. Minimum necessary requirements of such documents are set by local legislations. It is possible to divide such requirements approximately into 3 groups:
- Company officials names need to be present on some internal and external documents
- Document footers – majority of external documents have to contain basic company information in document footers, usually in company’s partner language
- Registration numbers have to be visible in internal and external document

This feature allows users to define company officials and designate them as General Manager, Accounting and Finance Managers for usage in internal and external documents.
Users can define document footers in different languages. Such footers can be used in different reports and documents.

Additional company registration numbers and other registration information can be stored in Company Information and used in documents.

## Internal Financial Documents

Users perform General Ledger operations and must have the possibility to print documents for these operations with layout in compliance with the legal requirements.
Users also want to print a document for posted General Ledger operations.
For the reasons above, this feature provides the following reports:
- General Journal – Test Report is used to print documents from G/L Journals
- General Ledger Document Report is used to print posted General Ledger operations

## Accounting Output Documents  

In order to comply with the legislation, reporting features and local reporting practices of Czech companies, this feature provides the following reports:
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

As one of the most extensively used areas of application for analysis and reporting, Eastern European countries often ask for following improvements of standard Account Schedules feature:
- Common list of expressions – common list of expressions contains named lines which can be used in formulas of all Account Schedules. This is done by defining one of the Account Schedules as a common list of expressions called Shared Account Schedule.
- Saving results (current state) of analysis – this improvement allows user to store results of analysis done by using Account Schedules, modification of results and retrieval of results later on.
- Formulas Drill Down – this improvement allows user to drill down the results of formulas. Drill-down is now accessible for Totalling Type – Formula. Drilling down the result of the formula shows the user a new form containing the list of elements used to calculate results and their description.
- Additional Data Sources – apart from being able to perform analysis on GL Entries, the user can perform analysis on VAT, Customer, Vendor and Value entries.

## Statutory Statements

Companies have to create Financial Statements according to the Accounting Law 563/1991. They have to create the Balance Sheet and the Profit and Loss Statement. 
This feature provides the following reports:

- Balance Sheet 
- Income Statement

These reports use the Account Schedule with the statement structure defined.

The Acc. Schedule Name contains new fields in the Czech version:
- Acc. Schedule Type – Balance Sheet or Income Statement

The Acc. Schedule Line contains new fields in the Czech version:
- Row Correction – link to other line for Balance Sheet setup
- Assets/Liabilities Type – Assets or Liabilities for Balance Sheet setup
- Calc – Always, Never, When positive, When Negative

Balance Sheet and the Profit and Loss Statements are often prepared in Excel file templates with the necessary design for statement printout. Users want to map defined Account Schedules to prepared Excel templates.

For the reasons above, this feature provides the new setup of Excel Templates and Statement File Mapping. Based on this setup users can export Account Schedule data to Excel file.

## WIP Extended Posting

The Czech legal Work in Progress (WIP) posting scheme includes the following new General Ledger Accounts:
- Consumption Account
- Change in Inventory of WIP Account
- Change in Inventory of Product Account  

This feature allows you to correctly perform Czech WIP and Production extended posting. It is therefore possible to set up combination Location and Inventory posting group for the account of Consumption, Work in Progress, Change of Semi-finished Product, Change of Product.
This new posting scheme is used in the following transactions:
- Consumption Posting in the Posting Journal
- Posting the Costs on Capacities in the Output Journal
- Finishing Orders and Auto Reporting

## Additional Finance Features

Use the following table to learn more about the additional finance features that are available for the Czech Republic.


| Topic                                                     | Description                                                  |
| :-------------------------------------------------------- | :----------------------------------------------------------- |
| [Year Closing Operations](year-close-operations.md)                        | To comply with accounting legislation at the end of the fiscal year, certain account books must be closed or opened. |
| [General Ledger Entries Application](general-ledger-entries-application.md)                                    | Apart from application of Customer and Vendor Ledger Entries, a new functionality of General Ledger Entries Application has been introduced. Application of General Ledger Entries is typically used to allow companies to work with temporary and transfer accounts in the General Ledger. |
| [Exchange Rate Updating](exchange-rate-update.md)                                    | Possibility to automatically update currency exchange rates from the external service provided by the ČNB (Czech National Bank). |

## See Also
[Czech Local Functionality](czech-local-functionality.md)