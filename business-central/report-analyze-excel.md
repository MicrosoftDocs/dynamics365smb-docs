---
title: Analyzing report data with Excel and XML
description: Learn how to use Excel and XML to analyze a report dataset. 
author: jswymer
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: task, process, report, print, schedule, save, Excel, PDF, Word, dataset
ms.date: 09/09/2024
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---
# Analyzing report data with Excel and XML

[!INCLUDE[2021_releasewave2](includes/2021_releasewave2.md)]

As a developer or advanced user, it helps to inspect the data that is generated for a given report dataset while you create new reports or modify existing ones. To support this capability, you can export a report dataset as raw data to an Excel workbook or XML file&mdash;directly. In Excel, for example, you can then do ad-hoc analysis of the data and diagnose issues.

## Get started

To export a report dataset to an Excel workbook or XML file, open the report in the client, then in the request page, select **Send to** > **Microsoft Excel Document (data only)** or **XML Document**. The file downloads to your device.

## More about Excel (data only)

The **Microsoft Excel Document (data only)** option exports the report results and the criteria used to generate them&mdash;but it doesn't include the report layout. The Excel file includes the full dataset, as raw data, arranged in rows and columns. All data columns of the report's dataset are included, regardless of whether they're used in the report layout.

Once you have the Excel file, you can start analyzing the data. For example, you could filter the data and use Power Pivot to display it.

Each time you export results, a new worksheet is created. Using the **Microsoft Excel Document (data only)** option, you can run the same report and reuse formatting changes. For example, for Power Pivot, you can run the report again for another time period, copy the results to the worksheet, and then refresh the worksheet. You can also find a reporting app on [Marketplace](https://marketplace.microsoft.com/).

> [!NOTE]
> You can't export a report that has more than 1,048,576 rows or 16,384 columns. With Business Central on-premises, the maximum number of exported rows might be even less. Business Central Server includes a configuration setting, called **Max Data Rows Allowed to Send to Excel**, for decreasing the limit from the maximum value. For more information, see [Configuring Business Central Server](/dynamics365/business-central/dev-itpro/administration/configure-server-instance#General) or contact your administrator.

## For administrators

- **Microsoft Excel Document (data only)** was introduced as an optional feature in the 2021 release wave 1, update 18.3. To give users access to this feature when running 2021 release wave 1, enable the **Save report dataset to Microsoft Excel Document** feature update in **Feature Management**. For more information, see [Enabling Upcoming Features Ahead of Time](/dynamics365/business-central/dev-itpro/administration/feature-management). In 2021 release wave 2, this feature became permanent.

- To use **Microsoft Excel Document (data only)**, user accounts need the **Allow Action Export Report Dataset To Excel** permission. You can give users this permission by assigning either the **Troubleshooting Tools** or **Export Report Excel** permission set. For more information, see [Assign Permissions to Users and Groups](ui-define-granular-permissions.md)  

## For developers and advanced users

The **Microsoft Excel Document (data only)** option exports all columns, including columns that hold filters and formatting instructions for other values. Here are a few points of interest:

- Binary data in a field, like an image, isn't exported.

  In columns that hold binary data, fields include the text **Binary data ({0} bytes)**, where **{0}** indicates the number of bytes.
- The Excel file also includes the **Report Metadata** worksheet.

  This worksheet shows the filters applied to the report and general report properties, like the name, ID, and extension details. The filters are shown in the **Filter (DataItem::Table::FilterGroupNo::FieldName)** column. The filters in this column include filters set on the report's request page. It also includes filters defined in AL code, for example, by the [DataItemLink property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-dataitemlink-reports-property) and [DataItemTableView property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-dataitemtableview-property).

For more information about report design, see [Report Overview](/dynamics365/business-central/dev-itpro/developer/devenv-reports).

## Related information

[Working with Reports](ui-work-report.md)  
[Managing Report and Document Layouts](ui-manage-report-layouts.md)  
[Assign Permissions to Users and Groups](ui-define-granular-permissions.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
