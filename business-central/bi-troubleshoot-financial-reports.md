---
title: Troubleshoot Financial Reporting
description: Describes how to troubleshoot some typical issues in financial reporting.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 01/22/2025
ms.custom: bap-template
ms.search.keywords: bi, power BI, analysis, KPI, account schedule, financial report
ms.search.form: 103_Primary, 104_Primary, 108, 195, 196, 197, 198, 489, 490, 764, 765, 766
ms.service: dynamics-365-business-central
---

# Troubleshoot Financial Reporting

This article provides resolutions to a few typical problems you might encounter within Financial Reporting.

## Balancing reports to the general ledger

When you create new financial reports, you might find that they don't balance to the general ledger. The following are the most likely reasons why.

* A new general ledger account was added to the chart of accounts, but not the financial reporting.
* General ledger accounts are missing from the Totaling accounts.
* General ledger accounts are listed multiple times in the Totaling accounts.
* A formula is missing.
* A formula points to the wrong row number reference.
* A formula doesn't include all the necessary rows.
* A formula includes rows more than one time.
* A formula is making an incorrect calculation.
* A formula incorrectly shows a positive value as negative or a negative value as positive.
* A totaling account is being used on a row instead of a posting account.

## Testing a financial report against Trial Balance reports

After you double-check the possible causes stated in the [Balancing reports to the general ledger](#balancing-reports-to-the-general-ledger) section, if you still have an imbalance, consider running one of the **Trial Balance** reports. These reports can serve as a reference point because they correctly lists all G/L accounts in your chart of accounts and always balance to zero. You can compare this version of the trial balance to the rows of your financial report to identify and correct the error.

When you run the Trial Balance report, fill out the report options as follows for a clean, simple, and balanced report to review.

* In the **Show Comparison** field, choose **Last Year**.
* Turn on the **Actual Balances** toggle.
* In the **Round to** field, choose the lowest value available for your currency.
* Turn on the **Print to Excel** toggle.
* On the **Filter** FastTab, in the **Account Type** field, choose **Posting**.
* In the **Date Filter** field, enter the date for the report. <!--Need a better description here.-->
* Turn off all other toggles and leave all other fields blank.

## Testing a financial report against a data analysis on G/L entries

A different method for testing a financial report than what is described in the [Testing a financial report against Trial Balance reports](#testing-a-financial-report-against-trial-balance-reports) section is to use the data analysis feature on the [General Ledger Entries](https://businesscentral.dynamics.com/?page=20&layout=analysis) page. This allows you to group and summarize amounts by G/L account or G/L account category, and set filters on relevant data properties, such as G/L account, G/L account category, or posting date.

Learn more in [Ad-hoc analysis on finance data](ad-hoc-analysis-finance.md).

## Adding check figures

One way to quickly identify errors in the design of your financial reporting is to add check figures to your row definitions. You want the figure to calculate to zero, which indicates that the report is correct. When you run financial reporting, a quick glance at the check figure can confirm whether the report is correct.

## When to use net change or balance at date

A typical mistake that financial reporting users make is to incorrectly combine row and column definitions. When column definitions use net change as the row type, the columns are most appropriately combined with income statement reports. When column definitions use balance at date as the row type, the columns are most appropriately combined with balance sheet reports.

An easy way to remember this rule of thumb is to think about what the goal of each report is to the viewer. People use balance sheet reports to find account balances of accounts on a certain date. So, using a Balance at Date column definition makes more sense.

People use income statement reports to explore the activity of each account during a period of time. So, using a Net Change column definition makes more sense.

For experienced accountants, we know that in some cases we can apply either report to analyze accounts. We might want to initially review the balance sheet using Balance at Date, but also use Net Change to see how much activity happened in each account as we review trends over time. We might review the Income Statement initially using Net Change to see the trend of activity over time. But we might also look at the Balance at Date of these accounts to see how much accumulated in them throughout the year.

While there isn't a single correct answer for how to use these different views, there are general conventions accountants use when they design reports for other viewers. These conventions are that the Balance Sheet uses Balance at Date, and the Income Statement uses Net Change.

> [!TIP]
> When you create column definitions, might include **BS** or **IS** in the definition description. Those tags can help report viewers decide which reports should use which column definitions.

## Related information

[Prepare financial reporting with financial data and account categories](bi-how-work-account-schedule.md)  
[Design your own financial reports](bi-design-financial-reports.md)  
[Walkthrough: Create custom financial reports](bi-examples-custom-financial-reports.md)  
[Financial analytics overview](bi.md)  