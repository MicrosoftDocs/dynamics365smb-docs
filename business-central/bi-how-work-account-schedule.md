---
title: Build Financial Reports Using Financial Data and Account Categories
description: Describes how to use financial reports to create various views and reports for analyzing financial performance data.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 03/27/2024
ms.custom: bap-template
ms.search.keywords: bi, power BI, analysis, KPI, account schedule, financial report
ms.search.form: Report_25, 103, 104, 108, 195, 196, 197, 198, 488, 489, 490, 764, 765, 766
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

G/L account categories simplify your financial report definitions and make them more resilient to changes in the chart of accounts structure. Learn more at [Use G/L account categories to change the layout of your financial statements](bi-row-definitions.md#use-gl-account-categories-to-change-the-layout-of-your-financial-statements).

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

- Name (code)
- Description
- Row definition
- Column definition

:::image type="content" source="media/financial-reports.png" alt-text="Shows how all financial reports are constructed from a row definition and a column definition." lightbox="media/financial-reports.png":::

> [!NOTE]
> The sample finance reports in [!INCLUDE[prod_short](includes/prod_short.md)] aren't ready to use out of the box. Depending of the way you set up your G/L accounts, dimensions, G/L account categories, and budgets, you need to adjust the sample row and column definitions and the finance reports they're used in to match your setup.

You can also use formulas to compare two or more financial reports and column definitions. Comparisons let can do the following things:

- Create customized financial reports.
- Create as many financial reports as you need, each with a unique name.
- Set up various report layouts and print the reports with the current figures.

## Learning path: Create financial reports in Microsoft Dynamics 365 Business Central

Want to learn how to create budgets, and then use financial reports, dimensions, and row and column definitions to generate the financial reports that businesses typically need?

Start on the following learning path [Create financial reports in Microsoft Dynamics 365 Business Central](/training/paths/create-financial-reports-dynamics-365-business-central).

## Create a new financial report

You use financial reports to analyze general ledger accounts or to compare general ledger entries with budget entries. For example, you can view the general ledger entries as percentages of the budget entries.

The financial reports in the standard version of [!INCLUDE[prod_short](includes/prod_short.md)] might not suit your business needs. To quickly create your own financial reports, start by copying an existing one, as described in step 3 below.

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, then choose the related link.  
1. On the **Financial Reports** page, choose the **New** action to create a new financial report name. Alternatively, to reuse settings from an existing financial report, choose the **Copy Financial Report** action.
1. Fill in the report short name (you can't change the name later) and description.
1. Choose a row definition and a column definition.
1. Optionally, choose analysis views for the row and column definitions.
1. Choose the **Edit Financial Report** action to access more properties on the financial report.
1. On the **Options** FastTab, you can edit the report description, change the row and column definitions, and define how to show dates. Dates can be a Day/Week/Month/Quarter/Year hierarchy, or use accounting periods. To learn more, go to [Comparing accounting periods using period formulas](bi-column-definitions.md#comparing-accounting-periods-using-period-formulas).
1. On the **Dimensions** FastTab, you can define dimension filters for the report.
1. You can preview the report in the area below the **Dimensions** FastTab.

> [!TIP]
> After you create a financial report, you can use the **Financial Report** page to preview and validate it. To open the page, choose the **View Financial Report** action.  

> [!NOTE]
> When you open a financial report in View or Edit mode, the Filter pane is available. Don't use the Filter pane to set filters for the data in your report. Such filters can cause errors or might not actually filter the data. Instead, use the fields on the **Options** and **Dimensions** FastTabs to set up filters for the report.

### Create or edit a row definition

Row definitions in financial reports provide a place for calculations that can't be made directly in the chart of accounts. For example, you can create subtotals for groups of accounts and then include that total in other totals. You can also calculate intermediate steps that aren't shown in the final report.

To learn more, go to [Row definitions in financial reporting](bi-row-definitions.md).

### Create or edit a column definition

Use column definitions to specify the columns to include in the report. For example, you can design a report layout to compare net change and balance for the same period this year and last year. You can have up to 15 columns in a column definition. For example, multiple columns are useful for displaying budgets for 12 months with a column that shows the total.

To learn more, go to [Column definitions in financial reporting](bi-column-definitions.md).

## Using dimensions in financial reports

In financial analysis, a dimension is data you add to an entry as a kind of marker. This data is used to group entries with similar characteristics, such as customers, regions, products, and salesperson, and easily retrieve these groups for analysis. You can use dimensions on entries in journals, documents, and budgets.

Each dimension describes the focus of analysis. So, a two-dimensional analysis, for example, would be sales per area. By using more than two dimensions when you create an entry, you can carry out a more complex analysis. An example of a complex analysis is exploring sales per sales campaign per customer group per area. That gives you greater insight into your business, such as how well your business is operating, where it is or isn't thriving, and where you should allocate more resources. That insight helps you make more informed business decisions. To learn more, go to [Work with Dimensions](finance-dimensions.md).

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

## Integrate financial reports with Excel

You can integrate a financial report with an Excel workbook template, adjust the layout to suit your needs, and then update the Excel template with data from [!INCLUDE[prod_short](includes/prod_short.md)]. For example, this integration makes it easier to generate your monthly and yearly financial statements in a format that works for you.

### Set up Excel integration for a financial report (create an Excel template)

To set up Excel integration for a financial report, follow these steps to create an Excel template for a report.

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, and then choose the related link.
1. On the **Financial Reports** page, select the financial report to enable with Excel, and then choose the **Export to Excel** action.
1. Choose the **Create New Document** action. This action downloads a template Excel workbook with a single worksheet named after the report name.
1. Copy the worksheet, and rename it to **Data**.
1. Rename the report worksheet to your liking.
1. In the report worksheet, mark all cells that show data from the financial report (including column and row headers). On the **Home** ribbon, find the **Number** menu and choose **General** as the format.
1. Choose the left most cell of the area with data from the financial report, and set a reference to the equivalent cell in the Data worksheet. Drag the formula to the right to extend it to all cells in the first row, and then drag the row down to cover all rows in the financial report.
1. Hide the **Data** worksheet.
1. Format the report worksheet to suit your needs.
1. Save the workbook in OneDrive, or a similar place where the file is backed up and versioned.
1. Close the workbook.

### Run a financial report with an Excel template

To run a financial report with an Excel template, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, and then choose the related link.
1. On the **Financial Reports** page, select the financial report to enable with Excel, and then choose the **Export to Excel** action.
1. Choose the **Update Copy of Existing Document** action.
1. Upload your Excel template (close the Excel workbook before uploading it).
1. On the **Name/Value Lookup** page, choose the Data worksheet.
1. [!INCLUDE[prod_short](includes/prod_short.md)] runs the financial report and merges the resulting data with your Excel template.

## Print and save financial reports

You can print financial reports using your device's printing services. [!INCLUDE[prod_short](includes/prod_short.md)] also offers options to save reports as Excel workbooks, Word documents, PDF, and XML files.

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, then choose the related link.
1. On the **Financial Reports** page, select the report to print, then choose the **Print** action.
1. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
1. In the **Printer** field, select the device to which the report is sent.
    1. The **(Handled by the browser)** option indicates there's no designated printer for the report. In this case, the browser handles the printout and display the standard printing steps, where you can choose a local printer connected to your device. **(Handled by the browser)** isn't available in the [!INCLUDE[prod_short](includes/prod_short.md)] mobile app or app for Teams.
1. Choose the **Print** action.

### Schedule a financial report or save as a PDF, Word, or Excel document

You can save a financial report in file formats such as PDF, XML, Word, or Excel. [!INCLUDE[prod_short](includes/prod_short.md)] can also generate recurring financial reports.

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, then choose the related link.
1. On the **Financial Reports** page, choose the **Print** action.
1. Set the report accordingly, then choose the **Send to** action.
1. Select the file format or the **Schedule** action, and choose **OK**.
1. To generate a scheduled or recurring financial report, fill in the fields. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].<br><br>For recurring financial reports, set the **Earliest Start Date/Time** and **Expiration Date/Time** fields with the first and last date, respectively, to generate the financial report. Also, select on which days the report is generated by setting the **Next Run Date Formula** field following the format explained in the [Use Date Formulas](ui-enter-date-ranges.md#use-date-formulas) section.


## Best practices for working with financial report definitions

Financial report definitions aren't versioned. When you change a report definition, the old version is replaced when your change saves to the database. The following list contains some best practices for working with financial report definitions:

- If you add report definitions, choose a good code and fill in the description field with a meaningful text while you still know what you use the report for. This information helps your coworkers (and your future self) to work with the report and perhaps changing the report definition.
- Before you change a report definition, consider taking a copy of it as a backup, just in case your change doesn't work as expected. You can either just copy the definition (give it a good name), or export it. To learn more, go to [Import or export financial report definitions](#import-or-export-financial-report-definitions).
- If you need a fresh copy of a definition that [!INCLUDE[prod_short](includes/prod_short.md)] provides, an easy way to get one is to create a new company that only contains setup data. Then, export the definition and import it in the company where the definition needs a refresh.

## Import or export financial report definitions

You can import and export financial report definitions as RapidStart configuration packages. For example, configuration packages are useful for sharing information with other companies. The package is created in a .rapidstart file, which compresses the contents.

> [!NOTE]
> When you import financial report definitions, existing records with the same names as those you are importing are replaced with the new definitions. The configuration package for a report definition won't overwrite any existing row or column definitions that are used in the report definition.

To import or export financial report definitions, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, then choose the related link.
1. Choose the financial report, then choose the **Import Financial Report** or **Export Financial Report** action, depending on what you want to do.

To learn more about how to import or export financial report row or column definitions, go to the following articles: 

- [Import or export financial reporting row definitions](bi-row-definitions.md#import-or-export-financial-reporting-row-definitions), or
- [Import or export financial reporting column definitions](bi-column-definitions.md#import-or-export-financial-report-column-definitions)

## See also

[Row definitions in financial reporting](bi-row-definitions.md)  
[Column definitions in financial reporting](bi-column-definitions.md)  
[Run and Print Reports](ui-work-report.md)  
[Financial Business Intelligence](bi.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
