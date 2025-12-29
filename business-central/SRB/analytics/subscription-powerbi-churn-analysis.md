---
title: Churn Analysis (Power BI Report)
description: The Churn Analysis report provides a detailed analysis of your subscription churn, breaking it down into its key contributing components.
author: vanessa-mi
ms.author: bholtorf
ms.reviewer: 
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form:
ms.date: 12/18/2025
ms.service: dynamics-365-business-central
---

# Churn Analysis (Power BI Report)

The **Churn Analysis** report provides a detailed analysis of monthly recurring revenue churn and downgrades, breaking it down into its key contributing components. This report can help you understand what’s driving MRR churn in your subscription business, and why.

:::image type="content" source="../../media/powerbi/subscription-billing/sb-churn-analysis.png" alt-text="Screenshot of the Subscription Billing Churn Analysis Power BI report":::

## Use the report

As a manager in a subscription business, you can use the Churn Analysis report to understand what drives lost recurring revenue. For example, after noticing unusually high churn in Q2 2024 in the Revenue Development report, you filter the Churn Analysis report to the same period. By drilling down into churn by Item Category Code and then by Item Name, you identify which products were most affected.

Using the Date, Fiscal Year or Fiscal Month Year filters is key here, as it allows you to isolate the time frame you want to analyze instead of looking at the full history. This way, you can connect high-level anomalies to their underlying causes and decide on targeted customer retention or product strategies.

## Key performance indicators

- [Mon. Recurring Revenue](subscription-powerbi-subscription-kpis.md#mon-recurring-revenue)
- [Change in Mon. Recurring Revenue](subscription-powerbi-subscription-kpis.md#change-in-mon-recurring-revenue)
- [Mon. Recurring Revenue Downgrade](subscription-powerbi-subscription-kpis.md#mon-recurring-revenue-downgrade)
- [Mon. Recurring Revenue Churn](subscription-powerbi-subscription-kpis.md#mon-recurring-revenue-churn)
- [Avg. Mon. Churn Rate](subscription-powerbi-subscription-kpis.md#avg-mon-churn-rate)

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
