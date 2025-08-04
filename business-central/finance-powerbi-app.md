---
title: Finance Power BI app
description: The Power BI Finance app provides comprehensive finance analytics to stakeholders at all levels of organizations.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: reporting
ms.search.form: 37059_Primary, 36984, 36985, 36986, 36987, 36988, 36989, 36990, 36991, 36992, 36993,36994, 36995, 36996, 36997
ms.date: 10/30/2024
ms.service: dynamics-365-business-central
---

# Finance Power BI app

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

This article explains how to use embedded Power BI reports in [!INCLUDE [prod_short](includes/prod_short.md)] to analyze finance data. You don't have to run a report or switch to another application, such as Excel. The feature provides an interactive and versatile way to calculate, summarize, and examine data in curated reports with predefined KPIs.

The Power BI reports on finance data support many analytics scenarios for finance processes.

Executives and the leadership team consume the data through high-level dashboards that present key performance indicators (KPIs) for finance. The KPIs aggregate data to provide a clear and concise overview of overall financial health, and highlight important performance metrics. This approach helps business leaders quickly assess performance toward strategic goals and make informed decisions without getting lost in granular details.

Managers and team leaders engage with the data through detailed managerial reports that showcase trends and summaries. Data is aggregated over time to reveal patterns and highlight areas that need attention. These reports provide context through charts, visualizations, and comparisons that help you understand underlying trends, identify risks, and make data-driven tactical adjustments.

Finance staff accesses operational reports that offer detailed, granular-level data. These reports offer task-specific information for daily functions. Staff can mine the data for specific transactions, process monitoring, and operational insights, ensuring effective day-to-day management of financial activities.

You can use the various reports in the Power BI Finance app for different things, depending on your role. This article describes some examples of use cases for different roles in an organization.

## Finance analytics for the leadership team

To fit this category, you might have a role such as:

- Executive
- Director
- Other high-level decision maker

### Sample scenario for a CFO

As the CFO, you're preparing for an upcoming board meeting and need an analysis of your company's financial position for the current fiscal quarter.

Using the [Financial Overview (Power BI report)](finance-powerbi-financial-overview.md), you begin with a comparative analysis of revenues. This quarter's revenue of $281,000 represents a significant increase compared to the same period last year of $242,000, marking a growth of $39,000, or approximately 16.1%. This positive trend indicates strong performance and suggests that current strategies are effectively increasing revenue.

:::image type="content" source="media/finance/financial-overview-app-page.png" alt-text="Screenshot of the Finance Overview report" lightbox="media/finance/financial-overview-app-page.png":::

You want to compare the net profit margin for the current quarter to the same period in the previous year. You quickly identify that net profit margins are slightly lower, but you need more information to determine why.

:::image type="content" source="media/finance/net-profit-margin-by-fiscal-year-and-month.png" alt-text="Screenshot of the Net Profit Margin visual" lightbox="media/finance/net-profit-margin-by-fiscal-year-and-month.png":::

By analyzing the [Profitability](finance-powerbi-profitability.md) report, you can easily see that expenses are up from 3.60 K to 11.85 K for the same period. Although revenue is up by approximately 16.1%, the increase in expenses suppressed growth and produced a marginal increase in profits.

:::image type="content" source="media/finance/profitability-snapshot.png" alt-text="Screenshot of the Profitability report" lightbox="media/finance/profitability-snapshot.png":::

To ensure the company is able to cover its short-term obligations, fund new initiatives, and maintain operational stability you review the liquidity report and cash reserves.

The cash ratio of 1.0 indicates that the company has enough cash and cash equivalents (1.02M) to pay off all current liabilities (1.02M) immediately, if needed. The quick ratio of 1.15 indicates that without including inventory in current assets, the company can still cover its short-term debts without relying on sales of inventory. Overall, the current ratio of 1.21 indicates the company is in a balanced but cautious liquidity position with current assets of $1.24M to current liabilities of 1.02M.

:::image type="content" source="media/finance/liquidity-kpi-snapshot.png" alt-text="Screenshot of the Liquidity report" lightbox="media/finance/liquidity-kpi-snapshot.png":::

## Finance analytics for the management team

As the Operations Manager, you oversee service delivery across various customer segments. These customer groups are tracked as dimensions values (Large, Medium, and Small) by the **Customer Group** global dimension.

By filtering the [Budget Comparison (Power BI report)](finance-powerbi-budget-comparison.md) by **Global Dimension 2** and **G/L Account Category** to **Income** and **Expense**, you can easily track budget performance. This data lets you allocate resources effectively, control the budget, and make data-driven decisions when you forecast.

:::image type="content" source="media/finance/budget-comparison-snapshot.png" alt-text="Screenshot of the Budget Comparison report" lightbox="media/finance/budget-comparison-snapshot.png":::

## Finance analytics for daily finance work

As a member of the accounts receivable team, you manage the inflow of cash by ensuring timely and efficient collection of payments from customers. To monitor and prioritize your efforts, you use the [Aged Receivables (Back Dating) (Power BI report)](finance-powerbi-aged-receivables-back-dating.md).

Analyzing by payment terms code allows you to quickly identify customers who have outstanding balances in aging buckets beyond 30 days. You can now prioritize not only customers, but the invoices those customers should pay first.

:::image type="content" source="media/finance/aged-receivables-snapshot.png" alt-text="Screenshot of the Aged Receivables (Back Dating) report" lightbox="media/finance/aged-receivables-snapshot.png":::

## Report overview in the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)]

[!INCLUDE [power-bi-finance-app](includes/power-bi-finance-app.md)]

## Set up the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)]

For the [!INCLUDE [powerbi-finance-app-name](includes/power-bi-finance-app-name.md)] to show correct KPIs and reports, there are a few things to set up in [!INCLUDE [prod_short](includes/prod_short.md)].

1. Set up G/L account categories for your chart of accounts.
1. Map G/L account categories to corresponding categories in the [!INCLUDE [prod_short](includes/powerbi-name.md)] Finance semantic model.

To learn more, go to [Setting up the Power BI finance app](finance-powerbi-app-setup.md).

## Related information

[Installing Power BI apps for Business Central](across-powerbi-install-business-central-apps.md)  
[Setting up the Power BI finance app](finance-powerbi-app-setup.md)  
[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Ad hoc analysis on finance data](ad-hoc-analysis-finance.md)  
[Built-in core finance reports](finance-reports.md)  
[Built-in fixed assets reports](fa-reports.md)  
[Built-in accounts receivable reports](receivables-reports.md)  
[Built-in accounts payable reports](payables-reports.md)  
[Financial analytics overview](bi.md)  
[Finance overview](finance.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
