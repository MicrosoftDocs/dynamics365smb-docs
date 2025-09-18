---
title: Statutory reports in Russia
description: Russian localization provides features for statutory reporting compliance.
author: DianaMalina
ms.topic: article
ms.search.keywords: statutory report, tax report, tax reporting, tax compliance, financial report, Russia
ms.date: 07/21/2025
ms.reviewer: v-soumramani
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Statutory reports

You can set up statutory reports in [!INCLUDE[prod_short](../../includes/prod_short.md)] which gives you the ability to import and export data for electronic tax reporting and other required documents.

After you set up a report and specify the required information, you can export the report to Excel and then print it.

## Getting started with statutory reports

Use the pages based on the following key tables to set up and create statutory reports.

| Table | Description |
|:-|:-|
| Statutory Report Setup | Specifies information that is used to set up statutory reports including templates, formats, number series, and export destinations. |
| Format Version | Specifies setup information about the different report formats. This includes when to use which report, the XML schema to use, and the required data format. |
| Statutory Report | Specifies a list of statutory reports with detailed information, such as type, format version, and if the statutory report is currently active. From this page, you can define statutory report tables, requisites groups, and the XML element lines. You can also export data. |
| Statutory Report Table | Specifies information that is required to set up reporting tables including scalability limits, templates, and standard text.   From this page, you can define table rows, columns, individual requisites, and data source mapping. |
| Stat. Report Table Row | Allows you to define row formats and functions for your statutory report tables. |
| Stat. Report Table Column | Allows you to define column formats for your statutory report tables. |
| Stat. Report Requisites Group | Specifies the conditions used to format and process statutory reports including export type, Microsoft Excel mapping, and cell quantity. |

## Data for statutory reports

Statutory reports are based on financial reports and tax registers. For each statutory report you set up on the **Statutory Reports** page, you create table mappings to define how the data maps to fields on tables in [!INCLUDE[prod_short](../../includes/prod_short.md)]. On the **Statutory Report Tables** page, in the **Int. Source Type** field, you specify the area the data comes from as described in the following table.

| Option | Description |
|:-|:-|
| **Acc. Schedule** | The data is based on a financial report. |
| **Tax Register** | The data is based on a tax register. Learn more at [Tax Registers](tax-registers.md). |
| **Tax Difference** | The data is based on a tax difference. Learn more at [Tax Differences](tax-differences.md). |
| **Payroll Analysis Report** | The data is based on payroll analysis. |

## Related information

- [Tax Accounting](Tax-Accounting.md)  
- [Tax Differences](Tax-Differences.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
