---
title: Column definitions in Financial Reporting
description: Describes how column definitions in financial reporting work.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 03/13/2025
ms.custom: bap-template
ms.search.keywords: bi, power BI, analysis, KPI, account schedule, financial report
ms.search.form: 103, 104, 108, 195, 196, 197, 198, 488_Primary, 489_Primary, 490, 764, 765, 766
ms.service: dynamics-365-business-central
---

# Column definitions in Financial Reporting

Use column definitions to specify the columns to include in a report. For example, you can design a report layout to compare net change and balance for the same period this year and last year. You can have up to 15 columns in a column definition. For example, multiple columns are useful for displaying budgets for 12 months with a column that shows the total.

## Create a new column definition

To create a new column definition, follow these steps:

1. On the **(Financial Report) Column Definitions** page, choose the **New** action.
1. Provide a unique name for the definition.
1. In the **Description** field, provide a descriptive name for the definition. This description provides context when you use the definition, but doesn't show on the report.
1. Provide an internal description for the definition.

## Edit the content of a column definition

To edit the content of a column definition, follow these steps.

> [!NOTE]
> Printed, previewed, and saved versions of a financial report display a maximum of five columns. In contrast, if a financial report is only meant for analysis on the **Financial Report** page, you can create as many columns as you want.

1. On the **(Financial Report) Column Definitions** page, select the definition, and then choose the **Edit Column Definition** action.
1. On the **Column Definition** page, create a row for each column of financial data that should show in the financial report. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
1. Choose **OK**.

> [!TIP]
> Open the **Financial Report** page from time to time to verify that the new column definition works as intended.

## Built-in column definitions

[!INCLUDE[prod_short](includes/prod_short.md)] provides sample column definitions that can help you to quickly get started setting up finance reports that suit your needs.

<!-- update this when we release the new templates in 24.1
| Column definition code | Description | How to use this column definition | 
| ------------------- | ----------- | ------------------------------ | 
| TBA 1 | TBA 1 | TBA 1 |
| TBA 2 | TBA 2 | TBA 2 |
| TBA 3 | TBA 3 | TBA 3 |
| TBA 4 | TBA 4 | TBA 4 |
-->

## Example: Create a column definition to calculate percentages

You might want to include a column in a financial report to calculate percentages of a total. For example, if you have rows that break down sales by dimension, you might want a column to indicate the percentage of total sales in each row.

1. Choose the ![Lightbulb that opens the Tell Me feature 2.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, then choose the related link.
1. On the **Financial Reports** page, select a financial report.  
1. Choose the **Edit Financial Report** action to set up a financial report row to calculate the total on which the percentages are based.  
1. Add a line immediately above the first row for which you want to display a percentage.  
1. Fill in the fields on the line as follows: 
    1. In the **Totaling Type** field, enter **Set Base for Percent**. 
    1. In the **Totaling** field, enter a formula for the total that the percentage is based on. For example, if row 11 contains the total sales, enter **11**.  
1. Choose the **Edit Column Definition** action to set up a column.  
1. Fill in the fields on the line as follows. 
    1. In the **Column Type** field, select **Formula**. 
    1. In the **Formula** field, enter a formula for the amount you want to calculate a percentage for, followed by the percentage sign (%). So, if column number N contains the net change, enter **N%**.  
1. Repeat steps 4 through 7 for each group of rows you want to break down by percentage.

## Comparing accounting periods using period formulas

Your financial report can compare the results of different accounting periods, such as the past month versus the same month last year. To do that, open the **Column Definition** page, and personalize it by adding the **Comparison Period Formula** field as a column. Learn more at [Personalize Your Workspace](ui-personalization-user.md). You can then set that field to a period formula.  

An accounting period doesn't need to match the calendar. However, each fiscal year must have the same number of accounting periods, although each period can be different in length.  

[!INCLUDE[prod_short](includes/prod_short.md)] uses the period formula to calculate the duration of the comparison period in relation to the period represented by the date filter on the report. The comparison period is based on the period of the start date of the date filter. The following table shows the abbreviations for period specifications.

| Abbreviation | Description                                                                           |
| ------------ | ------------------------------------------------------------------------------------- |
| P            | Period.                                                                                |
| LP           | Last period of a fiscal year, half-year, or quarter.                                   |
| CP           | Current period of a fiscal year, half-year, or quarter. Use CP in formulas to set the period that starts or ends the formula. For example, FY\[1..CP\] denotes the time from the beginning of the current fiscal year to the current period.|
| FY           | Fiscal year. For example, FY\[1..3\] denotes the first quarter of the current fiscal year. |

Examples of formulas:

| Formula | Description |
|-----|-----|
| \<Blank\>       | Current period. |
| \-1P            | Previous period.            |
| \-1FY\[1..LP\]  | Entire previous fiscal year.                  |
| \-1FY           | Current period in previous fiscal year.       |
| \-1FY\[1..3\]   | First quarter of previous fiscal year.        |
| \-1FY\[1..CP\]  | From the beginning of the previous fiscal year to the current period in the previous fiscal year, including both periods. |
| \-1FY\[CP..LP\] | From the current period in previous fiscal year to the last period of the previous fiscal year, including both periods.   |

To calculate by regular time periods, enter a formula in the **Comparison Date Formula** field instead. For example, if the field is set to -1Y, [!INCLUDE [prod_short](includes/prod_short.md)] compares to the same period one year earlier.

> [!NOTE]
> It isn't always obvious which periods you're comparing because you can set a date filter on a report that spans dates that are different than the accounting periods in your chart of accounts. So, if you create a financial report where you want to compare this period to the same period last year, set the **Comparison Date Formula** field to **-1FY**. Then, run the report on **February 28th** and set the date filter to **January and February**. As a result, the financial report compares January and February this year to January last year, which is the only completed accounting period of the two for last year.  

Learn more at [Work with Calendar Dates and Times](ui-enter-date-ranges.md).

## Find the reports that use a column definition

[!INCLUDE[prod_short](includes/introduced_in_2025rw1.md)]

Before you change a column definition, it can be helpful to know which reports use it so that you understand the effect of your change. To find out which reports use a column definition, follow these steps:

1. On the **(Financial Report) Column Definitions** page, select the definition, and then choose the **Edit Column Definition** action.
1. To open a list of reports that use the definition, choose the **Where-Used** action.

## Best practices for working with column definitions

<!-- [!INCLUDE [report-best-practices-column-defs](includes/report-best-practices-column-defs2.md)] -->

## Import or export financial report column definitions

Starting with the 2024 release wave 1 (version 24.1), you can import and export financial report column definitions as RapidStart configuration packages. For example, configuration packages are useful for sharing information with other companies. The package is created in a .rapidstart file, which compresses the contents.

> [!NOTE]
> When you import financial report column definitions, they replace existing records with the same names. The configuration package for a report definition won't overwrite any existing row or column definitions that are used in the report definition.

To import or export financial report column definitions, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Column Definitions**, and then choose the related link.
1. Choose the row definition, and then choose the **Import Column Definition** or **Export Column Definition** action, depending on what you want to do.

## Related information
<!-- 
2025w1: add link to administrator article for Financial Report Lifecycle telemetry 
-->

[Row definitions in financial reporting](bi-row-definitions.md)  
[Prepare financial reporting](bi-how-work-account-schedule.md)  
[Financial analytics overview](bi.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
