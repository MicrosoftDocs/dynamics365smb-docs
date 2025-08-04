---
title: Ad-hoc analysis of sustainability data
description: Learn how to use the data analysis mode to analyze sustainability data.
author: brentholtorf
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: bi, power BI, analysis, KPI, sustainability, ESG
ms.search.form: 6220,
ms.date: 06/12/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Ad-hoc analysis of sustainability data

This article explains how to use the **Data Analysis** feature to analyze sustainability data directly from list pages and queries. You don't have to run a report or switch to another application, such as Excel. The feature provides an interactive and versatile way to calculate, summarize, and examine data. Instead of running reports using options and filters, you can add multiple tabs that represent different tasks or views on the data. Some examples are "Emission overview" or "Emission By Scope," or any other view you can imagine. To learn more about how to use the **Data Analysis** feature, go to [Analyze list and query data with analysis mode](analysis-mode.md).

Use the following list pages for ad-hoc analysis of sustainability data:

- [Sustainability Ledger Entries](https://businesscentral.dynamics.com/?page=6220&layout=analysis)

## Sustainability ad-hoc analysis scenarios

Use the **Data Analysis** feature for quick fact checking and ad-hoc analysis:

- If you don't want to run a report.
- If a report for your specific need doesn't exist.
- If you want to quickly iterate to get a good overview on a part of your business.

The following sections provide examples of sustainability scenarios in [!INCLUDE [prod_short](includes/prod_short.md)].

| Area | To... | Open this page in analysis mode | Using these fields |
| ---- | ----- | ------------------------------- |------------------- |
| [Emission overview (sum by category)](#example-emission-overview-sum-by-category) | Analyze your emissions by category. | [Sustainability Ledger Entries](https://businesscentral.dynamics.com/?page=6220&layout=analysis) | **Account Category**, **Account Name**, **Emission NH4**, **Emission CO2**, and **Emission N2O**.|
| [Average emissions by category](#example-average-emissions-by-category) | Analyze your average emissions by category. | [Sustainability Ledger Entries](https://businesscentral.dynamics.com/?page=6220&layout=analysis) | **Account Category**, **Account Name**, **Emission NH4**, **Emission CO2**, and **Emission N2O**.|
| [Emissions by scope](#example-emissions-by-scope) | Analyze your emissions by scope. | [Sustainability Ledger Entries](https://businesscentral.dynamics.com/?page=6220&layout=analysis) | **Emission Scope**, **Account Category**, **Emission NH4**, **Emission CO2**, and **Emission N2O**.|

## Example: Emission overview (sum by category)

To analyze your emissions by category, follow these steps:

1. Open the [Sustainability Ledger Entries](https://businesscentral.dynamics.com/?page=6220&layout=analysis) page and turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field).
1. Turn on **Pivot** mode (located directly above the **Search** field).
1. Drag the **Account Category** and **Account Name** fields to the **Row Groups** area. Drag the fields in that order.
1. Drag the fields **Emission NH4**, **Emission CO2**, and **Emission N2O** to the **Values** area.
1. Rename your analysis tab to **Emission overview (sum)** or something that describes this analysis for you.

The following image shows the result of these steps.

:::image type="content" source="media/data-analysis-sustainability-entries.png" alt-text="Example 1 of how to do data analysis on the Sustainability Ledger Entries page." lightbox="media/data-analysis-sustainability-entries.png":::

## Example: Average emissions by category

To analyze your average emissions by category, follow these steps:

1. Open the [Sustainability Ledger Entries](https://businesscentral.dynamics.com/?page=6220&layout=analysis) page and turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field).
1. Turn on **Pivot** mode (located directly above the **Search** field).
1. Drag the **Account Category** and **Account Name** fields to the **Row Groups** area. Drag the fields in that order.
1. Drag the fields **Emission NH4**, **Emission CO2**, and **Emission N2O** to the **Values** area.
1. For each field in the **Values** area, select them and change the aggregation function to `Average`.
1. Rename your analysis tab to **Emission overview (avg)** or something that describes this analysis for you.

The following image shows the result of these steps.

:::image type="content" source="media/data-analysis-sustainability-entries-avg.png" alt-text="Example 2 of how to do data analysis on the Sustainability Ledger Entries page." lightbox="media/data-analysis-sustainability-entries-avg.png":::

## Example: Emissions by scope

To analyze your emissions by scope, follow these steps:

1. Open the [Sustainability Ledger Entries](https://businesscentral.dynamics.com/?page=6220&layout=analysis) page and turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field).
1. Turn on **Pivot** mode (located directly above the **Search** field).
1. Drag the **Emission Scope** and **Account Category** fields to the **Row Groups** area. Drag the fields in that order.
1. Drag the fields **Emission NH4**, **Emission CO2**, and **Emission N2O** to the **Values** area.
1. Rename your analysis tab to **Emission overview by scope** or something that describes this analysis for you.

The following image shows the result of these steps.

:::image type="content" source="media/data-analysis-sustainability-entries-scope.png" alt-text="Example 3 of how to do data analysis on the Sustainability Ledger Entries page." lightbox="media/data-analysis-sustainability-entries-scope.png":::

## Data foundation for ad-hoc analysis on sustainability

The information that you enter in a sustainability journal is temporary and you can change it while it's in the journal. When you post a sustainability journal, the information is transferred to sustainability ledger entries on individual sustainability accounts, where you can't change it. However, you can post reversing or correcting entries. The [Sustainability Ledger Entries](https://businesscentral.dynamics.com/?page=6220) list page is the main data source for ad-hoc analysis of sustainability data.

To learn more about posting sustainability entries, go to [Record sustainability entries](finance-sustainability-journal.md).

## Related information

[Record sustainability entries](finance-sustainability-journal.md)  
[Built-in sustainability reports](sustainability-reports.md)   
[Analytics, business intelligence, and reporting overview](reports-bi-reporting.md)  
[Sustainability management overview](finance-manage-sustainability.md)   
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
