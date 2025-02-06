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

The Change Log captures changes people make to the definitions for financial reports. For example, you can find out what changed, who changed it, and when the change was made.

To use the Change Log for financial reporting, you specify the tables you want it to monitor. The following table lists the tables and their IDs.

| Table | Table ID |
|------ | -------- |
| Report Definition       | 88  |
| Row Definition          | 84  |
| Column Definition       | 333 |

To learn more about the Change Log, go to [Log changes](across-log-changes.md).

## Get notified when financial report definitions change

To add an extra layer of security around your financial report definitions, you can monitor changes to their fields and get an email when someone changes a value. 

To learn more, go to [Get notified when system setup change](across-setup-auditing.md#get-notified-when-system-setup-change)

## Analyze changes to financial report definitions

You can use the Data Analysis feature to answer questions such as:

- Which definition changed?
- Who changed it, and when?

To learn more, go to [Analyze changes to your setup](across-setup-auditing.md#analyze-changes-to-your-setup).

## Permissions to view or edit financial reports

The following table lists the permission sets that control whether you can view or edit financial reports and their report definitions.

| Access   | Permission set |
|------------------------| ---------------------- |
| View financial reports. | **Account Schedules - View** |
| Edit financial report definitions, including row and column definitions. | **Account Schedules - Edit** |

## Related information

[Prepare financial reporting](bi-how-work-account-schedule.md)  
[Financial analytics overview](bi.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]