---
title: Total Contract Value Analysis (Power BI Report)
description: The Total Contract Value Analysis report provides a detailed analysis of your total contract value, breaking it down into its key contributing components.
author: vanessa-mi
ms.author: bholtorf
ms.reviewer: 
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form:
ms.date: 12/18/2025
ms.service: dynamics-365-business-central
---

# Total Contract Value Analysis (Power BI Report)

The **Total Contract Value Analysis** report provides a detailed analysis of total contract value (TCV), breaking it down into its key contributing components. This report can help you understand what’s driving TCV in your subscription business, and why.

:::image type="content" source="../../media/powerbi/subscription-billing/sb-total-contract-value-analysis.png" alt-text="Screenshot of the Subscription Billing Total Contract Value Analysis Power BI report":::

## Use the report

Leadership and management teams use the report to identify trends, break down total contract value (TCV) into its key contributing components, and make informed adjustments to strategies.

Subscription managers can use the decomposition tree in Power BI to perform a deep-dive analysis into the drivers of your TCV. This interactive visual allows you to break down the TCV by any available dimension—such as customer, item, contract terms, or billing rhythms in any order you choose.

For example, you might start by breaking down TCV by Contract Type to see which contract models are most valuable. You could then expand a specific type by Billing Rhythm to understand how your revenue is distributed between monthly and annual billing, and finally drill down to the customer level to identify the specific accounts contributing to those figures. This level of granularity helps you identify high-value segments and understand the underlying structure of your contractual commitments.

## Key performance indicators

- [Total Contract Value](subscription-powerbi-subscription-kpis.md#total-contract-value)

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
