---
title: Troubleshoot Financial Reporting
description: Describes how to troubleshoot some typical issues in financial reporting.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 09/10/2024
ms.custom: bap-template
ms.search.keywords: bi, power BI, analysis, KPI, account schedule, financial report
ms.search.form: 103_Primary, 104_Primary, 108, 195, 196, 197, 198, 489, 490, 764, 765, 766
ms.service: dynamics-365-business-central
---

# Troubleshoot Financial Reporting

This article provides resolutions to a few typical problems.

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

After you double-checking these possible causes, if you still have an imbalance, run the **Trial Balance** report. This report can serve as a reference point because it correctly lists transactions and always balances to zero. You can compare this version of the trial balance to the rows of your financial report to identify and correct the error.

When you run the Trial Balance report, fill out the report options as follows for a clean, simple, and balanced report to review.

* In the **Show Comparison** field, choose **Last Year**.
* Turn on the **Actual Balances** toggle.
* In the **Round to** field, choose the lowest value available for your currency.
* Turn on the **Print to Excel** toggle.
* On the **Filter** FastTab, in the **Account Type** field, choose **Posting**.
* In the **Date Filter** field, enter the date for the report. <!--Need a better description here.-->
* Turn off all other toggles and leave all other fields blank.

## Adding check figures

One way to quickly identify financial reporting design errors is to add check figures to every row definition. When you include a check figure in any row definition, the goal is to have the check figure calculate to zero. This indicates that the report is correct. When you run financial reports, a quick glance at the check figure allows you to confirm the report is correct because the check figure is zero, or that the report is incorrect because its value isn't zero. Check numbers make it easy to discover any new errors in your previously perfect reports. <!--How do you add check figures?-->

## When to use net change or balance at date

A typical mistake that financial reporting users make is to incorrectly combine row and column definitions. It's important to remember that when column definitions are designed using net change as the row type, these columns are most appropriately combined with income statement reports. When column definitions are designed using balance at date as the row type, these columns are most appropriately combined with balance sheet reports.

An easy way to remember this is to think about what the goal of each report is to the viewer.

When we view a balance sheet report, we're looking for the balances of each of these accounts as of a certain date. In this case, viewing the balance sheet with a Balance at Date column definition makes more sense.

When we view an income statement report, we want to explore the activity of each account during a period of time. In this case, viewing the income statement with a Net Change column definition makes more sense.

For experienced accountants, we know that in some cases we can apply either report to analyze accounts. We might want to initially review the balance sheet using Balance at Date, but also use Net Change to see how much activity happened in each account as we review trends over time. We might want to review the Income Statement initially using Net Change, so we can see the trend of activity over time, but then also look at the balance at date of these accounts to see how much has accumulated in them throughout the year.

There is no truly correct answer for how to use these different views, but there are general conventions accountants use when they design reports for other viewers. These conventions are that the Balance Sheet uses Balance at Date, and the Income Statement uses Net Change.

> [!TIP]
> When you create column definitions, might include **BS** or **IS** in the definition description. Those tags can help report viewers decide which reports should use which column definitions.

## See also