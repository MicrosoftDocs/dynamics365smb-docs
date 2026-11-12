---
title: Project Realization Power BI Report
description: Compare billable project prices with usage prices in Business Central, and analyze realization and price variances with the Project Realization report.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ai-usage: ai-assisted
ms.search.keywords: reporting
ms.search.form: 37036_Primary
ms.date: 11/12/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Project realization (Power BI report)

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The **Project Realization** report compares billable prices from project planning lines with usage prices from project ledger entries.

The report calculates realization as total billable price divided by total usage price. Realization variance is total billable price minus total usage price. These measures don't show how much of a project has been invoiced.

:::image type="content" source="media/projects/project-realization.png" alt-text="Screenshot of the Project Realization Power BI Report" lightbox="media/projects/project-realization.png":::

## Use the report

Leadership, project managers, and CFOs use the report to compare the billable value of projects with the value of recorded usage.

CFOs can check which projects have low realization and investigate differences between billable planning lines and recorded usage.

Project managers use this report to identify projects where billable prices don't cover usage prices.

## Key performance indicators (KPIs)

The *Project Realization* report includes the following KPIs:

- [Realization (%)](projects-powerbi-kpis.md#realization-)
- [Realization Variance](projects-powerbi-kpis.md#realization-variance)
- [Total Usage Price](projects-powerbi-kpis.md#total-usage-price)
- [Total Billable Price](projects-powerbi-kpis.md#total-billable-price)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables in [!INCLUDE[prod_short](includes/prod_short.md)]:

- Job
- Job Ledger Entries
- Job Planning Line

## Try the report

Try the report here: [Project Realization](https://businesscentral.dynamics.com?page=37036)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track your business KPIs with Power BI goals](track-kpis-with-power-bi-metrics.md)  
[Power BI Projects app](projects-powerbi-app.md)  
[Built-in Projects reports](project-reports.md)  
[Project management analytics overview](projects-analytics-overview.md)  
[Project management overview](projects-manage-projects.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
