---
title: Statutory reports in Russia
description: Russian enhancements include support for statutory reports.
author: DianaMalina


ms.topic: conceptual
ms.search.keywords:
ms.date: 04/01/2021
ms.reviewer: edupont
ms.author: soalex
---

# Statutory Reports

[!INCLUDE[prod_short](../../includes/prod_short.md)] lets you set up statutory reports so that you can import and export data for electronic tax reporting and other required documents.

After you have set up a report and specified the required information, you can export the report to Excel, and then print the report.

## Getting Started with Statutory Reports

Use the windows based on the following key tables to set up and create statutory reports. 

| Tables                        | Description                                                  |
| :---------------------------- | :----------------------------------------------------------- |
| Statutory Report Setup        | Specifies information that is used to set up statutory reports including templates, formats, number series, and export destinations. |
| Format Version                | Specifies setup information about the different report formats. This includes when to use which report, the XML schema to use, and the required data format. |
| Statutory Report              | Specifies a list of statutory reports with detailed information, such as type, format version, and if the statutory report is currently active. From this window, you can define statutory report tables, requisites groups, the XML element lines, and you can export data. |
| Statutory Report Table        | Specifies information that is required to set up reporting tables including scalability limits, templates, and standard text.   From this window, you can define table rows, columns, individual requisites, and data source mapping. |
| Stat. Report Table Row        | Allows you to define row formats and functions for your statutory report tables. |
| Stat. Report Table Column     | Allows you to define column formats for your statutory report tables. |
| Stat. Report Requisites Group | Specifies the conditions used to format and process statutory reports including export type, Microsoft Excel mapping, and cell quantity. |

## Data for Statutory Reports

The statutory reports are based on account schedules and tax registers. For each statutory report that you set up in the **Statutory Reports** window, you define how the data maps to fields on tables in Dynamics NAV by creating table mappings. In the **Statutory Report Tables** window, in the **Int. Source Type** field, you specify the area that the data comes from as described in the following table.

| Option                      | Description                                                  |
| :-------------------------- | :----------------------------------------------------------- |
| **Acc. Schedule**           | The data is based on an account schedule.                    |
| **Tax Register**            | The data is based on a tax register. For more information, see [Tax Registers](tax-registers.md). |
| **Tax Difference**          | The data is based on a tax difference. For more information, see [Tax Differences](tax-differences.md). |
| **Payroll Analysis Report** | The data is based on payroll analysis.                       |

## See Also

[Tax Accounting](Tax-Differences.md)  
[Tax Differences](Tax-Accounting.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]