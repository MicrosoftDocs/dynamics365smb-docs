---
title: Return Order Overview (Power BI report)
description: The Return Order Overview report tracks and analyzes return orders, providing insights into the financial effect on the organization.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: 37105_Primary
ms.date: 10/07/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Return Order Overview (Power BI Report)

[!INCLUDE[applies-to-2025w1](includes/applies-to-2025w1.md)]

The **Return Order Overview** report tracks and analyzes return orders, providing insights into return amounts, quantities, reasons for return, and the financial effect on the organization. The report gives a high-level summary of return trends for item categories and customers, and analyzes the return amount over time.

:::image type="content" source="media/powerbi/sales/sales-returns-overview.png" alt-text="Screenshot of the Return Order Overview report" lightbox="media/powerbi/sales/sales-returns-overview.png":::

## Use the report

Leadership and management teams use the report to identify key factors that cause return orders and credit memos.

For CEOs, you want to evaluate return trends to inform key business decisions. For example, you identify 60% of return reasons are attributed to damage during delivery. In response, you engage a new logistics partner to optimize shipping procedures and minimize product returns.

As a product manager, you want to identify the item attributes which contribute the most to return orders, to inform future product development. By analyzing the return amount, you identify a specific item category with lower profitability. These insights help identify a persistent component fault and implement production process improvements to reduce item defects.

As a salesperson, this report helps you monitor individual customer returns, to assist with managing client relationships. Using this report, you notice that a particular customer has the highest [Return Rate](sales-powerbi-sales-kpis.md#return-rate) and their return amount increased over the past month. Using this information, you decide to offer a special discount to rebuild client trust in the business.

## Key performance indicators

The report includes the following key performance indicators (KPIs) and measures:

- [Return Rate (Amount)](sales-powerbi-sales-kpis.md#return-rate-amount)
- [Total Credit (Amount)](sales-powerbi-sales-kpis.md#total-credit-amount)
- [Return Rate (Qty.)](sales-powerbi-sales-kpis.md#return-rate-qty)
- [Total Credit (Qty.)](sales-powerbi-sales-kpis.md#total-credit-qty)
- [No. of Outstanding Return Orders](sales-powerbi-sales-kpis.md#no-of-outstanding-return-orders)
- [Credit Adjusted Profit (LCY)](sales-powerbi-sales-kpis.md#credit-adjusted-profit-lcy)
- [Total Sales (Amount)](sales-powerbi-sales-kpis.md#total-sales-amount)

[!INCLUDE[click-on-a-kpi-link](includes/click-on-a-kpi-link.md)]

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Data used in the report

The report uses data from the following tables:

- Sales Credit Lines
- Sales Value Entries
- Project Ledger Entries
- Customer
- Item Category
- Reason Code
- Item
- G/L Account
- Resource

## Try the report

Try the report here: [Return Order Overview](https://businesscentral.dynamics.com?page=37105)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Ad hoc analysis of sales data](ad-hoc-analysis-sales.md)  
[Built-in sales reports](sales-reports.md)  
[Sales analytics overview](sales-analytics-overview.md)  
[Sales overview](sales-manage-sales.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
