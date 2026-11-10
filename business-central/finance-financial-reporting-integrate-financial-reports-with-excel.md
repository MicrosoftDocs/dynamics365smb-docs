---
title: Integrate financial reports with Excel
description: Describes how to use financial reporting together with Excel.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: how-to
ai-usage: ai-assisted
ms.date: 11/10/2026
ms.custom: bap-template
ms.search.keywords: bi, power BI, analysis, KPI, account schedule, financial report, Excel
ms.search.form: 490
ms.service: dynamics-365-business-central
---

# Integrate financial reports with Excel

The Financial Reporting feature offers multiple ways to view the reports in Excel. This integration makes it easier to generate your monthly and yearly financial statements in a format that works for you. You can:

* Download the report to Excel and use it as the starting point for a formatted template.
* Upload and store Excel templates as Excel layouts in [!INCLUDE[prod_short](includes/prod_short.md)].
* Define a default Excel layout for the report.

This article describes each approach.

## Set up Excel integration for a financial report (create an Excel template)

To set up Excel integration for a financial report, follow these steps to create an Excel template.

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, and then choose the related link.
1. On the **Financial Reports** page, select the financial report to enable with Excel, and then choose the **View Financial Report** action.
1. On the **Financial Report** page, choose the **Open in Excel (using layout)** action to download a template Excel workbook with a worksheet named after the report's row definition. [!INCLUDE [prod_short](includes/prod_short.md)] only creates a new workbook if you don't specify a default Excel layout for the report. Learn more in [Working with Microsoft Excel layouts](ui-excel-report-layouts.md).
1. Copy the worksheet for the formatted report to a new worksheet.
1. In the original report worksheet, mark all cells that show data from the financial report, including column and row headers. On the **Home** ribbon, find the **Number** menu and choose **General** as the category.
1. Choose the leftmost cell of the area with data from the financial report, and set a reference to the equivalent cell in the copied worksheet. Drag the formula to extend it to all cells in the first row, and then drag the row down to cover all rows in the financial report.
1. Hide the original worksheet.
1. Format the copied worksheet to suit your needs.
1. On the **Financial Report** page, choose the **Excel Layouts** action, choose **Import**, and then choose the workbook.
1. Close the workbook.

> [!TIP]
> The **Row No.** field shows on the data worksheet, but you might not want to include it on your worksheet.

> [!NOTE]
> If you make changes to the row or column definitions of the report you created a template for, you must update the template too. Each row and column in the Excel template must be in the same position as the generated report.

<a name="using-agentic-excel-for-formatting-your-report-worksheet"></a>

## Format your report worksheet with Copilot in Excel

When you export data from a financial report to Excel by using the **Open in Excel (using layout)** action, you can use Copilot in Excel to help prepare and format the workbook. Describe the changes you want in natural language. Copilot can edit the workbook directly in edit mode or propose a plan first in plan mode. Review and verify its changes before you use the report.

An example prompt could be (adjust to your style):

```Prompt example
I need to build a balance sheet report based on the data in the BS worksheet. 
The data was generated from the Financial Reporting feature in Business Central. 

Keep the BS worksheet as is, but hide it. 
My report should show in additional worksheets. 
It's OK to add multiple worksheets for different types of analysis.

I want the report be formatted professionally with headers in bold, and amounts formatted as currency (rounded to nearest integer). 
Totals should have a line above them.
```

Learn more in [Use Copilot in Excel to enhance data tasks](across-work-with-excel.md#use-copilot-in-excel-to-enhance-data-tasks).

## Example: Use and update an Excel template to create a monthly report

You can create an Excel template that contains the reports that you include in your reporting package. Each report in the workbook must have a data tab and a tab that has the formatted report. When you update your monthly package, use the **Update Copy of Existing Document** for each report. Be sure to save after each update.

To produce your monthly financial report, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, and then choose the related link.
1. Choose the financial report you used to create the Excel template, and then choose the **View Financial Report** action.
1. Set the date in the **Date Filter** field to the next month.
1. Choose the **Open in Excel (using layout)** action.
1. The Excel workbook is updated with data and downloaded for you. Be sure to enable editing to show the changes when you open the workbook.
1. Save the workbook with a different name than the original template.

## Save Excel templates as Excel layouts

[!INCLUDE[prod_short](includes/introduced_in_2025rw1.md)]

Instead of saving your Excel templates locally, you can import them into [!INCLUDE[prod_short](includes/prod_short.md)] with the Excel layouts for Financial Reporting feature.

### Manage Excel layouts for a financial report

Use the **Financial Report Excel Layouts** page to create, import, export, run, and delete layouts. To manage Excel layouts for a financial report, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, and then choose the related link.
1. On the **Financial Reports** page, select the financial report to enable with Excel layouts, and then choose **View Financial Report**.
1. On the **Financial Report** page, choose **Definitions**, and then **Excel Layouts**.

### Create a new Excel layout for a financial report

To create a new Excel layout for a financial report, follow these steps:

1. Open the **Financial Report Excel Layouts** page for the report.
1. To create a new layout, fill in the **Code**, **Description**, and **File name** fields. [!INCLUDE [prod_short](includes/prod_short.md)] prepares a new workbook for you in the background.
1. To download the Excel template, choose the **Export/Run** action.
1. Create your layout using the steps described in [Set up Excel integration for a financial report (create an Excel template)](#set-up-excel-integration-for-a-financial-report-create-an-excel-template).
1. When your layout is ready for testing, close the Excel workbook and choose the **Import** action. Upload your Excel workbook.

### Run a financial report with an Excel layout

To run a financial report with an Excel layout, follow these steps:

1. Open the **Financial Report Excel Layouts** page for the report.
1. Select the row with the layout, and then choose the **Export/Run** action.

### Replace an Excel layout for a financial report

To replace a financial report with a new Excel layout, follow these steps:

1. Open the **Financial Report Excel Layouts** page for the report.
1. Select the row with the layout, and then choose the **Import** action. Upload the new Excel workbook.

### Define a default Excel layout for a financial report

To define a default Excel layout for a financial report, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, and then choose the related link.
1. On the **Financial Reports** page, choose the financial report, and then choose the **View Financial Report** action.
1. On the **Options** FastTab, in the **Default Excel Layout** field, choose the default Excel layout for the report. By default, the field is hidden, so you might need to choose **Show more** on the FastTab.

### Run a financial report with a default Excel layout

To run a financial report with a default Excel layout, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, and then choose the related link.
1. On the **Financial Reports** page, open the financial report.
1. Choose the **Export to Excel/Print** action, and then choose the **Open in Excel (using layout)** action.

## Contributors

Microsoft maintains this article. The following contributors provided parts of the examples.

* [Jennifer Bonenfant](https://www.linkedin.com/in/jenniferbonenfant/) | MBA, CPA

## Related information

[Use Copilot in Excel to enhance data tasks](across-work-with-excel.md#use-copilot-in-excel-to-enhance-data-tasks)  
[View a financial report](finance-financial-reporting-view-a-report.md)  
[Prepare financial reporting](bi-how-work-account-schedule.md)  
[Financial analytics overview](bi.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
