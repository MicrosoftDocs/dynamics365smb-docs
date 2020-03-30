---
title: Set Up Financial Processes| Microsoft Docs
description: Learn about the tasks to set up finance in your business to suit all your accounting, auditing, or bookkeeping needs.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: accounting, auditing, bookkeeping
ms.date: 04/01/2020
ms.author: sgroespe

---
# Setting Up Finance
Before you can begin to run your business, you must specify rules and defaults for how you want to manage finance processes for that company. You start by setting up the core of the company's accounting records - the chart of accounts. Then you set up posting groups, which makes the process of assigning default general ledger posting accounts to customers, vendors, and items more efficient.

Some finance setup can be done automatically with assisted setup guides, and some must be done manually. For more information, see [Getting Ready for Doing Business](ui-get-ready-business.md).

You can use dimensions to add different types of information to every transaction. You can set up your company's basic dimensions, such as Projects and Departments. Later, you can add more dimensions when you need them, and you can set up temporary dimensions for use during a limited time period, for example, in connection with a sales campaign. For more information, see [Working with Dimensions](finance-dimensions.md).

Many of the setup tasks must be completed before you can begin recording financial transactions, but most settings can be changed at a later date. Some of the set up tasks are optional, for example, you only set up Intercompany Postings and Consolidations if you are working with multiple companies. Some setup tasks, such as specifying the period during which posting is allowed, may have to be repeated periodically.  

The following table describes a sequence of tasks, with links to the topics that describe them.

| To | See |
| --- | --- |
| Choose how you pay your vendors. |[Defining Payment Methods](finance-payment-methods.md) |
| Specify the posting groups that map entities like customers, vendors, items, resources, and sales and purchase documents to general ledger accounts. |[Setting Up Posting Groups](finance-posting-groups.md)|
|Create account schedules and define account categories to define the contents of financial charts and reports, such as the Balance Sheet and Income Statement reports.|[Prepare Financial Reporting with Account Schedules and Account Categories](bi-how-work-account-schedule.md)|
|Set up a tolerance by which the system closes an invoice even though the payment, including any discount, does not fully cover the amount on the invoice.|[Work with Payment Tolerances and Payment Discount Tolerances](finance-payment-tolerance-and-payment-discount-tolerance.md)|
| Set up fiscal periods. |[Work with Accounting Periods and Fiscal Years](finance-accounting-periods-and-fiscal-years.md) |
| Define how you report value-added tax amounts that you have collected for sales to the tax authorities. |[Set Up Value-Added Tax (VAT)](finance-setup-vat.md)|
|Prepare to handle unrealized VAT in connection with cash-based accounting methods.|[Set Up Unrealized VAT for Cash-Based Accounting](finance-setup-unrealized-vat.md)|
| Set your Sales and Purchases features up to handle payments in foreign currencies.|[Enable Application of Ledger Entries in Different Currencies](finance-how-enable-application-ledger-entries-different-currencies.md)
|Define one or more additional currencies so that amounts are automatically reported in both LCY and an additional reporting currency on each G/L entry and on other entries.|[Set Up an Additional Reporting Currency](finance-how-setup-additional-currencies.md)|
|Periodically adjust additional currency equivalents to make up for fluctuating exchange rates.|[Update Currency Exchange Rates](finance-how-update-currencies.md)|
|Define multiple interest rates to be used for different periods for delayed payments in trade transactions.|[Set Up Multiple Interest Rates](finance-how-to-set-up-multiple-interest-rates.md)|
|Prepare to round invoice amounts automatically when you create invoices.|[Set Up Invoice Rounding](finance-set-up-invoice-rounding.md)|
| Add new accounts to the existing chart of accounts. |[Setting Up the Chart of Accounts](finance-setup-chart-accounts.md) |
| Set up business intelligence (BI) charts to analyze cash flow. |[Setting Up Cash Flow Analysis](finance-setup-cash-flow-analyses.md) |
|Enable invoicing of a customer who is not set up in the system.|[Set Up Cash Customers](finance-how-to-set-up-cash-customers.md)|
| Set up Intrastat reporting, and submit the report to an authority | [Set Up and Report Intrastat](finance-how-setup-report-intrastat.md)|
|Make sure an entry in a general journal is allocated to several different accounts when you post the journal, either quantity, percentage, or amount.|[Use Allocation Keys in General Journals](ui-how-use-allocation-keys-general-journals.md)|

## See Related Training at [Microsoft Learn](/learn/paths/set-up-financial-management-dynamics-365-business-central/)

## See Also
[Finance](finance.md)  
[Reconciling Bank Accounts](bank-manage-bank-accounts.md)  
[Working with Dimensions](finance-dimensions.md)  
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Analyzing Cash Flow in Your Company](finance-analyze-cash-flow.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
