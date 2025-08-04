---
title: Ad-hoc analyses in purchasing
description: Learn how to use the data analysis mode to analyze data in purchasing.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: bi, power BI, analysis, KPI
ms.search.form: 9306, 9307, 518, 29
ms.date: 04/29/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Ad-hoc analyses in purchasing

This article explains how to analyze purchasing data from list pages and queries using the **Data Analysis** feature. The feature lets you analyze data directly from the page, without having to run a report or open another application, such as Excel. Data Analysis provides an interactive and versatile way to calculate, summarize, and examine data. Instead of running reports using options and filters, you can add multiple tabs that represent different tasks or views on the data. Some examples are "My vendors," or "Purchasing statistics," or any other view you can imagine. To learn more about how to use the **Data Analysis** feature, go to [Analyze list and query data with analysis mode](analysis-mode.md).

Use the following list pages for ad-hoc analysis of purchase processes:

- [Purchase Orders](https://businesscentral.dynamics.com/?page=9307&layout=analysis)
- [Purchase lines](https://businesscentral.dynamics.com/?page=518&layout=analysis)
- [Posted Purchase Invoices](https://businesscentral.dynamics.com/?page=146&layout=analysis)
- [Vendor Ledger Entries](https://businesscentral.dynamics.com/?page=29&layout=analysis)
- [General Ledger Entries](https://businesscentral.dynamics.com/?page=20&layout=analysis)

## Ad-hoc analysis scenarios for purchasing

Use the **Data Analysis** feature for quick fact checking and ad-hoc analysis:

- If you don't want to run a report
- If there isn't a report for your specific needs
- If you want to quickly iterate to get a good overview on a part of your business.

The following sections provide examples of purchasing scenarios in [!INCLUDE [prod_short](includes/prod_short.md)].

| Area | To... | Open this page in analysis mode | Using these fields |
| ---- | ----- | ------------------------------- |------------------- |
| [GRNI overview](#example-goods-received-not-invoiced-grni-overview) | Get a Goods Received, Not Invoiced (GRNI) overview across vendors. | [Purchase lines](https://businesscentral.dynamics.com/?page=518&layout=analysis) | **Type**, **Amt. Rec. Not Invoiced (LCY)** (filter on these fields), **Vendor No.**, **Document No.**, **No.**, and **Amt. Rec. Not Invoiced (LCY)** <br><br> **NOTE:** You must personalize the page to add these fields. To learn more, go to [Personalize your workspace](ui-personalization-user.md). | 
| [Finance (Accounts Payable)](#example-finance-accounts-payable) | See what you owe your vendors, maybe broken down into time intervals for when amounts are due. | [Vendor Ledger Entries](https://businesscentral.dynamics.com/?page=29&layout=analysis) | **Vendor Name**, **Document Type**, **Document No.**, **Due Date Year**, **Due Date Month**, and **Remaining Amount**. |
| [Finance (Accounts Payable)](#example-finance-accounts-payable---vendor-ledger-entries-on-hold) | Get an overview of vendor ledger entries that have been marked On Hold | [Vendor Ledger Entries](https://businesscentral.dynamics.com/?page=29&layout=analysis) | **Vendor Name**, **Document Type**, **Document No.**, **On Hold**, and **Remaining Amount**. |


## Example: goods received, not invoiced (GRNI) overview

To create a goods received, not invoiced (GRNI) overview across vendors, follow these steps:

1. Open the [Purchase lines](https://businesscentral.dynamics.com/?page=518) list page.
1. Personalize the page to add the **Amount Received Not Invoiced** field. To personalize the page, choose **Settings**, and then **Personalize**.
1. Choose :::image type="content" source="media/analysis-mode-icon.png" alt-text="Enter analysis mode."::: to turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field on the right).
1. In the **Additional Filters** menu (located below the **Columns** menu on the right), set the following filters:
    - **Type = Item**
    - **Amt. Rec. Not Invoiced (LCY) > 0**. 
1. Drag the **Vendor No.**, **Document No.**, and **No.** fields to the **Row Groups** area. Drag the fields in that order.
1. Add the **Amt. Rec. Not Invoiced (LCY)** field to include it on the overview.
1. To do the analysis for a given year or quarter, apply a filter in the **Analysis Filters** menu. The menu is on the right of the page, just below the **Columns** menu.
1. Rename your analysis tab to **Goods Received, Not Invoiced (GRNI)**, or something that describes this analysis.

## Example: finance (accounts payable)

To see what you owe your vendors, maybe broken down into time intervals for when amounts are due, follow these steps:

1. Open the [Vendor Ledger Entries](https://businesscentral.dynamics.com/?page=29&layout=analysis) list page, and turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field on the right).
1. Turn on the **Pivot Mode** toggle (located above the **Search** field on the right).
1. Drag the **Vendor Name**, **Document Type**, and **Document No.** fields to the **Row Groups** area, and then drag the **Remaining Amount** field to the **Values** area.
1. Drag the **Due Date Year** and **Due Date Month** fields to the **Column Labels** area. Drag the fields in that order.
1. To do the analysis for a given year or quarter, apply a filter in the **Analysis Filters** menu (located below the **Columns** menu on the right).
1. Rename your analysis tab to **Aged Payable Accounts by Month**, or something that describes this analysis.

The following image shows the result of these steps.

:::image type="content" source="media/data-analysis-vendor-ledger-entries.png" alt-text="Example of how to do data analysis on the Customer Ledger Entries page." lightbox="media/data-analysis-vendor-ledger-entries.png":::

## Example: finance (accounts payable) - vendor ledger entries on hold

To see vendor ledger entries on hold, follow these steps:

1. Open the [Vendor Ledger Entries](https://businesscentral.dynamics.com/?page=29&layout=analysis) list page, and turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field on the right).
1. Turn on the **Pivot Mode** toggle (located above the **Search** field on the right).
1. Drag the **Vendor Name**, **Document Type**, and **Document No.** fields to the **Row Groups** area, and then drag the **Remaining Amount** field to the **Values** area.
1. Drag the **On Hold** field to the **Column Labels** area.
1. Rename your analysis tab to **Payments On Hold**, or something that describes this analysis.

The following image shows the result of these steps.

:::image type="content" source="media/data-analysis-vendor-ledger-entries-payments-on-hold-example.png" alt-text="Example of how to do data analysis on the Vendor Ledger Entries page to find On hold entries." lightbox="media/data-analysis-vendor-ledger-entries-payments-on-hold-example.png":::


## Data foundation for ad-hoc analysis on purchasing

When you post a purchase document, [!INCLUDE [prod_short](includes/prod_short.md)] updates the vendor's account, general ledger (G/L), item ledger entries, and resource ledger entries:

- For each purchase document, a purchase entry is created in the **G/L Entry** table. An entry is also created in the vendor's account in the **Supplier Ledger Entry** table, and a G/L entry is created in the relevant payables account. In addition, posting the purchase might result in a value-added tax (VAT) entry and a G/L entry for the discount amount.

- For each purchase line, as applicable, entries are created in the:
  - **Item Ledger Entry** table, if the purchase line is of the Item type.
  - **G/L Entry** table, if the purchase line is of the G/L Account type.
  - **Resource Ledger Entry** table, if the purchase line is of the Resource type.
- In addition, purchase documents are always recorded in the **Purch. Recpt. Header** and **Purch. Inv. Header** tables.

To learn more, go to [Posting purchases](purchasing-how-record-purchases.md#posting-purchases).

## Related information

[Posting purchases](purchasing-how-record-purchases.md#posting-purchases)  
[Analyze list and query data with analysis mode](analysis-mode.md)  
[Analytics, business intelligence, and reporting overview](reports-bi-reporting.md)  
[Purchasing overview](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
