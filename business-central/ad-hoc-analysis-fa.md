---
title: Ad-Hoc Analysis of Fixed Assets Data
description: Analyze fixed asset values, value changes, and depreciation with analysis mode on ledger entries and the Fixed Assets Ad-hoc Analysis query.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: bi, power BI, analysis, KPI
ms.search.form: 5604, 20, Query_123_Primary
ms.date: 11/16/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
ai-usage: ai-assisted
---

# Ad-hoc analysis of fixed assets data

This article explains how to use the **Data Analysis** feature to analyze fixed assets data directly from list pages and queries. You don't have to run a report or switch to another application, such as Excel. The feature provides an interactive and versatile way to calculate, summarize, and examine data. Instead of running reports using options and filters, you can add multiple tabs that represent different tasks or views on the data. Some examples are "Total assets," "Depreciations over time," or any other view you can imagine. Learn more in [Analyze list and query data with analysis mode](analysis-mode.md).

Use the following list pages to start doing ad-hoc analysis of fixed assets processes:

- [FA Ledger Entries](https://businesscentral.dynamics.com/?page=5604&layout=analysis)
- [General Ledger Entries](https://businesscentral.dynamics.com/?page=20&layout=analysis)

<!-- TODO: add examples for 

insurance coverage ledger entries

-->

## Fixed assets ad-hoc analysis scenarios

Use the **Data Analysis** feature for quick fact checking and ad-hoc analysis:

- If you don't want to run a report.
- If a report for your specific need doesn't exist.
- If you want to quickly iterate to get a good overview on a part of your business.

The following sections provide examples of fixed assets scenarios in [!INCLUDE [prod_short](includes/prod_short.md)].

| Area | To... | Open this page in analysis mode | Using these fields |
| ---- | ----- | ------------------------------- |------------------- |
| [Fixed Assets (Current value)](#example-fixed-assets-current-value) | Track asset value, both across all assets and on a single asset. | [FA Ledger Entries](https://businesscentral.dynamics.com/?page=5604&layout=analysis) | **Depreciation Book Code**, **FA No.**, **FA Posting Date**, **FA Posting Type**, and **Amount** |
| [Asset value changes over time](#example-asset-value-changes-over-time) | Track asset value changes over time. | [FA Ledger Entries](https://businesscentral.dynamics.com/?page=5604&layout=analysis) | **FA Posting Type**, **FA Posting Date**, and **Amount** |
|[Fixed asset depreciations over time](#example-fixed-asset-depreciations-over-time) | Track depreciations over time, both across all assets and on a single asset. | [FA Ledger Entries](https://businesscentral.dynamics.com/?page=5604&layout=analysis) | **Depreciation Book Code**, **FA No.**, **FA Posting Date Year**, **FA Posting Date Month**, **Amount**, and **FA Posting Type** |

### Example: fixed assets current value

To track the value of one or more fixed assets, follow these steps:

1. Open the [FA Ledger Entries](https://businesscentral.dynamics.com/?page=5604&layout=analysis) list, and choose **Enter analysis mode** :::image type="icon" source="media/analysis-mode-icon.png"::: to turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field on the right).
1. Drag the **Depreciation Book Code** and **FA No.** fields to the **Row Groups** area.
1. Choose the **FA Posting Date** and **FA Posting Type** fields.
1. Drag the **Amount** field to the **Values** area.
1. Rename your analysis tab to **Asset overview - value**, or something that describes this analysis.

The following image shows the result of these steps.

:::image type="content" source="media/data-analysis-fa-ledger-entries-asset-overview-current-value.png" alt-text="Example of how to do data analysis on the FA Ledger Entries page to see the value of an asset." lightbox="media/data-analysis-fa-ledger-entries-asset-overview-current-value.png":::

> [!NOTE]
> This analysis sums all selected ledger entries, which can include postings that don't contribute to the asset's book value. Keep depreciation books separate when comparing values.

### Example: asset value changes over time

To track asset value changes over time, follow these steps:

1. Open the [FA Ledger Entries](https://businesscentral.dynamics.com/?page=5604&layout=analysis) list, and choose **Enter analysis mode** :::image type="icon" source="media/analysis-mode-icon.png"::: to turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field on the right).
1. Turn on the **Pivot Mode** toggle (located above the **Search** field on the right).
1. Drag the **FA Posting Type** field to the **Row Groups** area.
1. Drag the **FA Posting Date Year** and **FA Posting Date Month** fields to the **Column Labels** area.
1. Drag the **Amount** field to the **Values** area.
1. Rename your analysis tab to **Asset value changes over time**, or something that describes this analysis.

The following image shows the result of these steps.

:::image type="content" source="media/data-analysis-fa-ledger-entries-asset-changes-over-time.png" alt-text="Example of how to do data analysis on the FA Ledger Entries page to see asset value changes over time." lightbox="media/data-analysis-fa-ledger-entries-asset-changes-over-time.png":::

Filter **Depreciation Book Code** to one depreciation book so that the analysis doesn't combine values from different books.

### Example: fixed asset depreciations over time

To track depreciation for one or more fixed assets, follow these steps:

1. Open the [FA Ledger Entries](https://businesscentral.dynamics.com/?page=5604&layout=analysis) list, and choose **Enter analysis mode** :::image type="icon" source="media/analysis-mode-icon.png"::: to turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field on the right).
1. Turn on the **Pivot Mode** toggle (located above the **Search** field on the right).
1. Drag the **Depreciation Book Code** and **FA No.** fields to the **Row Groups** area.
1. Drag the **FA Posting Date Year** and **FA Posting Date Month** fields to the **Column Labels** area.
1. Drag the **Amount** field to the **Values** area.
1. In the **FA Posting Type** filter field, choose **Depreciation**.
1. Rename your analysis tab to **Depreciations over time**, or something that describes this analysis.

The following image shows the result of these steps.

:::image type="content" source="media/data-analysis-fa-ledger-entries-depreciation-by-asset.png" alt-text="Example of how to do data analysis on the FA Ledger Entries page to see depreciation over time." lightbox="media/data-analysis-fa-ledger-entries-depreciation-by-asset.png":::

## Use the Fixed Assets Ad-hoc Analysis query

You can use the [Fixed Assets Ad-hoc Analysis](https://businesscentral.dynamics.com/?query=123) query to analyze fixed asset ledger entries. The query adds additional information to the ledger entries, such as the fixed asset class, subclass, location, and depreciation book.

## Data foundation for ad-hoc analysis on fixed assets

When you post fixed asset journals, [!INCLUDE [prod_short](includes/prod_short.md)] creates entries in the **FA Ledger Entry** table, except for maintenance postings, which use the **Maintenance Ledger Entry** table. Therefore, ad-hoc analysis on fixed assets is typically done on the [FA Ledger Entries](https://businesscentral.dynamics.com/?page=5604) page.

You might also want to use the [Fixed Assets Ad-hoc Analysis](https://businesscentral.dynamics.com/?query=123) query.

## Contributors

Microsoft maintains this article. Parts of the examples were originally written by the following contributor.

- [Aldona Stec](https://www.linkedin.com/in/aldona-stec-25283bb1) | [!INCLUDE[prod_short](includes/prod_short.md)] Consultant

## Related information

[Analyze list and query data with analysis mode](analysis-mode.md)  
[Fixed assets analytics overview](fa-analytics-overview.md)  
[Analytics, business intelligence, and reporting overview](reports-bi-reporting.md)  
[Fixed assets overview](fa-manage.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
