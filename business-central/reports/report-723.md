---
title: Item - ABC Analysis (report)
description: Rank inventory items into A, B, and C categories based on their sales amounts to identify high-value items and support purchasing and replenishment decisions.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting, inventory, ABC analysis
ms.search.form: Report_723_Primary
ms.date: 04/30/2026
ms.service: dynamics-365-business-central
---

# Item - ABC Analysis (report)

[!INCLUDE[introduced-in-2026rw1](../includes/introduced-in-2026rw1.md)]

The **Item - ABC Analysis** report ranks your inventory items into A, B, and C categories based on their sales amounts (LCY). Use the report to decide which items should always be in stock and where you can afford occasional stock-outs. That way, you divert your supply chain resources to the items that matter the most.

The report calculates each item's share of total sales and classifies items by the percentage thresholds you define:

- **Category A** items have small volume and high value. These items drive the most revenue and should always be in stock.
- **Category B** items have medium volume and medium value.
- **Category C** items have high volume and small value. You might accept occasional stock-outs for these items.

Default category thresholds come from the **ABC Analysis Setup** page. The same thresholds are also used by the [Power BI Inventory app](../inventory-powerbi-app.md), so the classification is consistent across both reports. You can override the thresholds on the request page each time you run the report.

## Available layouts

[!INCLUDE[available-layouts-excel-only](../includes/available-layouts-excel-only.md)]

The Excel layout includes three worksheets:

- **Print**: A printable version of the report with item details and ABC classifications.
- **Structure**: A summary of cumulative values for each ABC class.
- **Analysis**: A worksheet with slicers for ABC class and inventory posting group, so you can slice and dice the data further.

## Use cases

[!INCLUDE [report-723-scenario](../includes/report-723-scenario-include.md)]

Inventory managers use the report to:

- Identify the items that contribute the most to revenue and prioritize their availability.
- Review which items fall into each category and adjust purchasing strategies accordingly.
- Spot items with zero sales that might be candidates for phase-out or promotion.

Purchasing agents use the report to:

- Focus negotiations and supplier relationships on high-value Category A items.
- Adjust reorder quantities and safety stock levels based on item classification.
- Identify Category C items where you can reduce inventory investment.

Controllers use the report to:

- Analyze the distribution of inventory value across categories.
- Support decisions about inventory write-downs or obsolescence provisions for low-value items.
- Validate that inventory investment aligns with sales performance.

## Set up ABC Analysis defaults

Before you run the report, you can set default category thresholds on the **ABC Analysis Setup** page. The three category percentages must add up to 100%.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **ABC Analysis Setup**, and then choose the related link.
2. Enter the percentage for **Category A**, **Category B**, and **Category C**. The values must total 100%.
3. Close the page.

The report uses these values as defaults. You can override them on the request page each time you run the report.

## Try the report

Try the report here: [Item - ABC Analysis](https://businesscentral.dynamics.com?report=723)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Report options

The following table describes the key options on the request page.

|Option  |Description  |
|---------|---------|
|**Ratio Cat. A/B/C** | Set the percentage thresholds for each category. The three values must total 100%. For example, A = 50, B = 30, C = 20 means that items contributing to the top 50% of total sales value are Category A. |
|**Show Category A/B/C** | Choose which categories to include in the report output. |
|**Print Lines with 0** | Include items with zero sales amounts. These lines are often excluded from the analysis. |

You can also apply filters on the **Item** data item, such as **No.**, **Inventory Posting Group**, **Date Filter**, and **Location Filter**.

## Alternative reports

There are several other ways to analyze your inventory. To learn more, go to:

- [Inventory Top 10 List](report-711.md)
- [Power BI inventory app](../inventory-powerbi-app.md)
- [Ad hoc analysis of inventory data](../ad-hoc-analysis-inventory.md)

## Related information

[Inventory and warehouse report overview](../inventory-WMS-reports.md)   
[Ad hoc analysis of inventory data](../ad-hoc-analysis-inventory.md)   
[Inventory analytics overview](../inventory-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
