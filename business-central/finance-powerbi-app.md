---
title: Finance Power BI app
description: The Power BI Finance app provides comprehensive finance analytics to stakeholders at all levels of organizations.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
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

## Report overview in the Power BI Finance app

The following table describes the reports in the Power BI Finance app, and how you can use them.

| To... | Open in Business Central (CTRL+select) | Learn more |
| ----- | ---------------------------------------- | ---------- |
|See a snapshot of the organization's financial health and performance. This page displays key performance indicators that give stakeholders a clear view of revenue, profitability, and financial stability.| [Financial Overview](https://businesscentral.dynamics.com?page=36984) | [About Financial Overview](./finance-powerbi-financial-overview.md) |
|Analyze and compare income statement accounts on a monthly basis with the **Income Statement by Month** report to gain a comparative view of net changes over time.| [Income Statement](https://businesscentral.dynamics.com?page=36985) | [About Income Statement](finance-powerbi-income-statement.md) |
|Analyze and compare balance sheet accounts on a monthly basis with the **Balance Sheet by Month** report to gain a comparative view of balance at date over time.| [Balance Sheet](https://businesscentral.dynamics.com?page=36986) | [About Balance Sheet](finance-powerbi-balance-sheet.md) |
|Compare G/L budgets to actuals on a month-to-month basis and quickly identify variances. | [Budget Comparison](https://businesscentral.dynamics.com?page=36987) | [About Budget Comparison](finance-powerbi-budget-comparison.md) |
|Analyze your company's liquidity position and track Current Ratio, Quick Ratio, and Cash Ratio over time. | [Liquidity KPIs](https://businesscentral.dynamics.com?page=36988) | [About Liquidity KPIs](finance-powerbi-liquidity.md) |
|Analyze your company's gross and net profits over time. Get detailed insights into net margins, gross profit margins, and the underlying revenue with the cost and expense figures that drive them.| [Profitability](https://businesscentral.dynamics.com?page=36989) | [About Profitability](finance-powerbi-profitability.md) |
|Analyze liability account balances as of a specific date. The report also shows key performance metrics influenced by liabilities, such as the debt ratio and debt-to-equity ratio.| [Liabilities](https://businesscentral.dynamics.com?page=36990) | [About Liabilities](finance-powerbi-liabilities.md) |
| Analyze the EBITDA and EBIT profitability metrics. These figures show over time to reveal trends, while also showing operating revenue and operating expenses to provide context for both measures.| [EBITDA](https://businesscentral.dynamics.com?page=36991) | [About EBITDA](finance-powerbi-ebitda.md) |
|Analyze how many days it takes to collect accounts receivable. See trends in the average collection period over time. Details such as the number of days, accounts receivable, and accounts receivable (average) provide context and enhance the analysis.| [Average Collection Period](https://businesscentral.dynamics.com?page=36992) | [About Average Collection Period](finance-powerbi-average-collection-period.md) |
|Categorize customer balances into aging buckets and see a breakdown by payment terms. Age by document date, due date, or posting date, and customize the aging bucket size by specifying the number of days. | [Aged Receivables (Back Dating)](https://businesscentral.dynamics.com?page=36993) | [About Aged Receivables (Back Dating)](finance-powerbi-aged-receivables-back-dating.md) |
|Categorize vendor balances into aging buckets and see a breakdown by payment terms. Age by document date, due date, or posting date, and customize the aging bucket size by specifying the number of days.| [Aged Payables (Back Dating)](https://businesscentral.dynamics.com?page=36994) | [About Aged Payables (Back Dating)](finance-powerbi-aged-payables-back-dating.md) |
|Analyze general ledger entries in detail, and slice G/L entries by all eight shortcut dimensions. | [General Ledger Entries](https://businesscentral.dynamics.com?page=36995) |[About General Ledger Entries](finance-powerbi-general-ledger-entries.md) |
|Analyze entries posted to the Vendor Ledger and Detailed Vendor Sub Ledger.| [Detailed Vendor Ledger Entries](https://businesscentral.dynamics.com?page=36996) | [About Detailed Vendor Ledger Entries](finance-powerbi-detailed-vendor-ledger-entries.md) |
|Analyze entries posted to the Customer Ledger and Detailed Customer Sub Ledger.| [Detailed Customer Ledger Entries](https://businesscentral.dynamics.com?page=36997) | [About Detailed Customer Ledger Entries](finance-powerbi-detailed-customer-ledger-entries.md) |

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## See also

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Ad hoc analysis on finance data](ad-hoc-analysis-finance.md)  
[Built-in core finance reports](finance-reports.md)  
[Built-in fixed assets reports](fa-reports.md)  
[Built-in accounts receivable reports](receivables-reports.md)  
[Built-in accounts payable reports](payables-reports.md)  
[Financial analytics overview](bi.md)  
[Finance overview](finance.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
