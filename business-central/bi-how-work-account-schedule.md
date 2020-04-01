---
title: Build financial reports using account schedules
description: Describes how to use account schedules to create various views and report for analyzing financial performance data.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: bi, power BI, analysis, KPI
ms.date: 04/01/2020
ms.author: edupont

---
# Prepare Financial Reporting with Account Schedules and Account Categories
Use account schedules to get insight into the financial data stored in your chart of accounts. Account schedules analyze figures in G/L accounts, and compare general ledger entries with general ledger budget entries. The results display in charts on your Role Center, such as the Cash Flow chart, and in reports, such as the Income Statement and the Balance Sheet reports.

You access these two reports, for example, with the **Financials Statements** action on the Business Manager and Accountant Role Centers.   

[!INCLUDE[d365fin](includes/d365fin_md.md)] provides a few sample account schedules that you can use right away, or you can set up your own rows and columns to specify the figures to compare. For example, you can create account schedules to calculate profit margins on dimensions like departments or customer groups. You can create as many customized financial statements as you want.  

Setting up account schedules requires an understanding of the financial data in the chart of accounts. For example, you can view general ledger entries as percentages of budget entries. This requires that budgets are created. For more information, see [Create G/L Budgets](finance-how-create-budgets.md).

## Account Schedules
Account schedules are used to arrange accounts listed in the chart of accounts in ways suited for presentation of information about those accounts. You can set up various layouts to define the information that you want to extract from the chart of accounts. One of the main functions of account schedules is to provide a place for calculations that cannot be made directly in the chart of accounts, such as creating subtotals for groups of accounts, which can be included in new totals and can then be used in other totals. For example, users can create account schedules to calculate profit margins on such dimensions as departments or customer groups. In addition, general ledger entries and general ledger budget entries can be filtered, for example, by net change or debit amount.

You can also compare two or more account schedules and column layouts by using formulas. This kind of comparison provides the ability to:

* Create customized financial reports.
* Create as many account schedules as needed, each with a unique name.
* Set up various report layouts and print the reports with the current figures.

## G/L Account Categories
You can use G/L account categories to change the layout of your financial statements. After you set up your account categories on the **G/L Account Categories** page, and you choose the **Generate Account Schedules** action, the underlying account schedules for the core financial reports are updated. The next time you run one of these reports, such as the **Balance Statement** report, new totals and subentries are added, based on your changes.

> [!NOTE]
> The top-level account categories, such as the **Liabilities** node are fixed and you cannot add your own. However, you can delete and add account categories at lower levels and change their structure to define how the related account schedule appears in reports.<br /><br />
> It is recommended to create and structure your own lower-level G/L account categories from scratch, in a hierarchy if needed, rather than try to rearrange the existing ones. For example, you can restructure the **Liabilities** node to contain a new **Equity** node followed by the **Current Liabilities** and **Long Term Liabilities** nodes.

## To create a new account schedule  
You use account schedules to analyze figures in general ledger accounts or to compare general ledger entries with general ledger budget entries. For example, you can view the general ledger entries as percentages of the budget entries.

The account schedules in the standard version of [!INCLUDE[d365fin](includes/d365fin_md.md)] are the basis of the standard financial reports, which may not suit the needs of your business. To quickly create your own financial reports, you can start by copying an existing account schedule. See step 3 below.

The **Acc. Schedule Overview** page is where you preview the financial report that the account schedule defines. In the following, it is important to understand that what you set up as account schedule rows and columns can only be seen and validated on the **Acc. Schedule Overview** page, which you open from an account schedule by choosing the **Overview** action. The **Account Schedule** page itself is only a setup area.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Account Schedules**, and then choose the related link.  
2. On the **Account Schedules** page, choose the **New** action to create a new account schedule name.
3. Alternatively, choose the **Copy Account Schedule** action, fill in the two fields, and then choose the **OK** button.
4. Fill in the fields as necessary. In the **Default Column Layout** field select an existing layout. You can edit it later if you want.

    You use column layouts to define columns for different parameters by which the financial data on the rows are shown. For example, you can design a column layout to compare net change and balance for the same period this year and last year, with four columns. For more information, see [To edit a column layout](bi-how-work-account-schedule.md#to-edit-a-column-layout).

5. Choose the **Edit Account Schedule** action.
6. Create a row for each financial element that you want to appear in the report, such as one row for current assets and another row for fixed assets. For inspiration, see existing account schedules in the CRONUS demonstration company.
7. Choose the **Overview** action to see the resulting financial report.
8. On the **Acc. Schedule Overview** page, in the **Column Layout Name** field, select another column layout to see the financial data by other parameters.
9. Choose the **OK** button.

You have now defined the basis of the account schedule, the rows of financial data to be displayed, and an existing layout of columns to show the data on the rows per different parameters. If the default column layout that you selected in step 4 does not suit your purpose, follow the next procedure.

### To edit a column layout
You use column layouts to define what columns should be included in the resulting report. For example, you can design a layout to compare net change and balance for the same period this year and last year.

> [!NOTE]
> A printed/previewed/saved version of an account schedule can display a maximum of five columns. If the account schedule is only meant for analysis on the **Acc. Schedule Overview** page, you can create as many columns as you want.

1. On the **Account Schedules** page, select the relevant account schedule, and then choose the **Edit Column Layout Setup** action.
2. On the **Column Layouts** page, create a row for each column by which financial data is shown in the financial report. [!INCLUDE [tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Choose the **OK** button.
4. Open the **Acc. Schedule Overview** page from time to time to verify that the new column layout works as intended.

> [!NOTE]
> The columns that you define on each row represent columns 3 and up on the **Acc. Schedule Overview** page. The first two columns, **Row No.** and **Description**, are fixed.  

### To create a column that calculates percentages  
Sometimes you may want to include a column in an account schedule to calculate percentages of a total. For example, if you have a number of rows that break down sales by dimension, you may want a column to indicate the percentage of total sales that each row represents.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Account Schedules**, and then choose the related link.
2. On the **Account Schedule Names** page, select an account schedule.  
3. Choose the **Edit Account Schedule** action to set up an account schedule row to calculate the total on which the percentages will be based.  
4. Insert a line immediately above the first row for which you want to display a percentage.  
5. Fill in the fields on the line as follows: In the **Totaling Type** field, enter **Set Base for Percent**. In the **Totaling** field, enter a formula for the total that the percentage will be based on. For example, if row 11 contains the total sales, enter **11**.  
6. Choose the **Edit Column Layout Setup** action to set up a column.  
7. Fill in the fields on the line as follows: In the **Column Type** field, select **Formula**. In the **Formula** field, enter a formula for the amount that you want to calculate a percentage for, followed by %. For example, if column number N contains the net change, enter **N%**.  
8. Repeat steps 4 through 7 for each group of rows that you want to break down by percentage.

## To set up account schedules with overviews  
You can use an account schedule to create a statement comparing general ledger figures and general leger budget figures.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Account Schedules**, and then choose the related link.
2. On the **Account Schedule Names** page, select an account schedule.  
3. Choose the **Edit Account Schedule** action  
4. On the **Account Schedule** page, in the **Name** field, select the default account schedule name.
5. Choose the **Insert Accounts** action.  
6. Select the accounts that you want to include in your statement, and then choose the **OK** button.

    The accounts are now inserted into your account schedule. If you want you can also change the column layout.  
7. Choose the **Overview** action.  
8. On the **Acc. Schedule Overview** page, on the **Dimension Filters** FastTab, set the budget filter to the desired filter name.  
9. Choose the **OK** button.  

Now you can copy and paste your budget statement into a spreadsheet.  

## Comparing Accounting Periods using Period Formulas
Your account schedule can compare the results of different accounting periods, such as this month versus same month last year. To do that, you add a column with the **Comparison Period Formula** field, and then set that field to a period formula.  

An accounting period does not have to match the calendar, but each fiscal year must have the same number of accounting periods, even though each period can be different in length.   

[!INCLUDE[d365fin](includes/d365fin_md.md)] uses the period formula to calculate the amount from the comparison period in relation to the period represented by the date filter on the report request. The comparison period is based on the period of the start date of the date filter. The abbreviations for period specifications are:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Abbreviation</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>P</p></td>
<td><p>Period</p></td>
</tr>
<tr class="even">
<td><p>LP</p></td>
<td><p>Last period of a fiscal year, half-year or quarter.</p></td>
</tr>
<tr class="odd">
<td><p>CP</p></td>
<td><p>Current period of a fiscal year, half-year or quarter.</p></td>
</tr>
<tr class="even">
<td><p>FY</p></td>
<td><p>Fiscal year. For example, FY[1..3] denotes first quarter of the current fiscal year</p></td>
</tr>
</tbody>
</table>

Examples of formulas:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Formula</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;Blank&gt;</p></td>
<td><p>Current period</p></td>
</tr>
<tr class="even">
<td><p>-1P</p></td>
<td><p>Previous period</p></td>
</tr>
<tr class="odd">
<td><p>-1FY[1..LP]</p></td>
<td><p>Entire previous fiscal year</p></td>
</tr>
<tr class="even">
<td><p>-1FY</p></td>
<td><p>Current period in previous fiscal year</p></td>
</tr>
<tr class="odd">
<td><p>-1FY[1..3]</p></td>
<td><p>First quarter of previous fiscal year</p></td>
</tr>
<tr class="even">
<td><p>-1FY[1..CP]</p></td>
<td><p>From the beginning of previous fiscal year to current period in previous fiscal year, inclusive</p></td>
</tr>
<tr class="odd">
<td><p>-1FY[CP..LP]</p></td>
<td><p>From current period in previous fiscal year to last period of previous fiscal year, inclusive</p></td>
</tr>
</tbody>
</table>

If you want to calculate by regular time periods, you must enter a formula in the **Comparison Date Formula** field instead.

> [!NOTE]
> It is not always transparent which periods you are comparing because you can set a date filter on a report that spans different dates than the accounting periods that are reflected in the data in the chart of accounts. For example, you create an account schedule where you want to compare this period with the same period last year, so you set the **Comparison Date Period Filter** field to *-1FY*. Then, you run the report on February 28th and set the date filter to January and February. As a result, the account schedule compares January and February this year to January last year, which is the only completed accounting period of the two for last year.  

## See Related Training at [Microsoft Learn](/learn/modules/configure-financial-reports-dynamics-365-business-central/index)

## See Also
[Business Intelligence](bi.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
