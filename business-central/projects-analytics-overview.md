---
title: Project analytics
description: Business Central has features that can help you gather, analyze, and share data from your projects for business intelligence and decision-making in your organization.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: bi, power BI, analysis, KPI
ms.search.form: 37062, 37033, 37034, 37035, 37036, 37037, 37039, Report_1006, Report_1007, Report_1008, Report_1009, Report_1010, Report_1011, Report_1012, Report_1013, Report_1014, Report_1015
ms.date: 11/11/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Project analytics

Businesses capture lots of data during daily activities that supports business intelligence (BI) for project managers, such as:

- Cost performance for projects
- Completion rates for projects
- Financial data for projects

[!INCLUDE[prod_short](includes/prod_short.md)] provides features to help you gather, analyze, and share your organization's project data:

- Power BI reports for projects
- Ad-hoc analysis on lists
- Ad-hoc analysis of data in Excel (using Open in Excel)
- Built-in project analytics tools
- Built-in project reports

Each of these features has its advantages and disadvantages, depending on the type of data analysis and the role of the user. To learn more, go to [Analytics, business intelligence, and reporting overview](reports-bi-reporting.md).

This article introduces how you can use these analytical features to gain insights into your projects.

## Analytics needs in projects

When you think about the analytics needs in projects management, it might help to use a persona-based model that describes different analytics needs at a high-level.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg" alt-text="Illustration of different personas for analytics" lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg":::

People in different roles have different needs when it comes to data, and they use the data in different ways. For example, people in project management interact with data differently than people in finance.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg" alt-text="Illustration of how different personas have different analytics needs." lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg":::

| Role  | Data aggregation | Typical ways to consume data          | 
|------------------- |-------------------| ---------------------- |
|COO / CFO / CEO | Performance data  | KPIs, dashboards, financial reports               |
|Project Manager     | Trends, summaries | Built-in managerial reports, ad-hoc analysis      |
|Project participant | Detailed data     | Built-in operational reports, on-screen task data |

## Using Power BI to monitor project KPIs

A key performance indicator (KPI) is a measurable value that shows how effectively you’re meeting your goals. In project management, people often use the following KPIs to monitor project performance:

- % Complete
- % Invoiced
- Realization %
- Actual Profit
- Actual Profit Margin %
- Actual (Total Cost)
- Budget (Total Cost)

:::image type="content" source="media/projects/project-overview.png" alt-text="Screenshot of the Projects Overview Power BI Report" lightbox="media/projects/project-overview.png":::

These KPIs (and more) are available for projects in the Project Power BI app for [!INCLUDE [prod_short](includes/prod_short.md)].

To learn more, go to [Power BI Projects app](projects-powerbi-app.md).

### Reports in the Power BI Projects app

[!INCLUDE [power-bi-projects-app](includes/power-bi-projects-app.md)]

To learn more, go to [Power BI Projects app](projects-powerbi-app.md).

## Ad-hoc analysis of project data

Sometimes, you just need to check whether the numbers add up correctly, or quickly confirm a figure. The following features are great for ad-hoc analyses:

- Data analysis on ledger list pages
- Open in Excel

The Data Analysis feature lets you open almost any list page, such as **Project Ledger Entries**, enter analysis mode, and then group, filter, and pivot data as you see fit.

Similarly, you can use the **Open in Excel** action to open a list page, optionally filter the list to a subset of the data, and then use Excel to work with the data. For example, by using features such as Analyze Data, What-If Analysis, or Forecast Sheet.

> [!TIP]
> If you configure OneDrive for system features, the Excel workbook opens in your browser.

<!-- coming later
To learn more about how to do ad-hoc analysis on inventory data, go to [Ad hoc analysis of inventory data](ad-hoc-analysis-inventory.md). 
-->

## Built-in reports for projects

[!INCLUDE [prod_short](includes/prod_short.md)] includes several built-in reports to help project organizations report on their data.

[!INCLUDE [report-explorer-projects](includes/report-explorer-projects.md)]

To learn more about reports that are relevant for project management, go to [Built-in project reports](project-reports.md).

## On-screen project analytics

[!INCLUDE [prod_short](includes/prod_short.md)] has several pages that give you project overviews and tasks to do, such as:

- [Monitor project progress and performance](projects-how-monitor-progress-performance.md)

## Related information

[Power BI Projects app](projects-powerbi-app.md)  
[Monitor project progress and performance](projects-how-monitor-progress-performance.md)  
[Built-in Projects reports](project-reports.md)  
[Project management overview](projects-manage-projects.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
