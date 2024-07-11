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

If you want more complex reports, financial reporting can also create customized reports. If you already have established financial reporting, choose this option. 

To create a completely new financial report, choose New. You will then be able to give the new report a Name and Description. Once you have created them, you can also assign default Row Definition, Column Definition, and Analysis Views to the report. 

## Copy an existing report

Any existing report may be copied using Copy Financial Report. When choosing this option, you can rename the copied report. Individual Row Definitions and Column Definitions can also be copied and renamed.  

## Create your own row definition

To create your own row definition, choose Edit Row Definition. Drill into the Name field to see all existing row definitions. Choose New and give the new row definition a Name and Description. 

You will now have a blank row definition that you can use to build your new report.  

> [!TIP]
> Take a moment to personalize your screen by showing only the **Row No.**, **Description**, **Totaling Type**, **Totaling**, **Row Type**, and **Bold** columns. These columns are recommended as the minimum necessary columns needed to use for a basic row definition. There are many additional columns available which can be used as you become more familiar with creating more advanced financial reporting in Business Central.

When getting started with financial reporting, there are a few choices we recommended in fields. The following table describes the recommended choices.

|Field  |Option  |
|---------|---------|
|Row No.     |Alpha, numeric, or alphanumeric codes are used here to identify rows in formulas.         |
|Description  |Used to hold the words to label each row of the report.         |
|Totaling Type    |Many choices, with Posting Accounts and Formulas used most commonly.         |
|Totaling     | Together with Totaling Type of Posting Accounts, maps general ledger accounts to the report, either individually or in ranges.<br><br> Together with Totaling Type of Formula, uses row references to Row No. to calculate basic addition, subtraction, multiplication, or division.          |
|Row Type     |**Net Change** is used for Income Statement reports.<br><br>**Balance at Date** is used for Balance Sheet reports.<br><br>**Beginning Balance** is used for Cash Flow Statements.          |
|Bold     |  Simple formatting to apply to headers, subtotals, and other elements of the report that you want to emphasize.       |

## When to show the opposite sign in rows and columns

The formatting option Show Opposite Sign is used for accounts to show the opposite sign in a naturally occurring credit balance account, like revenue, for presentational formatting of reports to be presented to non-accounting readers. 

> [!TIP]
> It's important to remember that Show Opposite Sign should be used on the Posting Account line for the account where the sign needs to be flipped. Using Show Opposite Sign on a formula like Gross Margin, where both Revenue and Cost of Good Sold are represented, will cause an incorrect result to occur in the final calculation. Extra attention must be paid to formulas when using Show Opposite Sign to ensure the calculation is still giving the correct result.

## Create your own column definition

To create your own column definition, choose Edit Column Definition. Drill into the Name field to see all existing column definitions. Choose New and give the new column definition a Name and Description.

You will now have a blank column definition that you can use to build your new report.  

> [!TIP]
> Take a moment to personalize your screen to show only the **Column No.**, **Column Header**, **Column Type**, **Ledger Entry Type**, **Budget Name**, **Formula**, and **Comparison Period Formula** columns. These columns are recommended as the minimum necessary columns needed to use for a basic column definition. There are many additional columns available which can be used as you become more familiar with creating more advanced financial reporting in Business Central.

When getting started with financial reporting, there are a few field choices we recommended. The following table describes the recommendations.

|Field  |Option  |
|---------|---------|
|Column No.     |Alpha, numeric, or alphanumeric codes are used here to identify columns in formulas.         |
|Column Header     |Used to hold the words used to label each column of the report.         |
|Column Type     |Many choices, with Net Change, Balance at Date, and Formula used most commonly.<br><br>**Net Change** is used for Income Statement reports.<br><br>**Balance at Date** is used for Balance Sheet reports. 

Formula uses row references to Column No. to calculate basic addition, subtraction, multiplication, and division.          |
|Ledger Entry Type     |Entries are used for general ledger entries.<br><br>Budget Entries are used for budget entry comparisons.         |
|Budget Name     |When using Budget Entries, selects which Budget to use.         |
|Formula     | Formula uses row references to Column No. to calculate basic addition, subtraction, multiplication, and division.        |
|Comparison Period Formula     | Holds various period related formulas to designate which period will be reported when combined with the date filter when viewing the report.        |

## When to use a comparison period formula and comparison date formula in a column definition

There are two options for column definition comparisons for periods of time: comparison period formula and comparison date formula.  

Comparison Period Formula is most appropriately used for reports created to show monthly, quarterly, or annual time periods. In most cases, financial reports use these increments of time, so the comparison period is used most frequently in financial reporting design.  

Comparison Date Formula is used for reports created to show weekly or daily time periods. These increments of time are more appropriate for operational reporting, like daily sales or weekly invoicing.

### Column definitions that include budgets

Budgets can be included on any report when included on the column definition. By selecting a ledger entry type of Budget Entries, and entering the Budget Name for the selected budget, comparisons of actual to budget can be easily incorporated to reports.