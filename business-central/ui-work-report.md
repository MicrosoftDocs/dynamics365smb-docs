---
title: Run and print reports in Business Central
description: Learn to enter a report into a job queue and schedule it to be processed on a specific date and time.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: conceptual
ms.search.keywords: task, process, report, print, schedule, save, Excel, PDF, Word, dataset
ms.search.form:
ms.date: 03/21/2025
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Run and print reports in Business Central

Reports help you collect and display data based on specific criteria. It organizes and presents the information in an easy-to-read format you can print or save as a file. There are many reports you can access throughout the application. The reports typically provide information related to the context of the page you're on. For example, the **Customer** page includes reports for the top 10 customers, sales statistics, and more.

> [!NOTE]
> Batch jobs and XMLports do more or less the same as reports, but are used more to process or export data. For example, the **Create Reminders** batch job creates reminder documents to send to customers with overdue payments. This article refers mainly to "reports", but similar information applies to batch jobs and XMLports.

## Get started

You can find reports in the **Reports** menu on selected pages, lists, and cards. You can also use the search ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") to find reports by name. For an overview of built-in reports, you can use in [!INCLUDE[prod_short](includes/prod_short.md)], sorted by categories, see [Available Reports in [!INCLUDE[prod_short](includes/prod_short.md)]](reports-available-reports.md).

When you choose a report, you see a request page titled after the report's name where you set various options and filters that determine what data is included. The following sections explain how to use the request page to build, preview, and print a report.

## <a name="SavedSettings"></a>Use default values&mdash;predefined settings

Most report request pages include the **Use default values from** field. With this field, you can select predefined settings for the report, which automatically set options and filters. Select an entry from the dropdown list to see the options and filters on the report request page change accordingly.

The entry called **Last used options and filters** is always available. This entry sets the report to use the options and filters you used the last time you ran the report.

The **Use default values from** field provides a fast and reliable way to consistently generate reports that contain the correct data. After you select an entry, you can change any of the options and filters before you preview or print the report. The changes you make won't be saved to the predefined settings entry you selected, but they'll be saved to the **Last used options and filters** entry.

> [!NOTE]
> The predefined settings are typically set up and managed by an administrator. Learn more in [Manage Saved Settings for Reports and Batch Jobs](reports-saving-reusing-settings.md).

## Specify the data to include in a report

Use the fields under **Options** and **Filters** to change or limit the information you want in the report. You can set filters in a report in more or less the same way as you set filters on lists. Learn more in the [Filtering](ui-enter-criteria-filters.md#filtering) section.

> [!CAUTION]
> The **Filter** FastTab on a report request page provides a generic filtering capability for reports. These filters are optional.
>
> Some reports ignore any such filters, which means no matter what filter is set in the **Filter** FastTab, the output of the report is the same. It's not possible to provide a list of which fields are ignored in which reports, so you'll have to experiment with the filters when using them.
>
> **Example**: When you use the **Create Reminders** batch job, a filter for the **Customer Ledger Entries** field of **Last Issued Reminder Level** is ignored because filters are fixed for that batch job.

## Preview a report

By previewing a report, you can see what the report looks like before you print it. The preview isn't based on the printer selected in the **Printer** field on the request page. It's controlled by the browser. After previewing, you can then go back to the request page and make changes to options and filters as you need.

The preview choices on the **Report Request** page depend on the report. So, for some reports, you can select **Preview**, while for others, the choice is **Preview & Close**. Both choices open a preview of the report. The difference is that **Preview** keeps the request page open, so you can go back to it, make changes, preview again, or print. In contrast, with **Preview & Close** the request page closes, and you have to open the report again to make changes or print.

> [!NOTE]
> If you're using Business Central 2020 release wave 1 or earlier, the only choice is **Preview**, which closes the request page on preview, as described for **Preview & Close**.

### Work with the preview

In the preview, use the menu bar on the report preview to:

- Move through pages
- Zoom in and out
- Resize to fit the page
- Select text
  
  You can copy text from a report, then paste it somewhere else, such as a page in [!INCLUDE[prod_short](includes/prod_short.md)] or Microsoft Word. Using a mouse, for example, select the left mouse button and hold where you want to start. Slide the mouse to select one or more words, sentences, or paragraphs. Then select the right mouse button and select **Copy**. You can now paste the selected text where you want it.

- Pan the document
  
  You can move the visible area of the report in any direction to view other areas of the report. Panning is helpful when you zoom in to see details. Using your mouse, for example, select and hold the left mouse button anywhere in the report preview, and then move your mouse to select a section of the report.

- Download to a PDF file on your computer or network.
- Print

## Save a report to a file

You can save a report to a PDF document, Microsoft Word document, Microsoft Excel workbook, or XML document by choosing **Send to**, then making your selection. A file is downloaded to your computer.

If your organization configured OneDrive for system features, instead of being downloaded, Excel workbooks and Word documents are opened in your browser using either Excel or Word for the web.

> [!TIP]
> The **Microsoft Excel Document (data only)** and **XML Document** options are mostly for advanced purposes. You'd typically use these options to do detailed data analysis. Learn more at [Analyzing Report Data with Excel and XML](report-analyze-excel.md).
>
> You can also use **Microsoft Excel Document (data only)** to create new Excel layouts for a given report. Learn more at [Work with Excel Layouts](ui-excel-report-layouts.md).  

## <a name="ScheduleReport"></a> Schedule a report to run later or periodically

You can schedule a single or recurring report to run at a specific date and time. Scheduled reports are entered in the job queue and processed at the scheduled time, similar to other jobs. Select the **Schedule** option after selecting **Send to**, then enter information, such as the printer, and time and date. The report is added to the job queue and runs at the specified time. When the report is processed, the item is removed from the job queue. Learn more at [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).  

When you schedule a report to run, you can specify, for example, that it must run every Thursday by setting the **Next Run Date Formula** field to *D4*. Learn more in the [Use Date Formulas](ui-enter-date-ranges.md#use-date-formulas) section.  

You can save the report to a file (such as Excel, Word, or PDF), print it, or only generate the report. If you save the report to a file, then the processed report is sent to the **Report Inbox** page on your Role Center for you to view it. Learn more at [Share and Export Reports with the Report Inbox](ui-work-report-inbox.md)

### Manage scheduled recurring reports

Batch jobs generate scheduled reports managed on the **Job Queue Entries** page. You can see each report's status and other information on the page, pause/resume the report batch job, and generate the report on demand.

From the **Job Queue Entries** page, you can also change some report parameters, such as the output file type, recurrence, run date, and starting and ending times. Before you edit an existing scheduled report, however, it's necessary to put the report job queue on hold:

1. Select the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Queue Entries**, then select the related link.  
2. On the **Job Queue Entries** page, select the desired report.
3. Select the **Set On Hold** action.
4. Open and edit the scheduled report by selecting its status (*On Hold*).

After you edit the report options, repeat the first two steps and then select the **Set Status to Ready** action to resume generating the report.

Learn more about job queue management at [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).  

## <a name="PrintReport"></a>Print a report

To print a report, select **Print** on the report request page or on the menu bar of the **Preview** page.

When a report uses an Excel layout, you don't have the **Printer** field or **Print** or **Preview** buttons. Instead, there's a **Download** option. To print, select **Download**, then open the downloaded file in Excel and print from there.

### <a name="Printer"></a>Printer

The **Printer** field on the request page shows the name of printer the report is sent to. To change a printer, just select the printer from the list.

> [!NOTE]
> The **(Handled by the browser)** option indicates there's no designated printer for the report. In this case, the browser handles the printout and displays the standard printing steps, where you can choose a local printer connected to your computer. The **(Handled by the browser)** option isn't available in the [!INCLUDE[prod_short](includes/prod_short.md)] mobile app or app for Microsoft Teams.

> [!TIP]
> The printer selected for you by default is set up on the **Printer Selections** page. Learn more about how you can change the default printer in the [Set up default printers](ui-specify-printer-selection-reports.md#default) section.

### Print reports in Thai

Specifically for the Thai version of [!INCLUDE[prod_short](includes/prod_short.md)], the **Print** button can't print reports correctly because of limitations in the service that generates the printable PDF file. Instead, you can open the report in Word and then save the report as a printable PDF.  

Or, you can ask your administrator to create a Word report layout for your most used reports. Learn more at [Managing Report and Document Layouts](ui-manage-report-layouts.md).  

## Switch the report layout

A report layout controls what is shown on a report, how it's arranged, and how it's styled. There are a few ways to change the layout:

- When you're setting up to run a report, you'll see the current layout in the **Report Layout** field on the request page. To temporarily switch to a different layout, select the **Report Layout** field, then select from a list of available layouts for the report.
- To change the default layout used by a report, go to either the **Report Layouts** or **Report Layout Selection** pages.

Learn more at [Set the Layout Used by a Report](ui-set-report-layout.md). Or, if you want to customize your own report layout, see [Get Started Creating Layouts](ui-get-started-layouts.md).

## Change language and format of numbers, dates, and times

By default, the language of text and format of numbers, dates, and times in a report are based on your working language and region settings, which are defined on the **My Settings** page. You can, however, change the language and format region on a case-by-case basis when you preview, print, or send a report. On the request page, set the **Language** and **Format Region** options to your preference. You can also specify the language and region format to use by default for customers and vendors on their card pages.

Depending on where you've specified the language and format settings, [!INCLUDE [prod_short](includes/prod_short.md)] determines the settings to use in the following order:

1. The settings you specify when you generate a report.
2. The settings specified on the document, which come from the customer or vendor's settings.
3. The settings specified on the Report AL object.
4. The settings defined in My Settings.

For more information about the **My Settings** page, see [Change basic settings](ui-change-basic-settings.md#region).

## Advanced options

The fields under the **Advanced** FastTab set limitations on the generated report to control printer resources. You typically won't have to change these settings, unless you have a large report. If a report exceeds these limitations when you try to preview or print, a message indicates which limitation you've exceeded. You can then change the settings to suit your report. Each field, however, has a maximum value you should be aware of:

|Field|Maximum value|
|-----|-------------|
|Maximum rendering time|12:00:00|
|Maximum rows|1000000|
|Maximum documents|500|

> [!NOTE]
> The maximum values might be different for [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, and an administrator can change them. Learn more in the [Configuring Business Central Server - Reports](/dynamics365/business-central/dev-itpro/administration/configure-server-instance#Reports) section. For an overview of report limitations in [!INCLUDE[prod_short](includes/prod_short.md)] online, see [Operational Limits](/dynamics365/business-central/dev-itpro/administration/operational-limits-online).

## Get help for a report

You can get help using a report in two ways: teaching tips and help pane.

### Teaching tip for a report

Many reports in [!INCLUDE[prod_short](includes/prod_short.md)] have a teaching tip to increase your chance of success with the report. The title and description of these teaching tips try to answer the following hypothetical questions:

- What is this report about?
- What can I do with this report?

With teaching tips, the report creator helps you understand the logic relevant to the report, allowing you to start your reporting task immediately without being blocked. After you dismiss a teaching tip, you can select or hover over the report title on the request page to reopen the teaching tip.

Learn more in [In-product tips](product-help-and-support.md#in-product-tips)

### Help pane for a report

When the report request page is open, select the **Help** question mark in the top-right corner of the role center to open the help pane. Here, you find the teaching tip text (if defined on the report). You also find relevant links to documentation articles that explain related topics in more depth.

Learn more in [Help pane](product-help-and-support.md#help-pane)

## See also

- [Available Reports in [!INCLUDE[prod_short](includes/prod_short.md)]](reports-available-reports.md)  
- [Use Reports in Daily Work](reports-use-reports.md)  
- [Business Intelligence and Reporting Overview](reports-bi-reporting.md)  
- [Set Up Printers](ui-specify-printer-selection-reports.md)  
- [Run Batch Jobs and XMLports](ui-how-run-batch-jobs.md)  
- [Work with Calendar Dates and Times](ui-enter-date-ranges.md)  
- [Managing Report and Document Layouts](ui-manage-report-layouts.md)  
- [Financial Business Intelligence](bi.md)  
- [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
