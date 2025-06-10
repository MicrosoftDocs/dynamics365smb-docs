---
title: Set up financial processes
description: Learn about the tasks required to set up finance in your business to suit all your accounting, auditing, or bookkeeping needs.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.form: 118_Primary
ms.search.keywords: accounting, auditing, bookkeeping
ms.date: 06/10/2025
ms.service: dynamics-365-business-central
---
# Setting up finance

Before you can begin to run your business, you must specify how you want to manage company finance processes. First, you set up the core of the company's accounting records: the chart of accounts (COA). Then you set up posting groups, which make the process of assigning default general ledger posting accounts to customers, vendors, and items more efficient.

Some finance setup can be done automatically with assisted setup guides, and some must be done manually. Learn more at [Getting Ready for Doing Business](ui-get-ready-business.md). The **General Ledger Setup** page specifies how to handle of your company's different accounting processes. For example, use this page to specify invoice rounding details, the currency code for your local currency, address formats, and whether you want to use an additional reporting currency. Learn more at [Understanding the General Ledger and the Chart of Accounts](finance-general-ledger.md).  

You can use dimensions to add different types of information to every transaction. You can set up your company's basic dimensions, such as *Projects* and *Departments*. Later, add more dimensions when you need them. For example, you can set up temporary dimensions to use for a limited time period, such during a sales campaign. Learn more at [Working with Dimensions](finance-dimensions.md).

Many of the setup tasks must be completed before you can begin recording financial transactions, but most settings can be adjusted as needed. That said, there are optional setup tasks as well. For example, you need only set up intercompany postings and consolidations if you are working with multiple companies. And other setup tasks, such as specifying the period during which posting is allowed, may have to be repeated periodically.  

The following table describes a sequence of tasks, with links to the topics that describe them.

| To... | Go to... |
| --- | --- |
|View or edit general ledger accounts to which all general ledger entries are posted|[Set Up or Change the Chart of Accounts](finance-setup-chart-accounts.md)|
| Specify how you want to be paid by customers, and how you want to pay your vendors. |[Set Up Payment Methods](finance-payment-methods.md) |
| Specify payment terms to manage due dates and calculate possible payment discounts.|[Set Up Payment Terms](finance-payment-terms.md) |
| Specify the posting groups that map entities like customers, vendors, items, resources, and sales and purchase documents to general ledger accounts. |[Set Up Posting Groups](finance-posting-groups.md)|
|Create financial reports and define account categories that determine the contents of financial charts and reports, such as the Balance Sheet and Income Statement reports.|[Prepare Financial Reporting with Financial Data and Account Categories](bi-how-work-account-schedule.md)|
|Set up a tolerance by which the system closes an invoice even if the payment, including any discount, does not fully cover the amount on the invoice.|[Work with Payment Tolerances and Payment Discount Tolerances](finance-payment-tolerance-and-payment-discount-tolerance.md)|
| Set up fiscal periods. |[Work with Accounting Periods and Fiscal Years](finance-accounting-periods-and-fiscal-years.md) |
|Set up invoice terms that remind your customers to make payment.|[Set Up Reminder Terms and Levels](finance-setup-reminders.md)|
| Define how you report value-added tax (VAT) amounts collected for sales to the tax authorities. |[Set Up Value-Added Tax (VAT)](finance-setup-vat.md)|
|Prepare to handle unrealized VAT in connection with cash-based accounting methods.|[Set Up Unrealized VAT for Cash-Based Accounting](finance-setup-unrealized-vat.md)|
|Define the foreign currencies you trade in or report transactions in.|[Set Up Currencies](finance-set-up-currencies.md)|
| Set up your Sales and Purchases features to handle payments in foreign currencies.|[Enable Application of Ledger Entries in Different Currencies](finance-how-enable-application-ledger-entries-different-currencies.md)
|Define one or more additional currencies so amounts are automatically reported in both local currency (LCY) and an additional reporting currency on each general ledger (G/L) entry and on other entries.|[Set Up an Additional Reporting Currency](finance-how-setup-additional-currencies.md)|
|Periodically adjust additional currency equivalents to make up for fluctuating exchange rates.|[Update Currency Exchange Rates](finance-how-update-currencies.md)|
|Define multiple interest rates to use for different periods for delayed payments in trade transactions.|[Set Up Multiple Interest Rates](finance-how-to-set-up-multiple-interest-rates.md)|
|Arrange for amounts to be automatically rounded as invoices are created.|[Set Up Invoice Rounding](finance-set-up-invoice-rounding.md)|
| Set up business intelligence (BI) charts to analyze cash flow. |[Setting Up Cash Flow Analysis](finance-setup-cash-flow-analyses.md) |
|Enable invoicing of a customers not set up in the system.|[Set Up Cash Customers](finance-how-to-set-up-cash-customers.md)|
| Set up Intrastat reporting, and submit the report to an authority. | [Set Up and Report Intrastat](finance-how-setup-report-intrastat.md)|
|Ensure a journal entry is allocated between different accounts, such as quantity, percentage, or amount, when you post it to the journal.|[Use Allocation Keys in General Journals](ui-how-use-allocation-keys-general-journals.md)|
|Set up source codes and reason codes to help track audit trails.|[Setting Up Source Codes and Reason Codes for Audit Trails](finance-setup-trail-codes.md)|
| Set up audit on changes to your finance setup | [Audit changes to your setup](across-setup-auditing.md) |
|Specify default reports to be used for different document types.|[Report Selection in Business Central](across-report-selections.md)|

> [!TIP]
> Depending on your geographical location, some Business Central pages may contain fields that are not described in the articles listed above because they apply to local functionality or customizations. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

## Related information

[Finance](finance.md)  
[Reconciling Bank Accounts](bank-manage-bank-accounts.md)  
[Work with Dimensions](finance-dimensions.md)  
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Analyzing Cash Flow in Your Company](finance-analyze-cash-flow.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
