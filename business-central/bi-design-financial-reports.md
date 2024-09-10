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

There are two options for column definition comparisons for periods of time: 

* Comparison period formula
* Comparison date formula

Comparison period formula is most often used for reports that show monthly, quarterly, or annual time periods. In most cases, financial reports use these increments of time, so the comparison period is used most often in financial reports.  

Comparison date formula is used for reports that show weekly or daily time periods. These increments of time are appropriate for operational reporting, such as daily sales or weekly invoicing.

### Column definitions that include budgets

Budgets can be included on any report when included on the column definition. By selecting a ledger entry type of **Budget Entries**, and entering the **Budget Name** for the selected budget, you can easily show comparisons of actual to budget in reports.

## Examples of custom financial reports

The following examples describe how to create the following reports:

* Example 1 creates a Trial Balance report
* Example 2 creates a Balance Sheet report
* Example 3 creates an Income Statement report

### Example 1: Trial Balance

In this example, we have a new financial report called **Trial Balance** and a new row definition called **TB**.

1. Open the new Trial Balance report.
1. Open the **TB** row definition, and choose **Insert**.
1. Choose the **Insert G/L Accounts** action to open the G/L Accounts page.
1. Filter the **Account Type** column to **Posting**.

   > [!TIP]
   > To quickly apply the filter, choose any row that has Posting in the Account Type column, and then right-click the Account Type column header and choose **Filter to this value**.

1. On the first line, choose **Show more options**, and then choose **Select more**.
1. Select all lines by choosing the radio button next to the first column header.
1. Choose **OK** to assign all general ledger accounts with a totaling type of Posting to your row definition.

   > [!TIP]
   > To sum the results of all lines, add a formula on the last line of the row definition. Because this is a trial balance report, the expected result is zero.

Your trial balancer report is now complete. To view the report, choose the report on the Financial Reporting page, and then choose **View Financial Report**. Choose the column definition you prefer for the report. Often used column definitions for a trial balance report are Balance Only, M-Balance, and Default.

> [!TIP]
> If you add a new general ledger account to the chart of accounts, you must update your row definition to include it. Otherwise, your trial balance report won't balance to zero.

### Example 2: Balance Sheet

In this example, we have a new financial report called **Balance Sheet** and a new row definition called **BS**.

1. Open the Balance Sheet report.
1. Open the **BS** row definition.
1. Map the accounts as shown in the following table. This example maps the balance sheet to the chart of accounts in the Cronus demonstration data. Your chart of accounts will be different.

   |Row No.  |Description  |Totaling Type  |Totaling  |Row Type  |Bold  |
   |---------|---------|---------|---------|---------|---------|
   |         | **Current Assets**| Formula |         |Balance at Date          | Yes |
   |CA | Cash                | Posting Accounts | 18000..18999 |Balance at Date|     |
   |CA | Accounts Receivable | Posting Accounts | 15000..15999 |Balance at Date|    |
   |CA |  Other Receivables  | Posting Accounts | 13000..13999 |Balance at Date|    |
   |CA | Inventory           | Posting Accounts | 14000..14999 |Balance at Date|    |
   |CA |Prepaid Expenses     | Posting Accounts | 16000..16999 |Balance at Date|    |
   |CA |Other Current Assets | Posting Accounts | 100000..11999|Balance at Date|    |
   |F1 | **Total Current Assets**  | Formula    |              |Balance at Date|    |
   |   |                           | Formula    |              |Balance at Date|    |
   |   | **Long Term Assets**      |            |              |Balance at Date|Yes |
   |LTA|Fixed Assets         | Posting Accounts| 10000..12899  |Balance at Date|    |
   |LTA|Accumulated Depreciation| Posting Accounts|12900..12999|Balance at Date|    |
   |LTA|Other Long Term Assets | Posting Accounts|17000..17999|19000..19999|Balance at Date||
   |F2 |**Total Long Term Assets**|Formula     |   LTA         |Balance at Date | Yes |
   |   |                          | Formula    |               |Balance at Date |     |
   |F3 | **Total Assets**         |            | F1+F2         | Balance at Date|     |

The following table describes the fields on the **Row Definition** page.

|Field  |Description  |
|---------|---------|
|Row No.      |Simple alpha codes are used for each section to allow for Row No. grouping when using Formulas. This creates shorter and more simple formulas. Each formula line is labeled with a simple alpha numeric code for easy identification.         |
|Description  | Used to hold the words to label each row of the report.        |
|Totaling type| Formula is used in three ways:<br><br>* To add the results of rows together.<br><br>* When combined with a section header or total.<br><br>* When inserting a blank row into the report.<br><br> Posting accounts are used to indicate that the row will pull the result of posted transactions based on the accounts listed in the Totaling column. |
|Totaling | Contains either a range of accounts shown as 10000..11999, or multiple nonconsecutive ranges of accounts shown as 17000..17999\|19000..19999.<br><br> Formulas are expressed as a simple row no. reference as in the case of CA, which will add all accounts with Row No. of CA.<br><br> Following the general accounting convention of displaying financial report lines in the order of liquidity, general ledger accounts initially appear out of order. When reviewing further, you can see that every account is represented in the ranges created for each line. By designing totaling ranges in this way, this report updates dynamically when a new general ledger account is added to the chart of accounts.  |
|Row type     | Balance at Date is used for Balance Sheet reports.        |
|Bold         | Section headers and totals are set to Bold so they stand out.        |

> [!TIP]
> This example shows a summarized balance sheet, where each line is a group of related balance sheet accounts. Your report’s level of summarization is up to you. Good financial report design tries to provide enough detail to tell the story of financial performance without detailing every account. Avoid creating a balance sheet that is a categorized trial balance. It can be hard for people to digest such a large amount of information.

Continue to add balance sheet sections as shown in the following table. You can incorporate your own account groupings to create or replicate your company’s method of displaying accounts.  

The last line of this report is a check figure that the report complies with the accounting equation where Assets = Liabilities + Equity. The result of this check figure should always be zero. If it isn't zero, it's a good indication that there's a problem:

* Some accounts aren't included in the report.
* Accounts might be included more than once.
* A formula in the report isn't calculating correctly.

|Row No.  |Description  |Totaling Type  |Totaling  |Row Type  |Bold  |
|---------|---------    |---------      |--------- |---------|---------|
|| **Current Liabilities**| Formula | |Balance at Date| Yes|
|CL|Accounts Payable|Posting Accounts|22100..22399|Balance at Date||
|CL|Accrued Payroll|Posting Accounts|23500..25399|26100..26399|Balance at Date||
|CL|Accrued Tax|Posting Accounts|23100..23499|Balance at Date||
|CL|Accrued Other|Posting Accounts|26400..29999|Balance at Date||
|CL|Other Current Liabilities|Posting Accounts|22400..23099|25400..26099|Balance at Date||
|F4|**Total Current Liabilities**|Formula|CL|Balance at Date| Yes |
|||Formula||Balance at Date||
||**Long Term Liabilities**|Posting Accounts||Balance at Date| Yes |
|LTL|Notes Payable|Posting Accounts|20000..21299|Balance at Date||
|LTL|Other Long Term Liabilities|Posting Accounts|21300..22099|Balance at Date||
|F5|**Total Long Term Liabilities**|Formula|LTL|Balance at Date| Yes |
|||Formula||Balance at Date||
|F6|**Total Liabilities**|Formula|F4+F5|Balance at Date| Yes |
|||Formula||Balance at date||
||**Equity**|Formula||Balance at Date||
|E|Common Stock|Posting Accounts|30000..30299|Balance at Date||
|E|Retained Earnings|Posting Accounts|30300..39999|Balance at Date||
|E|Current Year Earnings|Posting Accounts|40000..99999|Balance at Date||
|F7|**Total Equity**|Formula|E|Balance at Date||
|||Formula||Balance at Date||
|F8|**Total Liabilities and Equity**|Formula|F6+F7|Balance at Date| Yes |
|||Formula||Balance at Date||
|F9|Check Figure|Formula|F3+F8|Balance at Date||

Your balance sheet financial report is complete. To view the report, choose the report on the Financial Reporting page and select **View Financial Report**. Select any column definition to use with this report. The column definitions that are typically used for a balance sheet are **Balance Only**, **M-Balance**, and **Default**. You can also create a new column definition if you want.

The following image shows the structure of the report in this example.

:::image type="content" source="media/balance sheet report example.png" alt-text="Shows the structure of the balance sheet report"::: 

### Example 3: Income Statement

In this example, we have a new financial report called **Income Statement** and a new row definition called **IS**.

1. Open the **Income Statement** report.
1. Open the **IS** row definition.
1. Map the accounts as shown in the following table. This example maps the balance sheet to the chart of accounts in the Cronus demonstration data. Your chart of accounts will be different.

   |Row No.  |Description  |Totaling Type  |Totaling  |Row Type  |Bold  |
   |---------|---------    |---------      |--------- |---------|---------|
   ||**Revenue**|Formula||Net Change| Yes |
   |R|Product Revenue|Posting Accounts|40000..40209|Net Change|| 
   |R|Job Revenue|Posting Accounts|40410..40429|Net Change||
   |R|Services Revenue|Posting Accounts|40210..40309|40430..40909|Net Change||
   |R|Other Revenue|Posting Accounts|40310..40409|40920..40939|Net Change||
   |R|Discounts and Returns|Posting Accounts|40910..40919|40940..49999|Net Change||
   |F1|**Total Revenue**|Formula|R|Net Change| Yes |
   |||Formula||Net Change||
   ||**Cost of Goods**|Formula||Net Change||
   |C|Materials|Posting Accounts|50000..50209|Net Change||
   |C|Labor|Posting Accounts|50210..59999|Net Change||
   |C|Manufacturing Overhead|Posting Accounts|60000..69999|Net Change||
   |F2|**Total Cost of Goods**|Formula|C|Net Change| Yes |
   |||Formula||Net Change||
   |F3|**Gross Margin USD**|Formula|F1+F2|Net Change| Yes |
   |F4|**Gross Margin %**|Formula|F3/F1*100|Net Change| Yes |

The following table describes the fields on the **Row Definition** page.

|Field  |Description  |
|---------|---------|
|Row No.      |Simple alpha codes are used for each section to allow for Row No. grouping when using Formulas. This creates shorter and more simple formulas. Each formula line is labeled with a simple alpha numeric code for easy identification.         |
|Description  | Used to hold the words to label each row of the report.        |
|Totaling type| Formula is used in three ways:<br><br>* To add the results of rows together.<br><br>* When combined with a section header or total.<br><br>* When inserting a blank row into the report.<br><br> Posting accounts are used to indicate that the row will pull the result of posted transactions based on the accounts listed in the Totaling column. |
|Totaling | Contains either a range of accounts shown as 40000..40209, or multiple nonconsecutive ranges of accounts shown as 40210..40309\|40430..40909.<br><br> Formulas are expressed as a simple row no. reference as in the case of CA, which will add all accounts with Row No. of CA.<br><br> Following the general accounting convention of displaying financial report lines in the order of liquidity, general ledger accounts initially appear out of order. When reviewing further, you can see that every account is represented in the ranges created for each line. By designing totaling ranges in this way, this report updates dynamically when a new general ledger account is added to the chart of accounts.  |
|Row type     | Balance at Date is used for Balance Sheet reports.        |
|Bold         | Section headers and totals are set to Bold so they stand out.        |

> [!TIP]
> This example shows a summarized income statement, where each line is a group of related incomes statement accounts. Your report’s level of summarization is up to you. Good financial report design attempts to provide enough detail to tell the story of financial performance without detailing every account. Avoid creating an income statement that's a categorized trial balance. It can be hard for people to digest such a large amount of information.

Continue to add balance sheet sections as shown in the following table. You can incorporate your own account groupings to create or replicate your company’s method of displaying accounts.  

The last line of this report is a check figure that the report complies with the accounting equation where Assets = Liabilities + Equity. The result of this check figure should always be zero. If it isn't zero, it's a good indication that there's a problem:

* Some accounts aren't included in the report.
* Accounts might be included more than once.
* A formula in the report isn't calculating correctly.

|Row No.  |Description  |Totaling Type  |Totaling  |Row Type  |Bold  |
|---------|---------    |---------      |--------- |---------|---------|
||**Operating Expense**|Formula||Net Change| Yes |
|OE|Salaries and Wages|Posting Accounts|70000..72109|Net Change||
|OE|Employee Benefits|Posting Accounts|72110..73299|Net Change||
|OE|Employee Insurance|Posting Accounts|73300..74109|Net Change||
|OE|Employee Tax|Posting Accounts|74110..79999|Net Change||
|OE|Depreciation|Posting Accounts|80000..89999|Net Change||
|OE|Other Expense|Posting Accounts|90000..99999|Net Change||
|F5|**Total Operating Expense**|Formula|OE|Net Change| Yes |
|||Formula||Net Change||
|F6|**Net (Income) / Loss**|Formula|F1+F2+F5|Net Change||
|||Formula||Net Change||
|F7|Total of Income Statement|Posting Accounts|40000..99999|Net Change||
|F8|Check Figure|Formula|F6-F7|Net Change||

Your income statement report is complete. To view the report, choose the report on the Financial Reporting page, and select **View Financial Report**. Select any column definition you like to use with this report. The often used column definitions for a balance sheet are **M-NetChang** and **PTD + YTD**. You can also create a new column definition.

The following image shows the structure of the report in this example.

:::image type="content" source="media/income statement report.png" alt-text="Shows the structure of the income statement report.":::

## See also

[Primary capabilities of financial reporting](finance-financial-reporting-capabilities.md)  
[Organize report data using account categories](bi-account-categories.md)  
