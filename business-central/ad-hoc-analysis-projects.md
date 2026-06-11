---
title: Ad-hoc analysis of projects data
description: Learn how to use the data analysis mode to analyze projects data.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: bi, power BI, analysis, KPI
ms.search.form: 92,
ms.date: 06/10/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Ad-hoc analysis of project data

This article explains how to use the **Data Analysis** feature to analyze project data directly from list pages and queries. You don't have to run a report or switch to another application, such as Excel. The feature provides an interactive and versatile way to calculate, summarize, and examine data. Instead of running reports using options and filters, you can add multiple tabs that represent different tasks or views on the data. Some examples are "XXX," "YYY," or any other view you can imagine. To learn more about how to use the **Data Analysis** feature, go to [Analyze list and query data with analysis mode](analysis-mode.md).

Use the following list page and query to start doing ad-hoc analysis of project-management processes:

- [Project Ledger Entries (list page)](https://businesscentral.dynamics.com/?page=92&layout=analysis)
- [Project Ad-hoc Analysis (query)](https://businesscentral.dynamics.com/?query=486&layout=analysis)

## Project ad-hoc analysis scenarios

Use the **Data Analysis** feature for quick fact checking and ad-hoc analysis:

- If you don't want to run a report.
- If a report for your specific need doesn't exist.
- If you want to quickly iterate to get a good overview on a part of your business.

The following sections provide examples of project analysis scenarios in [!INCLUDE [prod_short](includes/prod_short.md)].

| Area | To... | Open this page in analysis mode | Using these fields |
| ---- | ----- | ------------------------------- |------------------- |
| [Fixed Assets (Current value)](#example-fixed-assets-current-value) | Track asset value, both across all assets and on a single asset. | [FA Ledger Entries](https://businesscentral.dynamics.com/?page=5604&layout=analysis) | **Depreciation Book**, **FA No.**, **FA Posting Date**, **FA Posting Type**, and **Amount** |

### Example: fixed assets current value

To track the value of one or more fixed assets, follow these steps:

1. Open the [Project Ledger Entries](https://businesscentral.dynamics.com/?page=92&layout=analysis) list, and choose :::image type="content" source="media/analysis-mode-icon.png" alt-text="Enter analysis mode."::: to turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field on the right).
1. Drag the **Depreciation Book** and **FA No.** fields to the **Row Groups** area.
1. Choose the **FA Posting Date** and **FA Posting Type** fields.
1. Drag the **Amount** field to the **Values** area.
1. Rename your analysis tab to **Asset overview - value**, or something that describes this analysis.

The following image shows the result of these steps.

:::image type="content" source="media/data-analysis-project-ledger-entries-project-statistics.png" alt-text="Example of how to do data analysis on the Project Ledger Entries page to see statistics across projects and project tasks." lightbox="media/data-analysis-project-ledger-entries-project-statistics.png":::

### Example: asset value changes over time

To track asset value changes over time, follow these steps:

1. Open the [FA Ledger Entries](https://businesscentral.dynamics.com/?page=5604&layout=analysis) list, and choose :::image type="content" source="media/analysis-mode-icon.png" alt-text="Enter analysis mode."::: to turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field on the right).
1. Turn on the **Pivot Mode** toggle (located above the **Search** field on the right).
1. Drag the **FA Posting Type** field to the **Row Groups** area.
1. Drag the **FA Posting Year** and **FA Posting Month** fields to the **Column Labels** area.
1. Drag the **Amount** field to the **Values** area.
1. Rename your analysis tab to **Asset value changes over time**, or something that describes this analysis.

The following image shows the result of these steps.

:::image type="content" source="media/data-analysis-fa-ledger-entries-asset-changes-over-time.png" alt-text="Example of how to do data analysis on the FA Ledger Entries page to see asset value changes over time." lightbox="media/data-analysis-fa-ledger-entries-asset-changes-over-time.png":::

### Example: fixed asset depreciations over time

To track depreciation for one or more fixed assets, follow these steps:

1. Open the [FA Ledger Entries](https://businesscentral.dynamics.com/?page=5604&layout=analysis) list, and choose :::image type="content" source="media/analysis-mode-icon.png" alt-text="Enter analysis mode."::: to turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field on the right).
1. Turn on the **Pivot Mode** toggle (located above the **Search** field on the right).
1. Drag the **Depreciation Book** and **FA No.** fields to the **Row Groups** area.
1. Drag the **FA Posting Year** and **FA Posting Month** fields to the **Column Labels** area.
1. Drag the **Amount** field to the **Values** area.
1. In the **FA Posting Type** filter field, choose **Depreciation**.
1. Rename your analysis tab to **Depreciations over time**, or something that describes this analysis.

The following image shows the result of these steps.

:::image type="content" source="media/data-analysis-fa-ledger-entries-depreciation-by-asset.png" alt-text="Example of how to do data analysis on the FA Ledger Entries page to see depreciation over time." lightbox="media/data-analysis-fa-ledger-entries-depreciation-by-asset.png":::

## Data foundation for ad-hoc analysis on projects

When you post project journals, [!INCLUDE [prod_short](includes/prod_short.md)] creates entries in the **Job Ledger Entry** table. Therefore, ad-hoc analysis on projects is typically done on the [Project Ledger Entries](https://businesscentral.dynamics.com/?page=92) page.

## Related information

[Analyze list and query data with analysis mode](analysis-mode.md)  
[Project management analytics overview](projects-analytics-overview.md)   
[Analytics, business intelligence, and reporting overview](reports-bi-reporting.md)  
[Project management overview](projects-manage-projects.md)

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]