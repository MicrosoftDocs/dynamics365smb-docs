---
title: Audit changes to your setup
description: Learn how to track the changes people make to your setup.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 01/20/2024
ms.custom: bap-template
ms.search.keywords: auditing
ms.search.form: 103, 108, 488
ms.service: dynamics-365-business-central
---

# Audit changes to your setup

[!INCLUDE[prod_short](includes/prod_short.md)] allows you to configure your system in many ways. This article explains ways to monitor changes to your setup.

## Set up change log for system setup 

You can use the Change Log feature to capture changes users make to your setup. For example, you can find out what changed, who changed it, and when the change was made.

To use the Change Log for system setup, you must specify the tables you want it to monitor. 

> [!TIP]
> If you want to track changes to data that is not shown in the table, you can use the page inspection tool on the page that shows the data to find the corresponding table name and ID. For learn more, go to [Inspecting and Troubleshooting Pages](/dynamics365/business-central/dev-itpro/developer/devenv-inspecting-pages?tabs=table) in the 
[!INCLUDE[dev-itpro-docs](includes/dev-itpro-docs.md)].

To learn more about the Change Log, go to [Log changes](across-log-changes.md).

### Audit changes to your finance setup

The following table lists some examples of finance setup tables where you might want to setup change tracking.

| If you want to audit changes to... | Table | Table ID |
| ---------------------------------- | ----- | -------- |
| Financial Reporting | Report Definition | 88  |
| Financial Reporting | Row Definition    | 84  |
| Financial Reporting | Column Definition | 333 |
| Payment methods     | Payment Method    | 289 |
| Payment terms       | Payment Terms     | 3 |
| Posting groups      | Gen. Product Posting Group | 251 |
| Posting groups      | Customer Posting Group | 92 |
| Posting groups      | Inventory Posting Group | 94 |
| Posting groups      | FA Posting Group | 5606 |
| Posting groups      | Vendor Posting Group | 93 | 


## Get notified when system setup change

To add an extra layer of security around your system setup, you can monitor changes to their fields and get an email when someone changes a value. To learn more, go to [Monitor sensitive fields](across-log-changes.md#monitor-sensitive-fields).

## Analyze changes to system setup

You can use the Data Analysis feature to answer questions such as:

- Which definition changed?
- Who changed it, and when?

:::image type="content" source=" media/data-analysis-change-log-entries-Who-changed-What-data-When.png" alt-text="Example of how to do data analysis on the Change Log Entries page (Who changed What data When)." lightbox="media/data-analysis-change-log-entries-Who-changed-What-data-When.png":::

To learn more, go to [Analyze data in the Change Log](across-log-changes.md#analyze-data-in-the-change-log).

## Related information

[Log changes](across-log-changes.md)  
[Monitor sensitive fields](across-log-changes.md#monitor-sensitive-fields)  
[Setting Up Finance](finance-setup-finance.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]