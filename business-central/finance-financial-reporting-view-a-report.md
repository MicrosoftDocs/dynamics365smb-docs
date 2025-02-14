---
title: View a financial report
description: Describes how to view a financial report on-screen, as a PDF, or in Excel.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 1/24/2025
ms.custom: bap-template
ms.search.keywords: bi, power BI, analysis, KPI, account schedule, financial report
ms.search.form: Report_25, 
ms.service: dynamics-365-business-central
---

# View a financial report on-screen, as a PDF, or in Excel

After you set up definitions for your financial reports, you can start using the data to support your finance and accounting processes. The Financial Reporting feature offers multiple ways for you to view the reports:

- On-screen, with drill-through to the underlying numbers.
- As PDF documents designed for sharing and printing.
- As Excel files that use the template or layout of your choice.

This article describes each approach.

## View a financial report on-screen

You can view any report on-screen with drill-through to the underlying numbers.

To view a financial report, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, and then choose the related link.
1. On the **Financial Reports** page, select the financial report you want to view, and then choose the **View Financial Report** action.

The page has **Options** and **Dimensions** FastTabs. If the FastTabs aren't available, you might need to enable them with the **Show all options** action.

On the **Options** FastTab, specify how the report shows data. For example:

- Use the **View by** field to specify the period for which to summarize data. Specifying a period is a good way to make the data more granular.
- Use the **Date Filter** field to show amounts for a certain data or date range.

<!-- uncomment for 2025w1
- The **Show All Lines** toggle specifies whether the page should display all lines, or exclude empty lines. This option is only available in 2025 release wave 1 and later.
- The **** field allows you to define how you want negative numbers to be formatted 
-->

On the **Dimensions** FastTab, you can choose to filter data according to global dimensions.

> [!TIP]
> If you change a setting, to refresh the data on the screen, use the **Recalculate** action.

### Show or hide the Row No. field on a report

The **Row No.** field might show when you view a report on-screen. The field doesn't show when you view the report in a PDF. To show or hide the field, personalize the page. To learn more, go to [Personalize your workspace](ui-personalization-user.md).

## Integrate financial reports with Excel

You can integrate a financial report with an Excel workbook template, adjust the layout to suit your needs, and then update the Excel template with data from [!INCLUDE[prod_short](includes/prod_short.md)]. For example, this integration makes it easier to generate your monthly and yearly financial statements in a format that works for you.

### Set up Excel integration for a financial report (create an Excel template)

To set up Excel integration for a financial report, follow these steps to create an Excel template.

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, and then choose the related link.
1. On the **Financial Reports** page, select the financial report to enable with Excel, and then choose the **View Financial Report** action.
1. On the **Financial Report** page, choose the **Create New Excel Template** action. This action downloads a template Excel workbook with a single worksheet named after the report.
1. Copy the worksheet, and rename it to **Data**.
1. Rename the report worksheet to your liking.
1. In the report worksheet, mark all cells that show data from the financial report, including column and row headers. On the **Home** ribbon, find the **Number** menu and choose **General** as the category.
1. Choose the leftmost cell of the area with data from the financial report, and set a reference to the equivalent cell in the Data worksheet. Drag the formula to extend it to all cells in the first row, and then drag the row down to cover all rows in the financial report.
1. Hide the **Data** worksheet.
1. Format the report worksheet to suit your needs.
1. Save the workbook in OneDrive, or a similar place where the file is backed up and versioned.
1. Close the workbook.

> [!TIP]
> The **Row No.** field is shown on the data worksheet, but you might not want to include it on your worksheet.

> [!NOTE]
> If you make changes to the row or column definitions of the report you created a template for, you must update the template too. Each row and column in the Excel template must be in the same position as the generated report.

### Run a financial report with an Excel template

To run a financial report with an Excel template, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, and then choose the related link.
1. On the **Financial Reports** page, select the financial report to enable with Excel, and then choose the **Export to Excel/PDF** menu.
1. Choose the **Update Copy of Existing Document** action.
1. Upload your Excel template (close the Excel workbook before uploading it).
1. On the **Name/Value Lookup** page, choose the Data worksheet.
1. [!INCLUDE[prod_short](includes/prod_short.md)] runs the financial report and merges the resulting data with your Excel template.

### Example: Use and update an Excel template to create a monthly report

You can create an Excel template that contains the reports that you include in your reporting package. Each report in the workbook must have a data tab and a tab that has the formatted report. When you update your monthly package, use the **Update Copy of Existing Document** for each report. Be sure to save after each update.

Follow these steps to produce your monthly financial report.

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, and then choose the related link.
1. Choose the financial report you used to create the Excel template, and then choose the **View Financial Report** action.
1. Change the date filter to the next month.
1. Choose the **Export to Excel/PDF** and **Update Copy of Existing Document** actions.
1. Select the template you saved in OneDrive (or a similar place.) Make sure that the Excel file is closed. Otherwise, an error message will state that the file is in use.
1. The next screen shows the worksheets/tabs that are available in the Excel workbook. Choose the **Data** tab, and then choose **OK**. If you choose the tab labeled **IS**, your formatting will be overwritten and you'll need to start over.
1. The Excel workbook is updated with data and downloaded to you. Be sure to enable editing to show your changes when opening the workbook.
1. Save the workbook with a different name than the original template.


## Print and save financial reports

You can print financial reports using your device's printing services. [!INCLUDE[prod_short](includes/prod_short.md)] also offers options to save reports as PDF files.

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, then choose the related link.
1. On the **Financial Reports** page, select the report to print, then choose the **Print** action.
1. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
1. In the **Printer** field, select the device to which the report is sent.
    1. The **(Handled by the browser)** option indicates that a printer isn't specified for the report. In this case, the browser handles the printout and displays the standard printing steps. You can choose a local printer connected to your device. **(Handled by the browser)** isn't available in the [!INCLUDE[prod_short](includes/prod_short.md)] mobile app or the app for Teams.
1. Choose the **Print** action.

> [!TIP]
> Your company name is always shown on the upper right in the PDF. If you define a *Display Name* on the **Companies** list page, then this will be shown instead of the **Name** (which is not easy to change).


### Schedule a financial report or save as a PDF document

You can save a financial report in file formats such as PDF. [!INCLUDE[prod_short](includes/prod_short.md)] can also generate recurring financial reports.

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, then choose the related link.
1. On the **Financial Reports** page, choose the **Print** action.
1. Set the report accordingly, then choose the **Send to** action.
1. Select the file format or the **Schedule** action, and choose **OK**.
1. To generate a scheduled or recurring financial report, fill in the fields. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].<br><br>For recurring financial reports, set the **Earliest Start Date/Time** and **Expiration Date/Time** fields with the first and last date, respectively, to generate the financial report. Also, select the days on which to generate the report by filling in the **Next Run Date Formula** field. To learn more about date formulas, go to [Use Date Formulas](ui-enter-date-ranges.md#use-date-formulas).

## Related information

[Prepare financial reporting](bi-how-work-account-schedule.md)  
[Financial analytics overview](bi.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
