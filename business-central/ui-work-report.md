---
title: Scheduling a Report to Run at a Specific Date and Time | Microsoft Docs
description: Learn about entering a report into a job queue and scheduling it to be processed at a specific date and time.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: task, process, report
ms.date: 04/01/2020
ms.author: sgroespe

---
# Working with Reports, Batch Jobs, and XMLports
A report gathers information based on a specified set of criteria, and organizes and presents the information in an easy-to-read format that you can print or save as a file. There are many reports that you can access throughout the application. The reports typically provide information relative to the context of the page you are on. For example, the **Customer** page includes reports for the top 10 customers, sales statistics, and more.

Batch jobs and XMLports do more or less the same as reports, but for the purpose of performing a process or exporting data. For example, the **Create Reminders** batch job creates reminder documents for customers with overdue payments.  

> [!NOTE]
> This topic refers mainly to "report", but similar information applies to batch jobs and XMLports.

You can find reports in the **Reports** tab on selected pages, or you can use search ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") to find reports by name.

## Specifying the Data to Include in Reports
When you open a report, batch job, or XMLport, you are typically presented with a request page where you set various options and filters that determine what to include in the report.

You set filters in a report in more or less the same way as you set filters on lists. For more information, see [Filtering](ui-enter-criteria-filters.md#filtering).

> [!Caution]
> The **Filter list by** section on a request page provides a generic filtering capability for reports. These filters are optional.<br /><br /> Some reports will ignore any such filters, meaning that no matter what filter is set in the **Filter list by** section, the output of the report is the same. It is not possible to provide a list of which fields are ignored in which reports, so you will have to experiment with the filters when using them.<br /><br />
**Example**: When you use the **Create Reminders** batch job, a filter for the **Customer Ledger Entries** field of **Last Issued Reminder Level** will be ignored because filters are fixed for that batch job.

## <a name="SavedSettings"></a>Using Saved Settings
The request page can include the **Saved Settings** section that contains one or more entries in the **Use default value from** box. A saved setting is basically a predefined group of options and filters that you can apply to the report before previewing or sending the report to a file. The saved settings entry called **Last used options and filters** is always available. This entry sets the report to use options and filters that were used the last time you used the report.

Using saved settings is a fast and reliable way to consistently generate reports that contain the correct data. After you set the **Use default value from** box to a saved settings entry, you can change any of the options and filters before previewing or saving the report. The changes that you make will not be saved to the saved settings entry you selected, but they will be saved to the **Last used options and filters** entry.

>[!NOTE]
>If you are an administrator, you can create and manage the saved settings for reports for all users. For more information, see [Manage Saved Settings for Reports and Batch Jobs](reports-saving-reusing-settings.md).

## Previewing a Report
Choose the **Preview** button to view the report in the. Use the menu bar on the report preview to:

-   Move through pages
-   Zoom in and out
-   Resize to fit the page
-   Select text

    You can copy text from a report, and then paste it somewhere else, like a page in [!INCLUDE[d365fin](includes/d365fin_md.md)] or Microsoft Word.  Using a mouse, for example, you press and hold where you want to start, and then move the mouse to select one or more words, sentences, or paragraphs. You can then press the right mouse button and select **Copy**. You can then paste the selected text where ever you want it.
-   Pan the document

    You can move the visible area of the report in any direction so you can view other areas or the report. This is helpful when you have zoomed in to see details.  Using your mouse, for example, press and hold the mouse button anywhere in the report preview, and then move your mouse.

-   Download to a PDF file on your computer or network.
-   Print

## Saving a Report
You can save a report to a PDF document, Microsoft Word document, or Microsoft Excel document by choosing the **Send to** button, and then making your selection.

## <a name="ScheduleReport"></a> Scheduling a Report to Run
You can schedule or batch job a report to run at a specific date and time. Scheduled reports and batch jobs are entered in the job queue and processed at the scheduled time, similar to other jobs. You choose the **Schedule** option after you choose the **Send to** button, and then you enter information such as printer, and time and date. The report is then added to the job queue and will be run at the specified time. When the report is processed, the item will be removed from the job queue. For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).

You can choose to save the processed report to a file, such as an Excel, Word, or PDF, print it to a selected printer, or process the report only. If you choose to save the report to a file, then the processed report is sent to the **Report Inbox** area on your Role Center, where you can view it.

## <a name="PrintReport"></a>Printing a Report
You can print a report by choosing the **Print** button on the report request page or on the menu bar on the **Preview** page.

Because [!INCLUDE[prodshort](includes/prodshort.md)] is a cloud service, it cannot reach local printers connected to users' machines. However, it can connect to cloud-enabled printers. In the generic version of [!INCLUDE[prodshort](includes/prodshort.md)], a cloud printer named **Email Printer** is installed as an extension and is ready to use after initial setup.

If a cloud printer is not installed and set up, or if an installed printer fails, then printing will default to the printing options for the browser. This is indicated by this value in the **Printer** field on the report request page: *(none, handled by the browser)*.

On the **Printer Management** page, you can see the printers that are set up. For more information, see [Set Up Printers](ui-specify-printer-selection-reports.md).

> [!NOTE]
> You cannot change the **Printer** field on the report request page. To use another printer, you must select it from the **Printer Management** page.

### Printing Reports in Thai
Specifically for the Thai version of [!INCLUDE[prodshort](includes/prodshort.md)], the **Print** button cannot print reports correctly due to limitations in the service that generates the printable PDF file. Instead, you can open the report in Word and then save the report as a printable PDF.  

Alternatively, you can ask your administrator to create a Word report layout for your most used reports. For more information, see [Managing Report and Document Layouts](ui-manage-report-layouts.md).  

## Changing Report Layouts
A report layout controls what is shown on a report, how it is arranged, and how it is styled. If you want to switch to a different layout, see [Change the Current Report Layout](ui-how-change-layout-currently-used-report.md). Or, if you want to customize your own report layout, see [Create and Modify a Custom Report Layout](ui-how-create-custom-report-layout.md).

## See Also
[Set Up Printers](ui-specify-printer-selection-reports.md)  
[Working with Calendar Dates and Times](ui-enter-date-ranges.md)  
[Managing Report and Document Layouts](ui-manage-report-layouts.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
