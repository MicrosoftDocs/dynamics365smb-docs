---
title: Build Financial Reports Using Financial Data and Account Categories
description: Describes how to use financial reports to create various views and reports for analyzing financial performance data.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bnielse
ms.topic: how-to
ms.date: 03/27/2024
ms.custom: bap-template
ms.search.keywords: bi, power BI, analysis, KPI, account schedule, financial report
ms.search.form: 103, 104, 108, 195, 196, 197, 198, 489, 490, 764, 765, 766
ms.service: dynamics-365-business-central
---
# Prepare financial reporting with financial data and account categories

The **Financial Reports** feature gives you insights into the financial data shown on your chart of accounts (COA). You can set up financial reports to analyze figures in general ledger (G/L) accounts, and compare general ledger entries with budget entries. The results display in charts and reports in your Role Center, such as the Cash Flow chart, and the Income Statement and Balance Sheet reports. You access these two reports, for example, with the **Financial Statements** action in the Business Manager and Accountant home pages.  

[!INCLUDE[prod_short](includes/prod_short.md)] provides sample financial reports you can use right away as templates. You can also set up your own reports to specify the figures to compare. For example, you can create financial reports to calculate profit margins using dimensions such as departments or customer groups. The number of financial reports you can create is unlimited and require no involvement of a developer.  

## Prerequisites for financial reporting

Setting up financial reports requires an understanding of the structure of your chart of accounts. There are three key concepts that you likely need to pay attention to before you design your financial reports:

- Map G/L posting accounts to G/L account categories.
- Design how you use dimensions.
- Set up G/L budgets.

G/L account categories simplify your financial report definitions and make them more resiliant to changes in the chart of accounts structure. Learn more at [Use G/L account categories to change the layout of your financial statements](#use-gl-account-categories-to-change-the-layout-of-your-financial-statements).

Setting up dimensions allows you to slice and dice your financial data in ways that make sense for your organization. Learn more at [Work with Dimensions](finance-dimensions.md). 

If you want to view general ledger entries as percentages of budget entries, you must create G/L budgets. Learn more at [Create G/L Budgets](finance-how-create-budgets.md).

## Financial reports

Financial reports arrange accounts from your chart of accounts in ways that make data easier to present. You can set up various layouts to define the information you want to extract from the chart of accounts. Financial reports also provide a place for calculations that can't be made directly in the chart of accounts. For example, you can create subtotals for groups of accounts and then include that total in other totals. Another example is to calculate profit margins on dimensions such as departments or customer groups. Additionally, you can filter general ledger entries and budget entries, for example, by net change or debit amount.

> [!NOTE] 
> Mathematically, think of a financial report as defined by two things:
>
> - A vector of row definitions that define what needs to be calculated.
> - A vector of column definitions that defines the data for the calculation.
>
> The financial report is then the outer product of these two vectors, where each cell value is calculated according to the formula in the row applied to the data definition from the column.

:::image type="content" source="media/financial-report-definition.svg" alt-text="Shows how a financial report is constructed from a row definition and a column definition." lightbox="media/financial-report-definition.svg":::

The **Financial Reports** page shows how all financial reports follow a pattern that consists of the following attributes:

* Name (code)
* Description
* Row definition
* Column definition

:::image type="content" source="media/financial-reports.png" alt-text="Shows how all financial reports is constructed from a row definition and a column definition." lightbox="media/financial-reports.png":::

> [!NOTE]
> The sample finance reports in [!INCLUDE[prod_short](includes/prod_short.md)] aren't ready to use out-of-the box. Depending of the way you set up your G/L accounts, dimensions, G/L account categories, and budgets, you need to adjust the sample row and column definitions and the finance reports they're used in to match your setup.

You can also use formulas to compare two or more financial reports and column definitions. Comparisons let can do the following things:

* Create customized financial reports.
* Create as many financial reports as you need, each with a unique name.
* Set up various report layouts and print the reports with the current figures.

## Learning path: Create financial reports in Microsoft Dynamics 365 Business Central

Want to learn how to create budgets, and then use financial reports, dimensions, and row and column definitions to generate the financial reports that are typically needed for most businesses?

Start learning in the learning path [Create financial reports in Microsoft Dynamics 365 Business Central](/training/paths/create-financial-reports-dynamics-365-business-central)

## Create a new financial report

You use financial reports to analyze general ledger accounts or to compare general ledger entries with budget entries. For example, you can view the general ledger entries as percentages of the budget entries.

The financial reports in the standard version of [!INCLUDE[prod_short](includes/prod_short.md)] might not suit your business needs. To quickly create your own financial reports, start by copying an existing one, as described in step three below.

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, then choose the related link.  
1. On the **Financial Reports** page, choose the **New** action to create a new financial report name. Alternatively, to reuse settings from an existing financial report, choose the **Copy Financial Report** action.
1. Fill in the report short name (this can't be changed) and description.
1. Choose a row definition and a column definition.
1. Optionally, choose analysis views for the row and column definitions.
1. Choose the **Edit Financial Report** action to access more properties on the financial report.
1. On the **Options** FastTab, you can edit the report description, change the row and column definitions, and define how to show dates. Dates can be a Day/Week/Month/Quarter/Year hierachy, or use accounting periods. To learn more, go to [Comparing accounting periods using period formulas](#comparing-accounting-periods-using-period-formulas).
1. On the **Dimensions** FastTab, you can define dimension filters for the report.
1. You can preview the report in the area below the **Dimensions** FastTab.

> [!TIP]
> After you create a financial report, you can use the **Financial Report** page to preview and validate it. To open the page, choose the **View Financial Report** action.  

> [!NOTE]
> When you open a financial report in View or Edit mode, the Filter pane is available. Don't use the Filter pane to set filters for the data in your report. Such filters can cause errors or might not actually filter the data. Instead, use the fields on the **Options** and **Dimensions** FastTabs to set up filters for the report.

### Create or edit a row definition

Row definitions in financial reports provide a place for calculations that can't be made directly in the chart of accounts. For example, you can create subtotals for groups of accounts and then include that total in other totals. You can also calculate intermediate steps that aren't shown in the final report.

1. On the **Financial Reports** page, select the relevant financial report, and then choose the **Edit Row Definition** action.
1. Choose the **Insert G/L Accounts**, **Insert CF Accounts**, and **Insert Cost Types** actions to create a row for each financial element you want to analyze. For example, you might have one row for current assets and another row for fixed assets. For inspiration, explore the financial reports in the CRONUS demonstration company.

    > [!NOTE]
    > The **Row No.** field shows the first 10 characters of an identifier, such as an account number. If you add elements with identifiers that start with the same 10 characters, you'll have duplicates in the **Row No.** field. If needed, you can manually edit the identifiers after you insert the elements. The full identifiers are displayed in the **Totaling** field.

> [!NOTE]
> The columns you define on each line in the row definition represent columns three and up on the **Financial Report** page. The first two columns, **Row No.** and **Description**, are fixed.  

### Create or edit a column definition

Use column definitions to specify the columns to include in the report. For example, you can design a report layout to compare net change and balance for the same period this year and last year. You can have up to 15 columns in a column definition. For example, multiple columns are useful for displaying budgets for 12 months with a column that shows the total.

> [!NOTE]
> A printed/previewed/saved version of a financial report displays a maximum of five columns. In contrast, if a financial report is only meant for analysis on the **Financial Report** page, you can create as many columns as you want.

1. On the **Financial Reports** page, select the relevant financial report, then choose the **Edit Column Definition** action.
1. On the **Column Definition** page, create a row for each column of financial data shown in the financial report. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
1. Choose **OK**.
1. Open the **Financial Report** page from time to time to verify the new column definition works as intended.

### Create a column definition to calculate percentages

You might want to include a column in a financial report to calculate percentages of a total. For example, if you have rows that break down sales by dimension, you may want a column to indicate the percentage of total sales in each row.

1. Choose the ![Lightbulb that opens the Tell Me feature 2.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, then choose the related link.
1. On the **Financial Reports** page, select a financial report.  
1. Choose the **Edit Financial Report** action to set up a financial report row to calculate the total on which the percentages are based.  
1. add a line immediately above the first row for which you want to display a percentage.  
1. Fill in the fields on the line as follows: In the **Totaling Type** field, enter **Set Base for Percent**. In the **Totaling** field, enter a formula for the total the percentage will be based on. For example, if row 11 contains the total sales, enter **11**.  
1. Choose the **Edit Column Definition** action to set up a column.  
1. Fill in the fields on the line as follows. In the **Column Type** field, select **Formula**. In the **Formula** field, enter a formula for the amount you want to calculate a percentage for, followed by the percentage sign (%). So, if column number N contains the net change, enter **N%**.  
1. Repeat steps 4 through 7 for each group of rows you want to break down by percentage.

## Use G/L account categories to change the layout of your financial statements

You can use G/L account categories to change the layout of your financial statements. For example, after you set up your account categories on the **G/L Account Categories** page, you can choose the **Generate Financial Reports** action and update the underlying financial reports for the core financial reports. The next time you run one of these reports, such as the **Balance Statement** report, new totals and subentries are added.

Another benefit of using G/L account categories over the raw G/L accounts in your row definitions is that a change in your chart of accounts structure doesn't affect your financial reports.

> [!NOTE]
> The top-level account categories, such as the **Liabilities** node, are fixed and you can't add your own. However, you can delete and add account categories at lower levels and define how the related financial report appears in reports.
>
> You should create and structure your own lower-level G/L account categories from scratch, in a hierarchy if needed, rather than try to rearrange the existing ones. For example, you can restructure the **Liabilities** node to contain a new **Equity** node followed by the **Current Liabilities** and **Long Term Liabilities** nodes. Learn more at [Mapping general ledger accounts to account categories](finance-general-ledger.md#account-categories).

## Using dimensions in financial reports

In financial analysis, a dimension is data you add to an entry as a kind of marker. This data is used to group entries with similar characteristics, such as customers, regions, products, and salesperson, and easily retrieve these groups for analysis. You can use dimensions on entries in journals, documents, and budgets.

Each dimension describes the focus of analysis. So, a two-dimensional analysis, for example, would be sales per area. By using more than two dimensions when you create an entry, you can carry out a more complex analysis. An example of a complex analysis is exploring sales per sales campaign per customer group per area. That gives you greater insight into your business, such as how well your business is operating, where it is or isn't thriving, and where you should allocate more resources. That insight helps you make more informed business decisions. Learn more at [Work with Dimensions](finance-dimensions.md).

## Set up financial reports with overviews

You can use a financial report to create a statement that compares general ledger figures with budget figures.

1. Choose the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, then choose the related link.
1. On the **Financial Reports** page, select a financial report.  
1. Choose the **Edit Row Definition** action  
1. On the **Row Definition** page, in the **Name** field, select the default financial report name.
1. Choose the **Insert G/L Accounts** action.  
1. Select the accounts you want to include in your statement, then choose **OK**.

    The accounts are inserted in your financial report. If you want, you can also change the column definition.  
1. Choose the **Edit Financial Report** action.  
1. On the **Financial Report** page, on the **Dimensions** FastTab, set the budget filter to the filter name you want to use.  
1. Choose **OK**.  

Now you can copy and paste your budget statement into a spreadsheet.  

## Comparing accounting periods using period formulas

Your financial report can compare the results of different accounting periods, such as the past month versus the same month last year. To do that, open the **Column Definition** page, and personalize it by adding the **Comparison Period Formula** field as a column. Learn more at [Personalize Your Workspace](ui-personalization-user.md). You can then set that field to a period formula.  

An accounting period doesn't need to match the calendar. However, each fiscal year must have the same number of accounting periods, even though each period can be different in length.  

[!INCLUDE[prod_short](includes/prod_short.md)] uses the period formula to calculate the duration of the comparison period in relation to the period represented by the date filter on the report. The comparison period is based on the period of the start date of the date filter. The abbreviations for period specifications are:

| Abbreviation | Description                                                                           |
| ------------ | ------------------------------------------------------------------------------------- |
| P            | Period.                                                                                |
| LP           | Last period of a fiscal year, half-year, or quarter.                                   |
| CP           | Current period of a fiscal year, half-year, or quarter. Use CP in formulas to set the period that starts or ends the formula. For example, FY\[1..CP\] denotes the time from the beginning of the current fiscal year to the current period.|
| FY           | Fiscal year. For example, FY\[1..3\] denotes the first quarter of the current fiscal year. |

Examples of formulas:

| Formula         | Description                                                                                     |
| --------------- | ----------------------------------------------------------------------------------------------- |
| \<Blank\>       | Current period.                                                                                  |
| \-1P            | Previous period.                                                                                 |
| \-1FY\[1..LP\]  | Entire previous fiscal year.                                                                     |
| \-1FY           | Current period in previous fiscal year.                                                          |
| \-1FY\[1..3\]   | First quarter of previous fiscal year.                                                           |
| \-1FY\[1..CP\]  | From the beginning of the previous fiscal year to the current period in the previous fiscal year, including both periods. |
| \-1FY\[CP..LP\] | From the current period in previous fiscal year to the last period of the previous fiscal year, including both periods.   |

If you want to calculate by regular time periods, you must enter a formula in the **Comparison Date Formula** field instead. For instance, if the field is set to -1Y, [!INCLUDE [prod_short](includes/prod_short.md)] compares to the same period one year earlier.

> [!NOTE]
> It is not always transparent which periods you are comparing because you can set a date filter on a report that spans different dates than the accounting periods reflected in the chart of accounts. So, if you create a financial report where you want to compare this period to the same period last year, you set the **Comparison Date Formula** field to *-1FY*. Then, you run the report on February 28th and set the date filter to January and February. As a result, the financial report compares January and February this year to January last year, which is the only completed accounting period of the two for last year.  

Learn more at [Work with Calendar Dates and Times](ui-enter-date-ranges.md).

## Print and save financial reports

You can print financial reports using your device's printing services. [!INCLUDE[prod_short](includes/prod_short.md)] also offers the option to save reports as Excel workbooks, Word documents, PDF, and XML files.

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, then choose the related link.
1. On the **Financial Reports** page, select the report to print, then choose the **Print** action.
1. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
1. In the **Printer** field, select the device to which the report will be sent.
    1. The **(Handled by the browser)** option indicates there's no designated printer for the report. In this case, the browser will handle the printout and display the standard printing steps, where you can choose a local printer connected to your device. **(Handled by the browser)** isn't available in the [!INCLUDE[prod_short](includes/prod_short.md)] mobile app or app for Teams.
1. Choose the **Print** action.

### Schedule a financial report or save as a PDF, Word, or Excel document

A financial report can be saved as a file in different formats, such as PDF, XML, Word, or Excel. Alternatively, [!INCLUDE[prod_short](includes/prod_short.md)] can generate recurring financial reports:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, then choose the related link.
1. On the **Financial Reports** page, choose the **Print** action.
1. Set the report accordingly, then choose the **Send to** action.
1. Select the file format or the **Schedule** action, and choose **OK**.
1. To generate a scheduled or recurring financial report, fill in the fields. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].<br><br>For recurring financial reports, set the **Earliest Start Date/Time** and **Expiration Date/Time** fields with the first and last date, respectively, to generate the financial report. Also, select on which days the report is generated by setting the **Next Run Date Formula** field following the format explained in the [Use Date Formulas](ui-enter-date-ranges.md#use-date-formulas) section.

## Importing or exporting financial report definitions

You can import and export financial report/row definitions as RapidStart configuration packages, which are useful for sharing the information with other companies, for example. The package is created in a .rapidstart file, which compresses the contents.

> [!NOTE]
> When you import financial report/row definitions, existing records with the same names as those you are importing will be replaced with the new definitions. Note that the configuration package for a report definition will not overwrite any existing row or column definitions that are used in the report definition.

To import or export financial report definitions, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, then choose the related link.
1. Choose the financial report, then choose the **Import Financial Report** or **Export Financial Report** action, depending on what you want to do.

To import or export financial report row definitions, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Row Definitions**, then choose the related link.
1. Choose the row definition, then choose the **Import Row Definition** or **Export Row Definition** action, depending on what you want to do.

## See also

[Run and Print Reports](ui-work-report.md)  
[Financial Business Intelligence](bi.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
