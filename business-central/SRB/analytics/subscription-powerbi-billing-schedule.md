---
title: Billing Schedule (Power BI Report)
description: The Billing Schedule report provides insight into upcoming and past billing schedules for subscriptions.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form:
ms.date: 05/12/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Billing Schedule (Power BI Report)

The **Billing Schedule** report provides a forecast of future invoicing activity based on the specific billing rhythms defined in your subscriptions. By visualizing when you generate invoices rather than when revenue is recognized, this report offers a cash-flow-oriented view of your upcoming billing operations for both customers and vendors.

:::image type="content" source="../../media/subscription-billing-schedule.png" alt-text="Screenshot of the Billing Schedule report.":::

## Use the report

Accounting teams and financial planners use this report to gain visibility into the timing of future billing activities.

Accounting teams can use the report to manage operational workloads and plan for cash flow peaks. The line chart shows the forecasted billed amount for customer and vendor contracts over future months and years. This information tells you exactly when high volumes of invoices or large transaction amounts are expected. For example, during heavy renewal periods in January or at the start of a new quarter. Having this foresight helps you ensure that your team is prepared for high-volume billing cycles and that the organization can accurately anticipate cash inflows and outflows.

Billing clerks and controllers can use the report as a tool for data integrity and process monitoring. Because the report is based on the actual Next Billing Date recorded in Business Central, it can highlight missed billing tasks. If the report shows data in the past, it serves as a clear indicator that a contract hasn't been invoiced as scheduled.

The detailed table allows you to break down these amounts by billing rhythm, customer, and customer subscription contract. This breakdown helps you quickly identify whether a group of contracts, such as those billed annually, is responsible for a cash flow spike. It can also help pinpoint overdue billing schedules that require attention to ensure your billing stays up to date.

## Key performance indicators

- [Customer Billing Forecast](subscription-powerbi-subscription-kpis.md#customer-billing-forecast)
- [Vendor Billing Forecast](subscription-powerbi-subscription-kpis.md#vendor-billing-forecast)

[!INCLUDE[click-on-a-kpi-link](../../includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](../../includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data form the following tables in Business Central:

- Subscription Contract Analysis Entries
- Customer
- Customer Subscription Contract

## Related information

[Track your business KPIs with Power BI metrics](../../track-kpis-with-power-bi-metrics.md)  
[Setting up the Subscription Billing Power BI app](subscription-powerbi-app-setup.md)  
[Subscription Billing controlling](../controlling.md)  
[Subscription Billing overview](../welcome.md)  
