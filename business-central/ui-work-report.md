---
title: Working with Reports, Batch Jobs, and XMLports
description: Learn about entering a report into a job queue and scheduling it to be processed at a specific date and time.
author: jswymer

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: task, process, report, print, schedule, save, Excel, PDF, Word, dataset
ms.date: 06/21/2021
ms.author: jswymer

---
# Working with Reports, Batch Jobs, and XMLports

A report gathers information based on a specified set of criteria. It organizes and presents the information in an easy-to-read format that you can print or save as a file. There are many reports that you can access throughout the application. The reports typically provide information related to the context of the page you're on. For example, the **Customer** page includes reports for the top 10 customers, sales statistics, and more.

Batch jobs and XMLports do more or less the same as reports, but are used more for processing or exporting data. For example, the **Create Reminders** batch job creates reminder documents for customers with overdue payments.  

> [!NOTE]
> This topic refers mainly to "report", but similar information applies to batch jobs and XMLports.

## Getting Started

You find reports in the **Reports** tab on selected pages, or you can use search ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") to find reports by name.

When you open a report, batch job, or XMLport, you're typically presented with a request page where you set various options and filters that determine what to include in the report. The following sections explain how to use the request page to build, preview, and print a report.

## <a name="SavedSettings"></a>Using default values - predefined settings 

Most request pages include the **Use default values from** field. This field lets you select predefined settings for the report, which automatically set options and filters for the report. Select an entry from the drop-down list, and you'll see the options and filters on the request page change accordingly.

The entry called **Last used options and filters** is always available. This entry sets the report to use options and filters that were used the last time you ran the report.

The **Use default values from** field provides a fast and reliable way to consistently generate reports that contain the correct data. After you select an entry, you can change any of the options and filters before previewing or printing the report. The changes that you make won't be saved to the predefined settings entry you selected, but they'll be saved to the **Last used options and filters** entry.

>[!NOTE]
> The predefined settings are typically set up and managed by an administrator. If you want to learn more, see [Manage Saved Settings for Reports and Batch Jobs](reports-saving-reusing-settings.md).

## Specifying the Data to Include in Reports

Use the fields under **Options** and **Filters** to change limit the information you want in the report. You set filters in a report in more or less the same way as you set filters on lists. For more information, see [Filtering](ui-enter-criteria-filters.md#filtering).

> [!CAUTION]
> The **Filter list by** section on a request page provides a generic filtering capability for reports. These filters are optional.
>
> Some reports will ignore any such filters, meaning that no matter what filter is set in the **Filter list by** section, the output of the report is the same. It's not possible to provide a list of which fields are ignored in which reports, so you will have to experiment with the filters when using them.
>
> **Example**: When you use the **Create Reminders** batch job, a filter for the **Customer Ledger Entries** field of **Last Issued Reminder Level** will be ignored because filters are fixed for that batch job.

## Previewing a Report

Previewing a report lets you see what the report will look like before you print it. The preview isn't based on the printer selected in the **Printer** field on the request page. It's controlled by the browser. After previewing, you can then go back to the request page and make changes to options and filters as needed.

To preview a report, choose the **Preview** or **Preview & Close** button on the report request page. The button that displays depends on the report, so some reports have **Preview** button, while others have a **Preview & Close** button. Both buttons will open a preview of the report. The difference is that **Preview** keeps the request page open, so you can go back to it, make changes, preview again, or print. With **Preview & Close**, the request page closes, so you'll have to open the report again to make changes or print.

> [!NOTE]
> If you're using Business Central 2020 release wave 1 or earlier, there's only a **Preview** button, which closes the request page on preview, like described for **Preview & Close**.

### Working with the Preview

In the preview, use the menu bar on the report preview to:

- Move through pages
- Zoom in and out
- Resize to fit the page
- Select text

    You can copy text from a report, and then paste it somewhere else, like a page in [!INCLUDE[prod_short](includes/prod_short.md)] or Microsoft Word.  Using a mouse, for example, you press and hold where you want to start. Then move the mouse to select one or more words, sentences, or paragraphs. Press the right mouse button and select **Copy**. Then, paste the selected text where you want it.
- Pan the document

    You can move the visible area of the report in any direction so you can view other areas or the report. Panning is helpful when you've zoomed in to see details.  Using your mouse, for example, press and hold the mouse button anywhere in the report preview, and then move your mouse.

- Download to a PDF file on your computer or network.
- Print

## Saving a Report to a File

You can save a report to a PDF document, Microsoft Word document, or Microsoft Excel worksheet by choosing the **Send to** button, and then making your selection.

### Send to Excel

<!-- The following table describes the options for saving the report results as a worksheet in an Excel workbook.

|Option  |Description  |
|---------|---------|
|Microsoft Excel Document (data and layout)|Export the report results with the RDLC layout applied. Use this option if you want to export the data one time, and only want to make minor changes to its appearance, such as font and color scheme. <br><br>**Note**: Some reports might export numbers as text, so it's a good idea to verify the numbers. |
|Microsoft Excel Document (data only)|Export the report results and the criteria that was used to generate them, such as the parameters you specified on the request page, metadata, and the fields that control the layout of the printed report. Use this option when you want to do ad hoc analysis of the data or diagnose data issues in reports. For example, you can filter the data and use Power Pivot to display it.<br><br>This option exports all columns, including columns that hold formatting instructions for other values and filters. In columns that hold binary data like images, instead of actually values, fields will include the text **Binary data ({0} bytes)**, where **{0}** indicates the number of bytes.<br><br>**NOTE** With Business Central on-premises, the Business Central Server includes a configurations setting, called **Max Data Rows Allowed to Send to Excel**. This setting limits the number of rows that can be exported to Excel. If you don't see the expected number of rows, it might be because of this setting. For more information, see [Configuring Business Central Server](/dynamics365/business-central/dev-itpro/administration/configure-server-instance#General) or contact your administrator.|-->

There are two options for saving the report results as a worksheet in an Excel workbook: **Microsoft Excel Document (data and layout)** and **Microsoft Excel Document (data only)**

#### [Microsoft Excel Document (data and layout)](#tab/data-and-layout)

This option is only available for reports that use an RDLC layout. It exports the report results with the RDLC layout applied. Use this option if you want to export the data one time, and only want to make minor changes to its appearance, such as font and color scheme.

#### <a name="exportdataonly"></a>[Microsoft Excel Document (data only)](#tab/data-only)

The **Microsoft Excel Document (data only)** option exports the report results and the criteria that was used to generate them&mdash;but it doesn't include the report layout. The Excel file will include the full dataset, as raw data, arranged in rows and columns. All data columns of the report's dataset are included, regardless of whether they're used in the report layout.  Use this option when you want to:

- Do ad hoc analysis of the data. For example, you can filter the data and use Power Pivot to display it.

  Each time you export results, a new worksheet is created. Using the **Microsoft Excel Document (data only)** option, you can run the same report and reuse formatting changes. For example, for Power Pivot, you can run the report again for another time period, copy the results to the worksheet, and then refresh the worksheet. You can also find a reporting app on [AppSource](https://appsource.microsoft.com/).
- Inspect the report dataset when you're creating or modifying custom report layouts.

  For information about creating custom report layouts, see [Creating or Modifying Custom Report Layouts](ui-how-create-custom-report-layout.md)
- Diagnose data issues in reports.

##### For administrators

- **Microsoft Excel Document (data only)** was introduced as an optional feature in the 2021 release wave 1, update 18.3. To give users access to this feature, enable the **Save report dataset to Microsoft Excel Document** feature update in **Feature Management**. For more information, see [Enabling Upcoming Features Ahead of Time](/dynamics365/business-central/dev-itpro/administration/feature-management). In 2021 release wave 2, this feature becomes permanent, so you won't have to enable it.

- User accounts will need the **<!--Export Report Dataset To Excel-->Allow Action Export Report Dataset To Excel** permission, which you can apply by using the **Troubleshooting Tools** permission set or **Export Report Excel** permission set.  

- You can't export a report that has more than 1,048,576 rows or 16,384 columns.

    > [!NOTE]
    > With Business Central on-premises, the maximum number of exported rows might be even less. Business Central Server includes a configuration setting, called **Max Data Rows Allowed to Send to Excel**, for decreasing the limit from the maximum value. For more information, see [Configuring Business Central Server](/dynamics365/business-central/dev-itpro/administration/configure-server-instance#General) or contact your administrator.

##### For developers and advanced users

The **Microsoft Excel Document (data only)** option exports all columns, including columns that hold filters and formatting instructions for other values. Here are a few points of interest:

- Binary data in a field, like an image, isn't exported.

  In columns that hold binary data, fields will include the text **Binary data ({0} bytes)**, where **{0}** indicates the number of bytes.
- Starting in Business Central 2021 release wave 2, the Excel file also includes the **Report Metadata** worksheet.

  This worksheet shows the filters applied to the report and general report properties, like the name, ID, and extension details. The filters are shown in the **Filter (DataItem::Table::FilterGroupNo::FieldName)** column. The filters in this column include filters set on the report's request page. It also includes filters defined in AL code, for example, by the [DataItemLink property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-dataitemlink-reports-property) and [DataItemTableView property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-dataitemtableview-property).

For more information about report design, see [Report Overview](/dynamics365/business-central/dev-itpro/developer/devenv-reports).

---

> [!NOTE]
> Some reports export numbers as text, which prevents you from doing calculations or using Power Pivot on the cells in the Excel worksheet. After exporting, it's a good idea to verify the numbers in the worksheet. If you want to do analysis and charting on the numbers, change the format of the relevant cells from **Text** to **Number**. For more information about formatting numbers in cells, see this video [Formatting Numbers in Cells in Microsoft Excel](https://www.youtube.com/watch?v=2suE4YmZu_Q).

### Microsoft Word Document
Use the **Microsoft Word Document** option to generate a report as a Word document.  

> [!NOTE]
> You can specify the layout to use for each report on the **Report Selection** page in the **Selected Layout** field. The default setting for reports is **RDLC (built-in)**, which produces reports in the same, or similar, layout as the **Microsoft Word Document** layout. However, the key difference is whether you want to generate a single or multiple report documents. For single documents, you can use the RDLC (built-in) option. For multiple documents, set the **Microsoft Word Document** as the default layout for the report. For more information, see [Managing Report and Document Layouts](ui-manage-report-layouts.md).

## <a name="ScheduleReport"></a> Scheduling a Report to Run

You can schedule or batch job a report to run at a specific date and time. Scheduled reports and batch jobs are entered in the job queue and processed at the scheduled time, similar to other jobs. You choose the **Schedule** option after you choose the **Send to** button, and then you enter information such as printer, and time and date. The report is then added to the job queue and will be run at the specified time. When the report is processed, the item will be removed from the job queue. For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).  

When you schedule a report to run, you can specify that it must run every Thursday by setting the **Next Run Date Formula** field to *D4*, for example. For more information, see [Using Date Formulas](ui-enter-date-ranges.md#using-date-formulas).  

You can choose to save the report to a file (like Excel, Word, or PDF), print it, or only generate the report. If you choose to save the report to a file, then the processed report is sent to the **Report Inbox** area on your Role Center, where you can view it.  

## <a name="PrintReport"></a>Printing a Report

To print a report, choose the **Print** button on the request page or on the menu bar of the **Preview** page.

### <a name="Printer"></a>Printer

The **Printer** field on the request page shows the name of printer that the report will be sent to. To change a printer, just select the printer from the list.

> [!NOTE]
> **(Handled by the browser)** indicates there's no designated printer for the report. In this case, the browser will handle the printout and display a standard experience, where you can choose a local printer connected to your device. **(Handled by the browser)** isn't available in the [!INCLUDE[prod_short](includes/prod_short.md)] mobile app or app for Microsoft Teams.

> [!TIP]
> The printer that's selected for you by default is set up on the **Printer Selections** page. For information about changing the default printer, see [To select which printers print which reports](ui-specify-printer-selection-reports.md#default).

### Printing Reports in Thai

Specifically for the Thai version of [!INCLUDE[prod_short](includes/prod_short.md)], the **Print** button can't print reports correctly because of limitations in the service that generates the printable PDF file. Instead, you can open the report in Word and then save the report as a printable PDF.  

Or, you can ask your administrator to create a Word report layout for your most used reports. For more information, see [Managing Report and Document Layouts](ui-manage-report-layouts.md).  

## Changing Report Layouts

A report layout controls what is shown on a report, how it's arranged, and how it's styled. If you want to switch to a different layout, see [Change the Current Report Layout](ui-how-change-layout-currently-used-report.md). Or, if you want to customize your own report layout, see [Create and Modify a Custom Report Layout](ui-how-create-custom-report-layout.md).

## Advanced options

The fields under **Advanced** set limitations on the generated report to control printer resources. You typically won't have to change these settings, unless you have a large report. If a report exceeds these limitations when you try to preview or print, a message appears telling you which limitation was exceeded. You can then change the settings to suit your report. Each field, however, has a maximum value that you should be aware of:

|Field|Maximum value|
|-----|-------------|
|Maximum rendering time|12:00:00|
|Maximum rows|1000000|
|Maximum documents|500|

> [!NOTE]
> The maximum values may be different for [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, and an administrator can change them. For more information, see [Configuring Business Central Server - Reports](/dynamics365/business-central/dev-itpro/administration/configure-server-instance#Reports). For an overview of reports limitations [!INCLUDE[prod_short](includes/prod_short.md)] online, see [Operational Limits](/dynamics365/business-central/dev-itpro/administration/operational-limits-online).

## See Also

[Set Up Printers](ui-specify-printer-selection-reports.md)  
[Working with Calendar Dates and Times](ui-enter-date-ranges.md)  
[Managing Report and Document Layouts](ui-manage-report-layouts.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]