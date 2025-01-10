---
title: Financial Reporting Auditing
description: Describes how to audit use and change of financial reports
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
# Financial Reporting Auditing

The **Financial Reports** feature gives users insights into the financial data shown on your chart of accounts (COA). 

This article explain ways you can audit changes to your financial report definitions and how to control access to financial reports.

## Setting up change log on financial report definitions

Using the Change Log feature, you can log any changes done to financial report definitions, such as what changed, who changed it, and when the change was made.

The following table lists the table and their Ids you need for setting this up.

| To track changes for... | Enable change log on table with Id |
| ----------------------- | ---------------------------------- |
| Report Definition       | 88  |
| Row Definition          | 84  |
| Column Definition       | 333 |

To learn more, go to [Log changes](across-log-changes.md).


## Get notified when financial report definitions change

To add an extra layer of security around your financial report definitions, you can monitor changes to their fields and get an email when someone changes a value. 

To learn more, go to [Monitor sensitive fields](across-log-changes.md#monitor-sensitive-fields).


## Analyze changes to financial report definitions

You can use the Data Analysis feature to analyze scenarios such as *Who changed what definition, and when* or *Which definitions were changed when, and by who*. 

To learn more, go to [Analyze data in the Change Log](across-log-changes.md#analyze-data-in-the-change-log).


## Permissions for viewing or editing financial reports

The following table lists the permission sets that control whether a user can view financial reports or edit financial report definitions.

| Access   | Permission set |
|------------------------| ----------------------- |
| View financial reports. | **Account Schedules - View** |
| Edit financial report definitions, including row and column definitions. | **Account Schedules - Edit** |

## See also

[Prepare financial reporting](bi-how-work-account-schedule.md)  
[Financial analytics overview](bi.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]