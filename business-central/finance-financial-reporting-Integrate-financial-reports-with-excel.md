---
title: Integrate financial reports with Excel
description: Describes how to use financial reporting together with Excel.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 3/8/2026
ms.custom: bap-template
ms.search.keywords: bi, power BI, analysis, KPI, account schedule, financial report, Excel
ms.search.form: 490
ms.service: dynamics-365-business-central
---

# Integrate financial reports with Excel

[!INCLUDE[integrate_financial_reports_with_excel_intro](includes/integrate_financial_reports_with_excel_intro.md)]

## Set up Excel integration for a financial report (create an Excel template)

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

## Using agentic Excel for formatting your report worksheet

When you export data from a financial report to Excel using the **Create New Excel Template** action, you can take advantage of **Agent Mode** in Excel to streamline data preparation and formatting. **Agent Mode** allows you to describe tasks in natural language. Depending on your instructions, Excel does the cleanup, transformation, or analysis steps automatically. 

An example prompt could be (adjust to your style)

```prompt
I need to build a balance sheet report based on the data in the BS worksheet. The data was generated from the Financial Reporting feature in Business Central. 

Keep the BS worksheet as is, but hide it. My report should be shown in additional worksheets. It is OK to add multiple worksheets for different types of analysis.

I want the report be formatted professionally with headers in bold, amounts formatted as currency (rounded to nearest integer). Totals should have a line above them.
```

To learn more, go to [Use Agentic Excel to enhance data tasks](across-work-with-excel.md#use-agentic-excel-to-enhance-data-tasks).

## Run a financial report with an Excel template

To run a financial report with an Excel template, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, and then choose the related link.
1. On the **Financial Reports** page, select the financial report to enable with Excel, and then choose the **Export to Excel/PDF** menu.
1. Choose the **Update Copy of Existing Document** action.
1. Upload your Excel template (close the Excel workbook before uploading it).
1. On the **Name/Value Lookup** page, choose the Data worksheet.
1. [!INCLUDE[prod_short](includes/prod_short.md)] runs the financial report and merges the resulting data with your Excel template.

## Example: Use and update an Excel template to create a monthly report

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

## Save Excel templates as Excel layouts

[!INCLUDE[prod_short](includes/introduced_in_2025rw1.md)]

Instead of saving your Excel templates locally, you can import them into [!INCLUDE[prod_short](includes/prod_short.md)] with the Excel layouts for Financial Reporting feature.

### Manage Excel layouts for a financial report

To manage Excel layouts for a financial report, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, and then choose the related link.
1. On the **Financial Reports** page, select the financial report to enable with Excel layouts, and then choose the **Definitions** menu.
1. To open the **Financial Report Excel Layouts** page where you can create, import, export, run, and delete layouts, choose the **Excel Layouts** action.

### Create a new Excel layout for a financial report

To create a new Excel layout for a financial report, follow these steps:

1. Open the **Financial Report Excel Layouts** page for the report.
1. To create a new layout, fill in the **Code**, **Description**, and **File name** fields.
1. Choose the **Run/Export** action to download the Excel template.
1. Create your layout using the steps described in [Set up Excel integration for a financial report (create an Excel template)](#set-up-excel-integration-for-a-financial-report-create-an-excel-template).
1. When your layout is ready for testing, close the Excel workbook and choose the **Import** action. Upload your Excel workbook.

### Run a financial report with an Excel layout

To run a financial report with an Excel layout, follow these steps:

1. Open the **Financial Report Excel Layouts** page for the report.
1. Select the row with the layout, and then choose the **Run/Export** action.

### Replace an Excel layout for a financial report

To replace a financial report with a new Excel layout, follow these steps:

1. Open the **Financial Report Excel Layouts** page for the report.
1. Select the row with the layout, and then choose the **Import** action. Upload the new Excel workbook.

### Define a default Excel layout for a financial report

To define a default Excel layout for a financial report, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, and then choose the related link.
1. On the **Financial Reports** page, open the financial report
1. On the **Options** FastTab, in the **Default Excel Layout** field, choose the default Excel layout for the report.

### Run a financial report with a default Excel layout

To run a financial report with a default Excel layout, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, and then choose the related link.
1. On the **Financial Reports** page, open the financial report.
1. Choose the **Export to Excel/Print** action, and then choose the **Open in Excel (using layout)** action.

## Contributors

*This article is maintained by Microsoft. Parts of the examples were originally written by the following contributors.*

* [Jennifer Bonenfant](https://www.linkedin.com/in/jenniferbonenfant/) | , MBA, CPA

## Related information

[Use Agentic Excel to enhance data tasks](across-work-with-excel.md#use-agentic-excel-to-enhance-data-tasks)
[View a financial report](finance-financial-reporting-view-a-report.md)
[Prepare financial reporting](bi-how-work-account-schedule.md)  
[Financial analytics overview](bi.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
