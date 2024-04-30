---
title: Track your business KPIs with Power BI metrics
description: Get an overview of using Power BI to get insight, business intelligence, and KPIs from your Business Central data.
author: kennienp
ms.topic: overview
ms.search.keywords: account schedule, analysis, reporting, financial report, business intelligence, KPI
ms.search.form: 6316, 6317
ms.reviewer: jswymer
ms.date: 04/24/2024
ms.author: kepontop
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Track your business KPIs with Power BI metrics

If you use Power BI on [!INCLUDE[prod_short](includes/prod_short.md)] data, it's easy to track KPIs or metrics that are important to you. 

With metrics in Power BI, you can curate your own metrics and track them against key business objectives, in a single pane. This feature enhances data culture by promoting accountability, alignment, and visibility for teams and initiatives within organizations. 

Follow this four-step process to setup Power BI metrics:

1. Create a scorecard in the Power BI service. Learn more at [Create scorecards in Power BI](/power-bi/create-reports/service-goals-create).  
2. Add the _metrics_ you want to track by connecting to your Power BI report on telemetry. Learn more at [Create connected metrics](/power-bi/create-reports/service-goals-create-connected).  
3. To add alerting, define status rules for your metrics. Learn more at [Create automated status rules for metrics](/power-bi/create-reports/service-metrics-status-rules).  

    This step will automate status updates based on rules that govern that metric. Rules trigger changes based on value, percentage of target met, date conditions, or a combination of the three, making the rules as versatile as possible. For connected metrics, these status rules are refreshed every time the data in your scorecard is refreshed.
4. Finally, follow metrics to get alerts in Teams or by email. Learn more at [Follow your metrics](/power-bi/create-reports/service-metrics-follow).  

Learn more about Power BI metrics at [Get started with metrics in Power BI](/power-bi/create-reports/service-goals-introduction).

> [!NOTE]
> Starting with Business Central 2023 release wave 2, it's possible to embed scorecards from Power BI metrics in [!INCLUDE[prod_short](includes/prod_short.md)].


## See also

[Using key performance indicators (KPIs) to meet your business goals](analytics-about-kpis.md)  
[Introduction to Business Central and Power BI](admin-powerbi.md)  
[Work with Power BI reports](across-working-with-powerbi.md)  
[Analytics overview](reports-bi-reporting.md)   

[!INCLUDE[footer-include](includes/footer-banner.md)]
