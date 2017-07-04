---
title: Scheduling a Report to Run at a Specific Date and Time | Microsoft Docs
description: Learn about entering a report into a job queue and scheduling it to be processed at a specific date and time.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: task, process, job queue
ms.date: 03/29/2017
ms.author: solsen

---
# Working with Reports
A report gathers information based on a specified set of criteria, and organizes and presents the information in an easy-to-read, printable format. There are many reports that you can access throughout the application. The reports provide information relative to the context of the page you are on. For example, the **Customer** page includes reports for the top 10 customers and the sales statistics, and more.

You can find reports in the **Reports** tab on selected pages, or you can use search to find reports by name. When you open a report, you are presented with a page that let's you specify the information (options and filters) that you want to include in the report and how you want it arranged. For example, depending on the report, you can specify a date range, a specific record such as a customer, or sorting order.

## Preview a report
Choose **Preview** to see the report in the browser. You can scroll through the page, zoom in and out, and download the report as a PDF document.   

## Save a Report
You can save a report to a PDF document, Microsoft Word document, or Microsoft Excel document by choosing the **Send to**, and then making your selection. 

## <a name="ScheduleReport"></a> Schedule a Report to Run
You can schedule a report to run at a specific date and time. Scheduled reports are entered in the job queue and processed at the scheduled time, similar to other jobs. You can choose to save the processed report to a file, such as an Excel, Word, or PDF, print it to a selected printer, or process the report only. If you choose to save the report to a file, then the processed report is sent to the **Report Inbox** area on your Home page, where you can view it.

You can schedule a report when you open a report. You choose the **Schedule** action and then you enter information such as printer, and time and date. The report is then added to the job queue and will be run at the specified time. When the report is processed, the item will be removed from the job queue. If you saved the processed report to a file, it will be available in the **Report Inbox** area.

## <a name="PrintReport"></a>Print a Report
When you want to print a report you have to download the report as a PDF, Word, or Excel document first by choosing **Send to**. Now, you can either open the report document right-away and print it, or save it and print it later.

## Saved Settings
A report can include one or more entries in the **Saved Settings** box. *Saved settings* are basically a predefined group of options and filters that you can apply to the report before previewing or sending to file. Using saved settings is a fast and reliable way to consistently generate reports that contain the correct data. You can see the saved settings that are available to you for a report in **Saved Settings** section of the report request page.

The saved settings entry called **Last used options and filters** is always available. This entry set the report to the option and filter values that were used the last time you ran the report.

>[!NOTE]
>As an administrator, you can create and manage the saved settings for reports. For more information, see [Managing Saved Settings on Reports](reports-saving-reusing-settings.md).

## See Also
[Specify Printer Selection for Reports](ui-specify-printer-selection-reports.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
