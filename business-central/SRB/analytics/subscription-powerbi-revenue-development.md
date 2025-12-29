---
title: Revenue Development (Power BI Report)
description: The Revenue Development report helps you track how and why subscription revenue evolves over time.
author: vanessa-mi
ms.author: bholtorf
ms.reviewer: 
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form:
ms.date: 12/18/2025
ms.service: dynamics-365-business-central
---

# Revenue Development (Power BI Report)

The **Revenue Development** report provides detailed insight into how monthly recurring revenue changes over time. It breaks down each month’s net change into **new subscriptions**, **upgrades**, **churn**, and **downgrades**, making it clear which factors are driving growth or decline. Changes from subscriptions that are billed based on **usage data** are also visualized, since these subscriptions can fluctuate regularly but are not considered upgrades or downgrades. This view helps you understand whether revenue development is the result of acquiring new customers, expanding existing contracts, offsetting cancellations and reductions, or usage-based variability.

:::image type="content" source="../../media/powerbi/subscription-billing/sb-revenue-development.png" alt-text="Screenshot of the Subscription Billing Revenue Development Power BI report":::

## Use the report

The Revenue Development report is particularly valuable for management and leaders in a subscription business. For example, a manager might spot unusually high churn in March 2024 and click on the data point in the chart. The tables below immediately show which subscription contracts were cancelled in that month. With this information, the manager can review the affected customers and decide on follow-up actions, such as reaching out to prevent further cancellations.

You can also use the tables to sort and filter for the contracts with the largest increases or decreases in recurring revenue. This makes it easier to identify where to focus attention — whether that means addressing customer churn, following up large downgrades, or reinforcing relationships with accounts that have expanded.

## Key performance indicators

- [Change in Mon. Recurring Revenue](subscription-powerbi-subscription-kpis#change-in-mon-recurring-revenue)
- [Mon. Recurring Revenue Churn](subscription-powerbi-subscription-kpis#mon-recurring-revenue-churn)
- [Mon. Recurring Revenue Downgrade](subscription-powerbi-subscription-kpis#mon-recurring-revenue-downgrade)
- [Mon. Recurring Revenue New](subscription-powerbi-subscription-kpis#mon-recurring-revenue-new)
- [Mon. Recurring Revenue Upgrade](subscription-powerbi-subscription-kpis#mon-recurring-revenue-upgrade)
- [Mon. Recurring Revenue Change UBB](subscription-powerbi-subscription-kpis#mon-recurring-revenue-change-ubb)

[!INCLUDE[click-on-a-kpi-link](../../includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](../../includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data form the following tables in Business Central:

- Subscription Contract Analysis Entries
- Customer Subscription Contracts

## Related information

[Track your business KPIs with Power BI metrics](../../track-kpis-with-power-bi-metrics.md)  
[Setting up the Subscription Billing Power BI app](subscription-powerbi-app-setup.md)  
[Subscription Billing controlling](../controlling.md)  
[Subscription Billing overview](../welcome.md)  
