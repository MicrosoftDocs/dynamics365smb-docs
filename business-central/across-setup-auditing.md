---
title: Audit changes to your setup
description: Learn how to track the changes people make to your setup.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 02/06/2025
ms.custom: bap-template
ms.search.keywords: auditing
ms.search.form: 103, 108, 488
ms.service: dynamics-365-business-central
---

# Audit changes to your setup

[!INCLUDE[prod_short](includes/prod_short.md)] allows you to configure your system in many ways. This article explains ways to monitor changes to your setup for financial auditing.

## Set up the Change Log to capture changes

You can use the Change Log feature to capture changes to your setup. For example, you can find out what changed, who changed it, and when the change was made.

To use the Change Log to monitor your setup, you must specify the tables you want it to monitor. The following table lists some examples of finance setup tables where you might want to setup change tracking. To learn more about the Change Log, go to [Log changes](across-log-changes.md).

| If you want to audit changes to... | Table | Table ID | Learn more... |
| ---------------------------------- | ----- | -------- | ------------- |
| Financial Reporting  | Report Definition | 88  | [Audit changes to financial reporting](finance-financial-reporting-auditing.md) |
| Financial Reporting  | Row Definition    | 84  | [Audit changes to financial reporting](finance-financial-reporting-auditing.md) |
| Financial Reporting  | Column Definition | 333 | [Audit changes to financial reporting](finance-financial-reporting-auditing.md) |
| General ledger (G/L) | G/L Account       | 15 | [Audit changes to G/L accounts setup](finance-chart-of-accounts.md#audit-changes-to-gl-accounts-setup) |
| General ledger (G/L) | G/L Account Category | 570 | [Audit changes to account categories](bi-account-categories.md#audit-changes-to-account-categories) |
| Payment methods      | Payment Method    | 289 | [Audit changes to payment methods](finance-payment-methods.md#audit-changes-to-payment-methods) |
| Payment terms        | Payment Terms     | 3 | [Audit changes to payment terms](finance-payment-terms.md#audit-changes-to-payment-terms ) |
| Posting groups       | Gen. Product Posting Group | 251 | [Audit changes to posting groups](finance-posting-groups.md#audit-changes-to-posting-groups) |
| Posting groups       | Customer Posting Group | 92 | [Audit changes to posting groups](finance-posting-groups.md#audit-changes-to-posting-groups) |
| Posting groups       | Inventory Posting Group | 94 | [Audit changes to posting groups](finance-posting-groups.md#audit-changes-to-posting-groups) |
| Posting groups       | FA Posting Group | 5606 | [Audit changes to posting groups](finance-posting-groups.md#audit-changes-to-posting-groups) |
| Posting groups       | Vendor Posting Group | 93 | [Audit changes to posting groups](finance-posting-groups.md#audit-changes-to-posting-groups) |


To learn more about setting up the finance area, go to [Setting Up Finance](finance-setup-finance.md).

> [!TIP]
> If you want to track changes to data that isn't shown in the table, you can use the page inspection tool on the page that shows the data to find the corresponding table name and ID. To learn more, go to [Inspecting and Troubleshooting Pages](/dynamics365/business-central/dev-itpro/developer/devenv-inspecting-pages?tabs=table) in the [!INCLUDE[dev-itpro-docs](includes/dev-itpro-docs.md)].

## Get notified when system setup change

To add an extra layer of security to your setup, you can monitor changes to fields and get an email when someone changes a value. To learn more, go to [Monitor sensitive fields](across-log-changes.md#monitor-sensitive-fields).

## Analyze changes to your setup

You can use the Data Analysis feature to answer questions such as:

- Which definition changed?
- Who changed it, and when?

:::image type="content" source=" media/data-analysis-change-log-entries-Who-changed-What-data-When.png" alt-text="Example of how to do data analysis on the Change Log Entries page (Who changed What data When)." lightbox="media/data-analysis-change-log-entries-Who-changed-What-data-When.png":::

To learn more, go to [Analyze data in the Change Log](across-log-changes.md#analyze-data-in-the-change-log).

## Related information

[Log changes](across-log-changes.md)  
[Monitor sensitive fields](across-log-changes.md#monitor-sensitive-fields)  

[!INCLUDE[footer-include](includes/footer-banner.md)]