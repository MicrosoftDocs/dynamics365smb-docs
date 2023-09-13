---
title: Build Financial Reports Using Financial Data and Account Categories
description: Describes how to use financial reports to create various views and reports for analyzing financial performance data.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bnielse
ms.topic: how-to
ms.date: 02/27/2023
ms.custom: bap-template
ms.search.keywords: bi, power BI, analysis, KPI, account schedule, financial report
ms.search.form: 103, 104, 108, 195, 196, 197, 198, 489, 490, 764, 765, 766
---
# Prepare Financial Reporting with Financial Data and Account Categories

Financial reports give you insight into the financial data stored in your chart of accounts (COA). Financial reports analyze figures in general ledger (G/L) accounts, and compare general ledger entries with budget entries. The results display in charts and reports in your Role Center, such as the cash flow chart and income statement and balance sheet reports.

You access these two reports, for example, with the **Financial Statements** action in the business manager and accountant role centers.  

[!INCLUDE[prod_short](includes/prod_short.md)] provides sample financial reports you can use right away. You can also set up your own rows and columns to specify the figures to compare. For example, you can create financial reports to calculate profit margins using dimensions such as departments or customer groups. The number of customized financial statements you can create is unlimited.  

Setting up financial reports requires an understanding of the financial data in the chart of accounts. For example, you can view general ledger entries as percentages of budget entries, but that requires you to have created budgets. Learn more at [Create G/L Budgets](finance-how-create-budgets.md).

## Financial reports

Financial reports arrange accounts from your chart of accounts in ways that make data easier to present. You can set up various layouts to define the information you want to extract from the chart of accounts. Financial reports provide a place for calculations that can't be made directly in the chart of accounts. For example, you can create subtotals for groups of accounts and then include that total in other totals. Another example is to calculate profit margins on dimensions such as departments or customer groups. Additionally, you can filter general ledger entries and budget entries, for example, by net change or debit amount.

You can also compare two or more financial reports and column definitions by using formulas, so you can do the following things:

* Create customized financial reports.
* Create as many financial reports as you need, each with a unique name.
* Set up various report layouts and print the reports with the current figures.

## G/L account categories

You can use G/L account categories to change the layout of your financial statements. For example, once you've set up your account categories on the **G/L Account Categories** page, you can choose the **Generate Financial Reports** action and update the underlying financial reports for the core financial reports. Then the next time you run one of these reports, such as the **Balance Statement** report, new totals and subentries are added.

> [!NOTE]
> The top-level account categories, such as the **Liabilities** node, are fixed and you cannot add your own. However, you can delete and add account categories at lower levels and define how the related financial report appears in reports.
>
> You should create and structure your own lower-level G/L account categories from scratch, in a hierarchy if needed, rather than try to rearrange the existing ones. For example, you can restructure the **Liabilities** node to contain a new **Equity** node followed by the **Current Liabilities** and **Long Term Liabilities** nodes.

## Create a new financial report

You use financial reports to analyze general ledger accounts or to compare general ledger entries with budget entries. For example, you can view the general ledger entries as percentages of the budget entries.

The financial reports in the standard version of [!INCLUDE[prod_short](includes/prod_short.md)] might not suit your business needs. To quickly create your own financial reports, start by copying an existing one, as described in step three below.

> [!TIP]
> After you create a financial report, you can use the **Financial Report** page to preview and validate your newly defined financial report. To open the page, choose the **Edit Financial Report** action.  

> [!NOTE]
> When you open a financial report in View or Edit mode, the Filter pane is available. However, don't use the pane to set filters for the data in your report. The filters can cause errors or might not actually filter the data. Instead, use the filter fields on the **Options** and **Dimensions** FastTabs.

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, then choose the related link.  
2. On the **Financial Reports** page, choose the **New** action to create a new financial report name.
3. Alternatively, if you want to reuse settings from an existing financial report, choose the **Copy Financial Report** action.
4. Fill the fields in as necessary. In the **Column Definition** field, select an existing definition, which you can later edit if you want.

    Column definitions specify the parameters by which the financial data on the rows is shown. For example, a column definition might contain four columns you can use to compare net change and balance for the same period this year and last year. Learn more in the [Edit a column definition](bi-how-work-account-schedule.md#edit-a-column-definition) section.

5. Choose the **Edit Row Definition** action.
6. Choose the **Insert G/L Accounts**, **Insert CF Accounts**, and **Insert Cost Types** actions to create a row for each financial element you want to analyze. For example, you might have one row for current assets and another row for fixed assets. For inspiration, see the financial reports in the CRONUS demonstration company.

    > [!NOTE]
    > The **Row No.** field shows the first 10 characters of an identifier, such as an account number. If you add elements with identifiers that start with the same 10 characters you'll have duplicates in the **Row No.** field. If needed, you can manually edit the identifiers after you insert the elements. The full identifiers are displayed in the **Totaling** field.

7. On the **Financial Reports** page, choose the **Edit Financial Report** action to access the resulting financial report.
8. On the **Financial Report** page, in the **Column Definition** field, select another column definition to explore the financial data by other parameters.
9. Choose **OK**.

You've now defined the following the basis of the financial report, the rows of financial data to display, and an existing layout of columns to show the data on the rows using custom parameters. If the default column definition you selected in step 4 doesn't suit your purpose, follow the steps in [Edit a column definition](#edit-a-column-definition).

### Edit a column definition

Use column definitions to specify the columns to include in the report. For example, you can design a layout to compare net change and balance for the same period this year and last year. You can have up to 15 columns, which is useful for, say, displaying budgets for 12 months with a column that shows the total.

> [!NOTE]
> A printed/previewed/saved version of a financial report displays a maximum of five columns. In contrast, if a financial report is only meant for analysis on the **Financial Report** page, you can create as many columns as you want.

1. On the **Financial Reports** page, select the relevant financial report, then choose the **Edit Column Definition** action.
2. On the **Column Definition** page, create a row for each column of financial data shown in the financial report. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Choose **OK**.
4. Open the **Financial Report** page from time to time to verify the new column definition works as intended.

> [!NOTE]
> The columns you define on each row represent columns three and up on the **Financial Report** page. The first two columns, **Row No.** and **Description**, are fixed.  

### Create a column that calculates percentages

Sometimes you may want to include a column in a financial report to calculate percentages of a total. For example, if you have rows that break down sales by dimension, you may want a column to indicate the percentage of total sales in each row.

1. Choose the ![Lightbulb that opens the Tell Me feature 2.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, then choose the related link.
2. On the **Financial Reports** page, select a financial report.  
3. Choose the **Edit Financial Report** action to set up a financial report row to calculate the total on which the percentages will be based.  
4. Insert a line immediately above the first row for which you want to display a percentage.  
5. Fill in the fields on the line as follows: In the **Totaling Type** field, enter **Set Base for Percent**. In the **Totaling** field, enter a formula for the total the percentage will be based on. For example, if row 11 contains the total sales, enter **11**.  
6. Choose the **Edit Column Definition** action to set up a column.  
7. Fill in the fields on the line as follows: In the **Column Type** field, select **Formula**. In the **Formula** field, enter a formula for the amount you want to calculate a percentage for, followed by the percentage sign (%). So, if column number N contains the net change, enter **N%**.  
8. Repeat steps 4 through 7 for each group of rows you want to break down by percentage.

## Set up financial reports with overviews

You can use a financial report to create a statement comparing general ledger figures and budget figures.

1. Choose the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, then choose the related link.
2. On the **Financial Reports** page, select a financial report.  
3. Choose the **Edit Row Definition** action  
4. On the **Row Definition** page, in the **Name** field, select the default financial report name.
5. Choose the **Insert G/L Accounts** action.  
6. Select the accounts you want to include in your statement, then choose **OK**.

    The accounts are now inserted into your financial report. If you want, you can also change the column definition.  
7. Choose the **Edit Financial Report** action.  
8. On the **Financial Report** page, on the **Dimensions** FastTab, set the budget filter to the filter name you want to use.  
9. Choose **OK**.  

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

You can print financial reports using your device's printing services. [!INCLUDE[prod_short](includes/prod_short.md)] also offers the option to save reports as Microsoft Excel workbooks, Microsoft Word documents, PDF, and XML files.

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, then choose the related link.
2. On the **Financial Reports** page, select the report to print, then choose the **Print** action.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. In the **Printer** field, select the device to which the report will be sent.
    1. The **(Handled by the browser)** option indicates there's no designated printer for the report. In this case, the browser will handle the printout and display the standard printing steps, where you can choose a local printer connected to your device. **(Handled by the browser)** isn't available in the [!INCLUDE[prod_short](includes/prod_short.md)] mobile app or app for Microsoft Teams.
5. Choose the **Print** action.

### Schedule a financial report or save as a PDF, Word, or Excel document

A financial report can be saved as a file in different formats, such as PDF, XML, Word, or Excel. Alternatively, [!INCLUDE[prod_short](includes/prod_short.md)] can be set to generate recurring financial reports:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, then choose the related link.
2. On the **Financial Reports** page, choose the **Print** action.
3. Set the report accordingly, then choose the **Send to** action.
4. Select the file format or the **Schedule** action, and choose **OK**.
5. To generate a scheduled or recurring financial report, fill in the fields. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].
   * For recurring financial reports, set the **Earliest Start Date/Time** and **Expiration Date/Time** fields with the first and last date, respectively, to generate the financial report. Also, select on which days the report is generated by setting the **Next Run Date Formula** field following the format explained in the [Use Date Formulas](ui-enter-date-ranges.md#use-date-formulas) section.

## Importing or exporting financial reports

You can import and export financial reports as RapidStart configuration packages, which are useful for sharing the information with other companies, for example. The package is created in a .rapidstart file, which compresses the contents.

### Import and export financial reports

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, then choose the related link.
2. Choose the financial report, then choose the **Import Financial Report** or **Export Financial Report** action, depending on what you want to do.

> [!NOTE]
> When you import financial reports, existing records with the same names as those you are importing will be deleted.

## See also

[Run and Print Reports](ui-work-report.md)  
[Financial Business Intelligence](bi.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
