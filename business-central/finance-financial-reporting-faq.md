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

# Financial Reporting frequently asked questions (FAQ)

This article provides answers to frequently asked questions about the Financial Reporting feature in [!INCLUDE [prod_short](includes/prod_short.md)].

## New report, row, or column definitions aren't available after an upgrade. How do I get access to them?

Financial report, row, and column definitions are stored as data in the [!INCLUDE [prod_short](includes/prod_short.md)] database. To make sure your definitions aren't overwritten or changed during upgrade, new definitions are only available in new [!INCLUDE [prod_short](includes/prod_short.md)] tenants.

To make new report, row, or column definitions available in existing companies, follow these steps:

1. Create a new tenant.
1. Export the definitions you would like as configuration packages.
1. Sign in to your tenant, and switch to the company where you want the new definitions.
1. Import the configuration packages with the new definitions.

To learn more, go to [Import or export financial report definitions](bi-how-work-account-schedule.md#import-or-export-financial-report-definitions).

## Why don't the numbers in my report balance with the general ledger?

When you create new financial reports, you might find that they don't balance with the general ledger. To learn more about possible reasons and ways to fix these issues, go to [Balancing reports to the general ledger](bi-troubleshoot-financial-reports.md#balancing-reports-to-the-general-ledger).

## How can I test my report?

One way to quickly identify errors in the design of your financial reporting is to add check figures to your row definitions. To learn more, go to [Adding check figures](bi-troubleshoot-financial-reports.md#adding-check-figures).

## When should I use net change vs. balance at date?

A typical mistake that financial reporting users make is to incorrectly combine row and column definitions. When column definitions use net change as the row type, the columns are most appropriately combined with income statement reports. When column definitions use balance at date as the row type, the columns are most appropriately combined with balance sheet reports. To learn more, go to [When to use net change or balance at date](bi-troubleshoot-financial-reports.md#when-to-use-net-change-or-balance-at-date).

## Which users can run or modify financial reports?

To learn more, go to [Permissions to view or edit financial reports](finance-financial-reporting-auditing.md#permissions-to-view-or-edit-financial-reports).

## How can I setup auditing on changes to financial reports?

To learn more, go to [Set up the Change Log for financial report definitions](finance-financial-reporting-auditing.md#set-up-the-change-log-for-financial-report-definitions).

## How can I get notified when financial report definitions change?

To learn more, go to [Get notified when financial report definitions change](finance-financial-reporting-auditing.md#get-notified-when-financial-report-definitions-change).

## How can I analyze changes to financial reports?

To learn more, go to [Analyze changes to financial report definitions](finance-financial-reporting-auditing.md#analyze-changes-to-financial-report-definitions).

## Related information

[Troubleshoot Financial Reporting](bi-troubleshoot-financial-reports.md)  
[Prepare financial reporting](bi-how-work-account-schedule.md)  
[Financial analytics overview](bi.md)  