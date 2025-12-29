---
title: Subscription Billing Overview (Power BI Report)
description: The Subscription Billing Overview report provides a high-level summary of your organization's subscription activities.
author: vanessa-mi
ms.author: bholtorf
ms.reviewer: 
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form:
ms.date: 12/18/2025
ms.service: dynamics-365-business-central
---

# Subscription Billing Overview (Power BI Report)

The **Subscription Billing Overview** report provides a high-level summary of your organization's subscription business. The report shows key performance metrics (KPIs), such as:

- Monthly recurring revenue
- Total contract revenue
- Number of active customers
- Churn rate

This report also highlights the top five customers by monthly recurring revenue and the top 5 vendors by monthly recurring cost.

:::image type="content" source="../../media/powerbi/subscription-billing/sb-overview.png" alt-text="Screenshot of the Subscription Billing Overview Power BI report":::

## Use the report

The report is intended for the following roles:

- Executives
- Directors
- Other high-level decision makers

Executives and revenue owners regularly monitor subscription performance to ensure predictable growth and long-term customer value. To get a quick, high-level overview of the subscription business, you use the Power BI Subscription Billing Overview report to review:

- [Monthly recurring revenue (MRR)](subscription-powerbi-subscription-kpis#mon-recurring-revenue), to understand the current recurring revenue base and its development over time.
- [Change of monthly recurring revenue](subscription-powerbi-subscription-kpis#change-in-mon-recurring-revenue), to identify revenue losses and assess subscription retention.
- [Total contract value (TCV)](subscription-powerbi-subscription-kpis#total-contract-value), to evaluate the long-term financial impact of customer relationships.

The report aggregates these KPIs at a high level, enabling decision makers to quickly assess the health, stability, and growth of the subscription business.

## Key performance indicators

The report includes the following KPIs and measures:

- [Monthly recurring revenue (MRR)](subscription-powerbi-subscription-kpis#mon-recurring-revenue)
- [Monthly recurring cost (MRC)](subscription-powerbi-subscription-kpis#mon-recurring-cost)
- [Net monthly recurring profit (NMRP)](subscription-powerbi-subscription-kpis#mon-net-profit-amount)
- [Active customers](subscription-powerbi-subscription-kpis#active-customers)
- [Total contract value (TCV)](subscription-powerbi-subscription-kpis#total-contract-value)
- [Change of monthly recurring revenue](subscription-powerbi-subscription-kpis#change-in-mon-recurring-revenue)
- [Avg. monthly churn rate %](subscription-powerbi-subscription-kpis#avg-mon-churn-rate)

[!INCLUDE[click-on-a-kpi-link](../../includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](../../includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data form the following tables in Business Central:

- Subscription Contract Analysis Entries
- Customer
- Vendor

## Related information

[Track your business KPIs with Power BI metrics](../../track-kpis-with-power-bi-metrics.md)  
[Setting up the Subscription Billing Power BI app](subscription-powerbi-app-setup.md)  
[Subscription Billing controlling](../controlling.md)  
[Subscription Billing overview](../welcome.md)  
