---
title: Manufacturing Analytics and Reporting
description: Business Central has features to help you gather, analyze, and share manufacturing data for business intelligence and decision-making in your organization.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: bi, power BI, analysis, KPI
ms.search.form: 
ms.date: 11/16/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
ai-usage: ai-assisted
---

# Manufacturing analytics

Businesses capture lots of data during daily activities that supports business intelligence (BI) for manufacturing, such as:

- Utilization
- Capacity
- Work center load
- Production time
- Production scrap

[!INCLUDE[prod_short](includes/prod_short.md)] provides features to help you gather, analyze, and share your organization's manufacturing data:

- Power BI reports for manufacturing
- Ad-hoc analysis on lists
- Ad-hoc analysis of data in Excel (using Open in Excel)
- Built-in manufacturing analytics tools
- Built-in manufacturing reports

Each feature has its advantages and disadvantages, depending on the type of analysis you want to do and your role. Learn more in [Analytics, business intelligence, and reporting overview](reports-bi-reporting.md).

This article introduces how you can use these analytical features to gain insights into your manufacturing processes.

## Analytics needs in manufacturing

When you think about analytics in manufacturing, it might help to use a persona-based model that describes different needs at a high level.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg" alt-text="Illustration of different personas for analytics" lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg":::

People in different roles have different needs when it comes to data, and they use data in different ways. For example, people in manufacturing interact with data differently than people in finance.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg" alt-text="Illustration of how different personas have different analytics needs." lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg":::

| Role  | Data aggregation | Typical ways to consume data          |
|------------------- |-------------------| ---------------------- |
| COO / CFO / CEO | Performance data  | KPIs, dashboards, financial reports               |
| Plant Manager     | Trends, summaries | Built-in managerial reports, ad-hoc analysis      |
| Factory worker | Detailed data     | Built-in operational reports, on-screen task data |

## Use Power BI to monitor key performance indicators in manufacturing

A key performance indicator (KPI) is a measurable value that shows how effectively you’re meeting your goals. Businesses often use the following KPIs to monitor production performance:

- Total Actual Cost with sub-cost calculations such as Actual Material Cost, Actual Capacity Cost, and more
- Expected Cost, Expected Cost Variance, and Expected Cost Dev %
- Total Standard Cost, Standard Cost Variance, and Standard Cost Dev %
- Planned vs. Finished Quantity

:::image type="content" source="media/manufacturing/finished-production-order-breakdown-v26.png" alt-text="Screenshot of the Finished Production Order Breakdown Power BI Report" lightbox="media/manufacturing/finished-production-order-breakdown-v26.png":::

These KPIs, and more, are available for manufacturing in the [!INCLUDE [powerbi-manufacturing-app-name](includes/power-bi-manufacturing-app-name.md)] for [!INCLUDE [prod_short](includes/prod_short.md)]. Learn more in [Manufacturing KPIs](manufacturing-powerbi-kpis.md).

### Reports in the [!INCLUDE [powerbi-manufacturing-app-name](includes/power-bi-manufacturing-app-name.md)]

[!INCLUDE [power-bi-manufacturing-app](includes/power-bi-manufacturing-app.md)]

Learn more in [Power BI Manufacturing app](manufacturing-powerbi-app.md).

## Ad-hoc analysis of manufacturing data

Sometimes you just need to check whether the numbers add up correctly, or quickly confirm a figure. The following features are great for ad-hoc analyses:

- Data analysis on ledger list pages
- Open in Excel

The Data Analysis feature lets you open almost any list page, such as **Item Ledger Entries** or **Capacity Ledger Entries**, enter analysis mode, and then group, filter, and pivot data as you see fit.

Similarly, you can use the **Open in Excel** action to open a list page, optionally filter the list to a subset of the data, and then use Excel to work with the data. For example, use features such as Analyze Data, What-If Analysis, or Forecast Sheet. For What-If Analysis or Forecast Sheet, use Excel for Windows.

> [!TIP]
> If you configure OneDrive for system features, the Excel workbook opens in your browser.

<!-- coming later
To learn more about how to do ad-hoc analysis on production data, go to [Ad hoc analysis of inventory data](ad-hoc-analysis-manufacturing.md). 
-->

## Built-in reports for manufacturing

[!INCLUDE [prod_short](includes/prod_short.md)] includes several built-in reports to help manufacturing organizations report on their data.

[!INCLUDE [report-explorer-manufacturing](includes/report-explorer-manufacturing.md)]

Learn more in [Built-in production report overview](production-reports.md).

## On-screen manufacturing analytics

[!INCLUDE [prod_short](includes/prod_short.md)] has several pages that give you manufacturing overviews and tasks to do, such as:

- [View the load in work and machine centers](production-how-to-view-the-load-on-work-centers.md)  

## Print barcodes for finished goods on production orders

To remove a step or two from the process of tracking finished goods, [!INCLUDE [prod_short](includes/prod_short.md)] offers a **Print Label** action on the **Released Production Order** and **Finished Production Order** pages. The action prints a report that includes the **Item No.**, **Description**, **Unit of Measure**, and 1D and 2D barcode information from the orders. On the request page, you can also specify whether to print the **Lot No.**, **Serial No.** or **Package No.** values as barcodes.

The report prints labels only for posted output entries that have a value for the selected item tracking type.

> [!NOTE]
> Some printers and barcode/QR code formats require a specific implementation. You might need to upload a different Word template.
>
> Check with your equipment supplier to learn how to print Word documents on your device.

If you decide to clone the report to create your own custom version, select **Prod. Output Item Label** in the **Usage** field on the **Report Selection - Production** page and enter your report's ID in the **Report ID** field.

## Related information

[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[View the load in work and machine centers](production-how-to-view-the-load-on-work-centers.md)  
[Built-in production report overview](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
