---
title: View a financial report
description: Describes how to view a financial report on-screen, as a PDF, or in Excel.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 3/17/2026
ms.custom: bap-template
ms.search.keywords: bi, power BI, analysis, KPI, account schedule, financial report
ms.search.form: Report_25_Primary, 490
ms.service: dynamics-365-business-central
---

# View a financial report on-screen, as a PDF, or in Excel

After you set up definitions for your financial reports, you can start using the data to support your finance and accounting processes. The Financial Reporting feature offers multiple ways to view the reports:

- On-screen, with drill-through to the underlying numbers.
- As PDF documents designed for sharing and printing.
- As Excel files that use the template or layout of your choice.

This article describes each approach.

## View a financial report on-screen

You can view any report on-screen with drill-through to the underlying numbers.

To view a financial report, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, and then choose the related link.

   > [!TIP]
   > By default, the **Financial Reports** page displays reports in a list view. However, some people prefer a tile view. Tiles show most of the same information as the list, just in a different way. If you like tiles, it's easy to switch. In the upper right of the page, choose the **View layout options** icon :::image type="content" source="media/view-layout-options.png" alt-text="Screenshot of the View layout options icon.":::, and choose **Tiles**. 

1. On the **Financial Reports** page, select the financial report you want to view, and then choose the **View Financial Report** action.

The page has **Options** and **Dimensions** FastTabs. If the FastTabs aren't available, you might need to enable them with the **Show all options** action.

On the **Options** FastTab, specify how the report shows data. For example:

- Use the **View by** field to specify the period for which to summarize data. Specifying a period is a good way to make the data more granular.
- Use the **Date Filter** field to show amounts for a certain data or date range.
- The **Show All Lines** toggle specifies whether the page displays all lines, or excludes empty lines, as defined in the row definition.
- The **Negative Amount Format** field allows you to define how you want to format negative numbers.

On the **Dimensions** FastTab, you can choose to filter data according to global dimensions.

> [!TIP]
> If you change a setting, to refresh the data on the screen, use the **Recalculate** action.

### Show or hide the Row No. field on a report

The **Row No.** field might show when you view a report on-screen. The field doesn't show when you view the report in a PDF. To show or hide the field, personalize the page. To learn more, go to [Personalize your workspace](ui-personalization-user.md).

## Integrate financial reports with Excel

[!INCLUDE[integrate_financial_reports_with_excel_intro](includes/include-integrate-financial-reports-with-excel-intro.md)]

To learn more, go to [Integrate financial reports with Excel](finance-financial-reporting-Integrate-financial-reports-with-excel.md).


## Print and save financial reports

You can print financial reports using your device's printing services. [!INCLUDE[prod_short](includes/prod_short.md)] also offers options to save reports as PDF files.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Financial Reports**, then choose the related link.
1. On the **Financial Reports** page, select the report to print, then choose the **Print/PDF** action.
1. In the **Printer** field, select the device to which the report is sent.
    
    The **(Handled by the browser)** option indicates that a printer isn't specified for the report. In this case, the browser handles the printout and displays the standard printing steps. You can choose a local printer connected to your device. **(Handled by the browser)** isn't available in the [!INCLUDE[prod_short](includes/prod_short.md)] mobile app or the app for Teams.
1. Fill in the fields remaining fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
1. You can print the report, or send its results to a type of document, such as a PDF, XML, Word, or Excel:
   
   1. To send the report results to a type of document, choose the **Send to** action. 
   1. To print the report, choose the **Print** action.

> [!TIP]
> The name of your company always shows in the upper right of the PDF. If you specify a **Display Name** on the **Companies** list page, that name shows instead of the name in the **Name** field (which isn't easy to change).

## Schedule a financial report

You might have a report that you want to run regularly. To avoid having to run the report manually, you can run it according to a schedule. The schedule can produce the report as an Excel file that shows up in the Report Inbox on your Role Center, as a PDF, or both. If you want to share the report with colleagues, you can set up the schedule to send the report to them by email.

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, then choose the related link.
1. On the **Financial Reports** page, choose the **Definitions** action, and choose **Schedules**.
1. In the **Code** field, enter a name for the schedule. For example, if the schedule runs the report on a weekly basis, you might name it "Weekly."
1. In the **Description** field, enter text that indicates what the report shows.
1. To export the report to Excel, select the **Export to Excel** checkbox, and then choose the template to use in the **Excel Template Code** field.
1. To export the report to PDF, select the **Export to PDF** checkbox.
1. To send the report to recipients by email, select the **Send Email** checkbox. If you choose this option, choose the **Recipients** action to specify who to send the report to. 
1. To filter the values on the report to suit your needs, choose the **Custom Filters** action. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
1. To specify when to start the schedule, and how often it runs:
   1. To manually specify a start date and time, fill in the **Next Run Date/Time** field. To calculate the start date, leave this field blank and instead, enter a date formula in the **Start Date Filter Formula** field. To learn more about date formulas, go to [Use date formulas](ui-enter-date-ranges.md#use-date-formulas).
   1. To specify how often to run the report, enter a date formula in the **Recurrence Run Date Formula** field.

## Review financial report runs

[!INCLUDE [finance-review-fin-rep-runs](includes/finance-review-fin-rep-runs.md)] 

## Related information
<!-- 
2025w1: add link to administrator article for Financial Report Usage telemetry
-->
[Prepare financial reporting](bi-how-work-account-schedule.md)  
[Financial analytics overview](bi.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
