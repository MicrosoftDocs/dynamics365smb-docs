---
title: Use Statistical Accounts to Analyze Non-Transactional Data
description: Describes how to use statistical accounts as another source of data for your analyses.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 03/07/2023
ms.custom: bap-template
ms.search.keywords: bi, power BI, analysis, KPI, financial report
ms.search.form: 2632_Primary, 2631, 2633, 2623, 2634
ms.service: dynamics-365-business-central
---
# Analyze Data with Statistical Accounts

Use statistical accounts to supplement information in financial reports. Statistical accounts let you add metrics that are based on non-transactional data. You add the non-transactional data as number-based units, such as:

* Employee headcount
* Square footage
* The number of customers with overdue accounts

For example, you can measure revenue or costs based on the number of people in a department. The headcount for the department is the unit for the statistical account. The following image shows an example of a report that uses a statistical account to show revenue per employee.

:::image type="content" source="media/statistical account report example.png" alt-text="An example of a report that includes data from a statistical account.":::

In terms of how they work, statistical accounts are similar to posting accounts. They store transactions that you post using statistical account journals, so that you can use the transactions as data for financial reports. To learn more about financial reports, go to [Prepare Financial Reporting with Financial Data and Account Categories](bi-how-work-account-schedule.md). 

There are a couple of key differences between statistical accounts and posting accounts. Statistical accounts are separate entities, and aren't included in trial balance reports. Also, you don't need to balance debit and credit amounts when you use statistical account journals to post entries to a statistical account. You just post the amount.

## Set up a statistical account

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Statistical Accounts**, then choose the related link.
1. On the **General** FastTab, fill in the fields. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## Post amounts to a statistical account

1. To post the amounts you want to track, on the **Statistical Accounts** page, choose the **Statistical Accounts Journal** action.
1. In the **Posting date** field, enter the last date of the posting period that you want to post amounts for.
1. Optional: If you want to track amounts for a specific document, in the **Document No.** field, enter the document's ID.
1. In the **Statistical Account No.** field, choose the statistical account that you'll post amounts to.
1. In the **Description** field, enter a brief description of what you're measuring.  
1. In the **Amount** field, enter the amount to post. 
1. Optional: If you'll want to include the statistical account in more advanced analyses, specify dimensions in the **Department Code** and **Customergroup Code** fields. To learn more about dimensions, go to [Analyze Data by Dimensions](bi-how-analyze-data-dimension.md).

## Verify statistical account amounts

On the **Statistical Accounts** page, use the **Statistical Accounts Balance** action to verify that the registered amounts are correct for each period.  

## Include the statistical account in a financial report

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Financial Reports**, then choose the related link.
1. Create a new financial report in one of the following ways:
    1. To start from scratch, choose **New**. To learn more about creating financial reports, go to [Create a new financial report](bi-how-work-account-schedule.md#create-a-new-financial-report).
    1. To use settings from a similar report you already have, choose the report to copy, and then choose the **Copy Financial Report** action. You can edit the settings you copy in your new report.
1. Add the statistical account:
    1. If you're starting from scratch, choose the **Edit Row Definition** action.
    1. To use a row definition from an existing report, choose the report to copy from, and then choose the **Copy Row Definition** action.
1. On the **Row Definition** page, in the **Row No.** field, define where the row will appear in the sequence of rows on the report.
1. In the **Description** field, enter text that indicates what you're measuring.
1. In the **Totaling Type** field, choose **Statistical Accounts**.
1. In the **Totaling** field, choose a statistical account.
1. In the **Row Type** field, choose whether to view the balance on the posting date or the beginning of the posting period, or to show the change to the amount during the period.
1. Fill in the remaining fields. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## Related information

[Prepare Financial Reporting with Financial Data and Account Categories](bi-how-work-account-schedule.md)  
[Financial analytics overview](bi.md)  