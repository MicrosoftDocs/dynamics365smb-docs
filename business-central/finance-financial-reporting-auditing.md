---
title: Audit changes to financial reporting
description: Learn how to track the changes people make to your financial reports.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 01/10/2024
ms.custom: bap-template
ms.search.keywords: account schedule, financial report, auditing
ms.search.form: Report_25, 103, 108, 488
ms.service: dynamics-365-business-central
---
# Audit changes to financial reporting

Financial reporting helps you gather insights into the financial data in your chart of accounts (COA). This article explains ways to monitor changes to your financial report definitions, and how to control access to financial reports.

## Set up the Change Log for financial report definitions

You can use the Change Log feature to capture changes users make to the definitions for financial reports. [!INCLUDE [include-audit-what-who-when](includes/include-audit-what-who-when.md)] 

The following table lists the table for financial report definitions and their IDs.

| Table | Table ID |
|------ | -------- |
| Report Definition       | 88  |
| Row Definition          | 84  |
| Column Definition       | 333 |

[!INCLUDE [include-audit-changes-to-setup-learn-more-link](includes/include-audit-changes-to-setup-learn-more-link.md)]

## Get notified when financial report definitions change

To add an extra layer of security around your financial report definitions, you can monitor changes to their fields and get an email when someone changes a value. 

To learn more, go to [Get notified when system setup change](across-setup-auditing.md#get-notified-when-system-setup-change)

## Analyze changes to financial report definitions

You can use the Data Analysis feature to answer questions such as:

- Which definition changed?
- Who changed it, and when?

To learn more, go to [Analyze changes to your setup](across-setup-auditing.md#analyze-changes-to-your-setup).

## Telemetry on changes to financial report definitions  

If the telemetry feature is enabled on the [!INCLUDE[prod_short](includes/prod_short.md)] environment, administrators can analyze when any change happened to a financial report/row/column definition.

To learn more, go to [Analyzing financial report lifecycle telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-financial-report-lifecycle-trace?toc=/dynamics365/business-central/toc.json)

## Telemetry on usage of financial reports

If the telemetry feature is enabled on the [!INCLUDE[prod_short](includes/prod_short.md)] environment, administrators can analyze who uses financial reports and when.

To learn more, go to [Analyzing financial report usage telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-financial-report-usage-trace?toc=/dynamics365/business-central/toc.json)

## Permissions to view or edit financial reports

The following table lists the permission sets that control whether you can view or edit financial reports and their report definitions.

| Access   | Permission set |
|------------------------| ---------------------- |
| View financial reports. | **Account Schedules - View** |
| Edit financial report definitions, including row and column definitions. | **Account Schedules - Edit** |


<!-- 
## Audit changes to financial report definitions with Microsoft Purview

2025w1: add link to purview administrator article 
-->

## Related information
<!-- 
2025w1: add links to administrator article for Purview
-->
[Analyzing financial report usage telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-financial-report-usage-trace?toc=/dynamics365/business-central/toc.json)
[Analyzing financial report lifecycle telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-financial-report-lifecycle-trace?toc=/dynamics365/business-central/toc.json)
[Prepare financial reporting](bi-how-work-account-schedule.md)  
[Financial analytics overview](bi.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]