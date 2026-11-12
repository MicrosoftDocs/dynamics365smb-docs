---
title: Water and Waste Analysis Power BI Report
description: Review water usage and waste by facility, location, and type in Business Central with the Water and Waste Analysis Power BI report for sustainability.
author: altotovi
ms.author: altotovi
ms.reviewer: bholtorf
ms.topic: concept-article
ai-usage: ai-assisted
ms.search.keywords: reporting
ms.date: 11/12/2026
ms.service: dynamics-365-business-central
---

# Water and waste analysis (Power BI report)

[!INCLUDE[applies-to-2025w2](includes/2025_releasewave1.md)]

The Water and Waste Analysis report provides a detailed analysis of the organization's water usage and waste generation. The report organizes the information by facility and location. You can compare water usage with the configured water capacity of responsibility centers, and review different types of water and waste. The year-over-year and day-over-day calculations show percentage changes in usage.

:::image type="content" source="media\sustainability\water-and-waste-analysis.png" alt-text="Screenshot of the Water and Waste Analysis Power BI report" lightbox="media\sustainability\water-and-waste-analysis.png":::

## Use the report

Sustainability Managers use the report to monitor water usage and waste generation at an organizational level. You can explore water capacity, water usage, waste generation, and the different types of water and waste for each facility or location. Available water is the configured water capacity for the selected period minus water usage. The report doesn't calculate waste capacity.

Facility Managers can quickly and effectively monitor how your facility is performing against your baseline and targets, and compare the different types of water and waste.

## Key performance indicators (KPIs)

The Water and Waste Analysis report includes the following KPIs and measures:

- [Water Realized (%)](sustainability-powerbi-kpis.md#water-realized-)
- [Water Intensity vs Baseline (%)](sustainability-powerbi-kpis.md#water-intensity-vs-baseline-)
- [Waste Realized (%)](sustainability-powerbi-kpis.md#waste-realized-)
- [Waste Intensity vs Baseline (%)](sustainability-powerbi-kpis.md#waste-intensity-vs-baseline-)
- [Discharged Into Water vs Baseline (%)](sustainability-powerbi-kpis.md#discharged-into-water-vs-baseline-)
- [Water Intensity](sustainability-powerbi-kpis.md#water-intensity)
- [Water Available](sustainability-powerbi-kpis.md#water-available)
- [Facility Capacity](sustainability-powerbi-kpis.md#facility-capacity)

Choose the link for a KPI to learn more about what it means, its calculation, and what data is used in the calculations.

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The Water and Waste Analysis report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Sustainability Ledger Entry
- Sustainability Account Category
- Sustainability Account
- Sustainability Goals
- Responsibility Center
- Country/Region

## Try the report

Try the report here: [Water and Waste Analysis](https://businesscentral.dynamics.com?page=6319)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sustainability Overview (Power BI Report)](sustainability-powerbi-sustainability-overview.md)  
[Sustainability management overview](finance-manage-sustainability.md)  
[Sustainability reports and analytics in Business Central](sustainability-reports.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
