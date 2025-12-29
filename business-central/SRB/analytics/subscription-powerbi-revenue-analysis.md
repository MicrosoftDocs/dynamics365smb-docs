---
title: Revenue Analysis (Power BI Report)
description: The Revenue Analysis report provides a detailed analysis of your monthly recurring revenue, breaking it down into its key contributing components.
author: vanessa-mi
ms.author: bholtorf
ms.reviewer: 
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form:
ms.date: 12/18/2025
ms.service: dynamics-365-business-central
---

# Revenue Analysis (Power BI Report)

The **Revenue Analysis** report provides a detailed analysis of monthly recurring revenue, breaking it down into its key contributing components. This report can help you understand what’s driving MRR in your subscription business, and why.

:::image type="content" source="../../media/powerbi/subscription-billing/sb-revenue-analysis.png" alt-text="Screenshot of the Revenue Analysis Power BI report":::

## Use the report

The Revenue Analysis report uses a decomposition tree that lets you break down monthly recurring revenue (MRR) step by step. For example, you might start by decomposing revenue by Initial Term to see whether short-term or long-term subscriptions are driving results. From there, you can drill deeper into contract types within your long-term contracts to understand which offerings contribute most and then expand further to identify the largest customers in this segment.

Alternatively, you can analyze revenue by item category and then drill down into individual items to see which products generate the most recurring revenue. This flexibility helps you uncover the exact drivers of subscription performance and where growth opportunities lie.

## Key performance indicators

- [Mon. Recurring Revenue](subscription-powerbi-subscription-kpis.md#mon-recurring-revenue)

[!INCLUDE[click-on-a-kpi-link](../../includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](../../includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data form the following tables in Business Central:

- Customer
- Item
- Salesperson/Purchaser
- Subscription
- Customer Subscription Contract
- Vendor Subscription Contract
- Subscription Contract Analysis Entries

## Related information

[Track your business KPIs with Power BI metrics](../../track-kpis-with-power-bi-metrics.md)  
[Setting up the Subscription Billing Power BI app](subscription-powerbi-app-setup.md)  
[Subscription Billing controlling](../controlling.md)  
[Subscription Billing overview](../welcome.md)  
