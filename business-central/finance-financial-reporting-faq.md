---
title: Financial Reporting FAQ
description: FAQ for the Financial Reporting feature in Business Central.
author: kennieNP
ms.topic: get-started
ms.date: 1/7/2025
ms.author: kepontop
ms.reviewer: bholtorf
ms.search.keywords: bi, power BI, analysis, KPI, account schedule, financial report
ms.search.form: Report_25, 103, 104, 108, 195, 196, 197, 198, 488, 489, 490, 764, 765, 766
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Frequently asked questions about the Financial Reporting feature in Business Central.

This article provides answers to frequently asked questions (FAQs) about the Financial Reporting feature in Business Central.

<!-- This question is not ready for publish
## New report/row/column definitions are not available after an upgrade. How do I get access to them?

Finanical report/row/column definitions are stored as data in the [!INCLUDE [prod_short](prod_short.md)] database. To make sure your definitions are not overwritten or changed during upgrades, new report/row/column definitions are only available in new [!INCLUDE [prod_short](prod_short.md)] companies. 

If you want to make new report/row/column definitions available in existing companies, do as follows:
1. creating a new company 
1. Export the definitions you would like as configuration packages. 
1. Shift to the company where you want the new definitions.
1. Import configuration packages with the new definitions. 

To learn more, go to [Import or export financial report definitions](bi-how-work-account-schedule.md#import-or-export-financial-report-definitions). 
-->

## Which users are allowed to run or modify financial reports?

To learn more, go to [Permissions for viewing or editing financial reports](bi-how-work-account-schedule.md#permissions-for-viewing-or-editing-financial-reports).

## Why does numbers in my report not balance to the general ledger?

When you create new financial reports, you might find that they don't balance to the general ledger. To learn more about possible reasons and ways to fix these issues, go to [Troubleshoot Financial Reporting](bi-troubleshoot-financial-reports.md#balancing-reports-to-the-general-ledger).

## How can I add tests to my reports?

One way to quickly identify errors in the design of your financial reporting is to add check figures to your row definitions. To learn more, go to [Troubleshoot Financial Reporting](bi-troubleshoot-financial-reports.md#adding-check-figures).

## When should I use net change vs. balance at date?

A typical mistake that financial reporting users make is to incorrectly combine row and column definitions. When column definitions use net change as the row type, the columns are most appropriately combined with income statement reports. When column definitions use balance at date as the row type, the columns are most appropriately combined with balance sheet reports. To learn more, go to [Troubleshoot Financial Reporting](bi-troubleshoot-financial-reports.md#when-to-use-net-change-or-balance-at-date).


## More Information

[Troubleshoot Financial Reporting](bi-troubleshoot-financial-reports.md)  
[Prepare financial reporting](bi-how-work-account-schedule.md)  
[Financial analytics overview](bi.md)  