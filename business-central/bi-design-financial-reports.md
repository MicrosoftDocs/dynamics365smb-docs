---
title: Design your own financial reports
description: Learn how to structure and design custom financial reports.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 07/11/2024
ms.custom: bap-template
ms.search.keywords: bi, power BI, analysis, KPI, account schedule, financial report
ms.search.form: 108, 490, 790
ms.service: dynamics-365-business-central
---

# Design your own financial reports

You can use financial reporting to create custom reports. For example, if you want more complex reports.

To create a new financial report, choose the **New** action. You can then give the report a name and add a description. Afterward, you can specify default settings for the report, such as:

* **Row Definition**
* **Column Definition**
* **Analysis Views**

## Copy an existing report

To copy an existing report, use the **Copy Financial Report** action. When you choose this option, you can rename the copied report. You can also copy and rename individual row definitions and column definitions.  

## Create your own row definition

To create your own row definition, choose **Edit Row Definition**. To explore existing row definitions, choose the **Name** field. Choose **New**, and give the row definition a name and description.

You now have a blank row definition that you can use to build your new report.  

> [!TIP]
> Take a moment to personalize your screen to show only the **Row No.**, **Description**, **Totaling Type**, **Totaling**, **Row Type**, and **Bold** columns. These columns are recommended as the minimum columns needed for a basic row definition. There are many columns available, which can be used as you become familiar with creating more advanced financial reports in [!INCLUDE [prod_short](includes/prod_short.md)].

When getting started with financial reporting, there are a few choices we recommended in fields. The following table describes the recommended choices.

|Field  |Option  |
|---------|---------|
|Row No.     |Alpha, numeric, or alphanumeric codes are used here to identify rows in formulas.         |
|Description  |Specifies the words to label each row of the report.         |
|Totaling Type    |The **Posting Accounts** and **Formulas** options are often used.         |
|Totaling     | Together with the **Totaling Type** of **Posting Accounts**, maps general ledger accounts to the report, either individually or in ranges.<br><br> Together with **Totaling Type** of the **Formula**, uses row references to the **Row No.** field to do basic addition, subtraction, multiplication, or division.          |
|Row Type     |**Net Change** is used for income statement reports.<br><br>**Balance at Date** is used for balance sheet reports.<br><br>**Beginning Balance** is used for cash flow statements.          |
|Bold     |  Simple formatting to apply to headers, subtotals, and other elements of the report that you want to emphasize.       |

## When to show the opposite sign in rows and columns

Use the **Show Opposite Sign** option to show the opposite sign in a credit balance account, such as revenue, for reports you present to people who aren't accountants.

> [!TIP]
> It's important to remember that you should use the **Show Opposite Sign** option on the posting account line for the account where the sign needs to be flipped. If you use the option on a formula such as gross margin, where both revenue and cost of goods sold are represented, the calculation will be incorrect. Pay extra attention when you use the setting in formulas.

## Create your own column definition

To create your own column definition, choose **Edit Column Definition**. To explore existing definitions, choose the **Name** field. Choose **New**, and give the new column definition a name and a description.

You now have a blank column definition that you can use to build your new report.  

> [!TIP]
> Take a moment to personalize your screen to show only the **Column No.**, **Column Header**, **Column Type**, **Ledger Entry Type**, **Budget Name**, **Formula**, and **Comparison Period Formula** columns. These columns are recommended as the minimum needed for a basic column definition. There are many columns available, which you can use as you become more familiar with creating advanced financial reports.

When getting started with financial reporting, there are a few field choices we recommended. The following table describes the recommendations.

|Field  |Option  |
|---------|---------|
|Column No.     |Alpha, numeric, or alphanumeric codes are used here to identify columns in formulas.         |
|Column Header     |Used to hold the words used to label each column of the report.         |
|Column Type     |The often used options are **Net Change**, **Balance at Date**, and **Formula**.<br><br>**Net Change** is used for income statement reports.<br><br>**Balance at Date** is used for balance sheet reports.<br><br>**Formula** uses row references to Column No. to do basic addition, subtraction, multiplication, and division.          |
|Ledger Entry Type     |Entries are used for general ledger entries.<br><br>**Budget Entries** are used for budget entry comparisons.         |
|Budget Name     |When using budget entries, select the budget to use.         |
|Formula     | Formula uses row references to Column No. to do basic addition, subtraction, multiplication, and division.        |
|Comparison Period Formula     | Holds various period-related formulas that determine the period for the report combined with the date filter.        |

## When to use a comparison period formula and comparison date formula in a column definition

There are two options for column definition comparisons for accounting periods:

* Comparison period formula
* Comparison date formula

Comparison period formula is often used for reports that show monthly, quarterly, or annual accounting periods. In most cases, financial reports use these increments of time.  

Comparison date formula is typically used for reports that show weekly or daily accounting periods. These increments of time are appropriate for operational reporting, such as daily sales or weekly invoicing.

### Column definitions that include budgets

Budgets can be included on any report when included on the column definition. By selecting a ledger entry type of **Budget Entries**, and entering the **Budget Name** for the selected budget, you can easily show comparisons of actual to budget in reports.

## Related information

[Examples of custom financial reports](bi-examples-custom-financial-reports.md)  
[Organize report data using account categories](bi-account-categories.md)  
[Primary capabilities of financial reporting](finance-financial-reporting-capabilities.md)  
[Financial analytics overview](bi.md)   