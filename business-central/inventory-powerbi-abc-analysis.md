---
title: ABC Analysis (Power BI Report)
description: Rank inventory items into A, B, and C categories based on their sales amounts to identify high-value items and support purchasing and replenishment decisions.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting, inventory, ABC analysis
ms.search.form: Report_723_Primary
ms.date: 05/26/2026
ms.service: dynamics-365-business-central
---

# ABC Analysis (Power BI Report)

[!INCLUDE[introduced-in-2026rw1](../includes/introduced-in-2026rw1.md)]

The **ABC Analysis** Power BI report ranks your inventory items into A, B, and C categories based on their sales amounts (LCY). Use the report to decide which items should always be in stock and where you can afford occasional stock-outs. That way, you divert your supply chain resources to the items that matter the most.

The report calculates each item's share of total sales and classifies items by the percentage thresholds you define:

- **Category A** items have small volume and high value. These items drive the most revenue and should always be in stock.
- **Category B** items have medium volume and medium value.
- **Category C** items have high volume and small value. You might accept occasional stock-outs for these items.

Default category thresholds come from the **ABC Analysis Setup** page. The same thresholds are also used by the [Power BI Inventory app](../inventory-powerbi-app.md), so the classification is consistent across both reports. You can override the thresholds on the request page each time you run the report.

> [!TIP]
> The same report is available in Excel. To learn more, go to [Item - ABC Analysis (report)](reports/report-723.md).

## Use the report

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

Before you run the report, you must set default category thresholds on the **ABC Analysis Setup** page. The three category percentages must add up to 100%.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **ABC Analysis Setup**, and then choose the related link.
2. Enter the percentage for **Category A**, **Category B**, and **Category C**. The values must total 100%.
3. Close the page.

The report uses these values as defaults. You can override them on the request page each time you run the report.

## Key Performance Indicators

The ABC Analysis report includes the following KPIs:

- 
- 
- 
- 

Click on the link for a KPI to learn more about what it means, how it is calculated, and what data was used in the calculations.

> [!TIP]
> You can easily track the KPIs that the Power BI reports display against your business objectives. To learn more, go to [Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md).

## Data used in the report

The report uses data from the following tables in [!INCLUDE [prod_short](includes/prod_short.md)]:

## Try the report

Try the report here: 

> [!TIP]
> If you hold down the CTRL key while you select the report link, the report opens on a new browser tab. The new tab lets you stay on the current page while you explore the report on the other browser tab.

## Related information