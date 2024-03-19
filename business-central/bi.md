---
title: Financial Analytics in Business Central
description: Business Central contains many features to help you gather, analyze, and share valuable company data for business intelligence and decision-making.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: bi, power BI, analysis, KPI
ms.search.form: 103, 108, 198, 490
ms.date: 09/22/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
---

# Financial Analytics in Business Central

Businesses capture a tremendous amount of data during daily activities. This data, which reflects such things as the organization's sales figures, purchases, operational expenses, employee salaries, and budgets, represents valuable information, or business intelligence (BI), for decision makers. [!INCLUDE[prod_short](includes/prod_short.md)] contains many features to help you gather, analyze, and share your organization's finance data:

- Financial reporting (for financial statements and KPIs)
- Ad-hoc analysis on lists
- Ad-hoc analysis of data in Excel (using open in Excel)
- Built-in finance reports

Each of these features has its own advantages and disadvantages, depending on the type of data analysis and the role of the user. To learn more, see [Analytics, business intelligence, and reporting overview](reports-bi-reporting.md).

In this article, we introduce how these analytical features can be used in an organization to provide financial insights.

## Analytics needs in finance

When thinking of analytics needs in finance, it might help to use a mental model based on personas described on a high-level and their different analytics needs.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg" alt-text="Illustration of different personas for analytics" lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg":::

The model is based on the observation that different roles in an organization have different needs when it comes to data: the higher the role is placed in the org chart, the more data needs to be aggregated for them to do their work. 

Each of the roles has some preferred/typical ways to consume/analyze data, ways that reflect the level of data aggregation needed in their role as shown in this illustration and table.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg" alt-text="Illustration of how different personas have different analytics needs." lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg":::

| Role              | Data aggregation  | Typical ways to consume data                          | 
|-------------------|-------------------| ----------------------------------------------------- |
|CFO / CEO          | Performance data  | KPIs <br> Dashboards <br> Financial reports           |
|Finance Management | Trends, summaries | Built-in managerial reports <br> Ad-hoc analysis      | 
|Bookkeeper         | Detailed data     | Built-in operational reports <br> On-screen task data |


## Finance KPIs

A key performance indicator (KPI) is a measurable value that shows how effectively you’re meeting your goals. Think of KPIs as your organization's scorecard, a way of measuring whether or not you’re delivering on your objectives. 

In finance, the following KPIs are commonly used for monitoring your organization's financial health:

- Gross Profit Margin
- Net Profit Margin
- Working Capital 
- Current/Quick Ratio
- Financial leverage, also known as the Equity Multiplier
- Debt-to-Equity Ratio
- Total Asset Turnover
- Return on Equity
- Return on Assets

For more information, see [Financial KPIs in Business Central](bi-finance-kpis.md)


## Using Financial reporting to produce financial statements and KPIs

The *Financial reporting* feature gives you insight into the financial data stored in your chart of accounts (COA). You can setup financial reports to analyze figures in general ledger (G/L) accounts, and compare general ledger entries with budget entries. The results display in charts and reports in your Role Center, such as the cash flow chart and income statement and balance sheet reports.

The **Dimensions** functionality plays an important role in business intelligence. A dimension is data that you can add to an entry as a parameter. As such, you can use it to group entries that have similar characteristics, such as customers, regions, products, and salesperson, and easily retrieve these groups for analysis. Among other purposes, you use dimensions when defining analysis views and creating financial reports. Learn more at [Work with Dimensions](finance-dimensions.md).

> [!TIP]
> As a quick way to analyze transactional data, you can filter totals in the chart of accounts and all entries in **Entries** pages by dimensions. Look for the **Set Dimension Filter** action.  

The following table describes a sequence of tasks within financial reporting, with links to the articles that describe them.  

| To | See |
| --- | --- |
|Create new financial reports to define financial statements for reporting or to display as charts.|[Prepare Financial Reports with Financial Data and Account Categories](bi-how-work-account-schedule.md)|
|Analyze your financial performance by setting up key performance indicators (KPIs) based on financial reports, which you then publish as web services. The published financial reports KPIs can be viewed on a web site or imported to Microsoft Excel using OData web services.|[Set Up and Publish KPI Web Services Based on Financial Reports](bi-how-to-set-up-and-publish-kpi-web-services-based-on-account-schedules.md)|
|Set up views to analyze data using dimensions.|[Analyze Data by Dimensions](bi-how-analyze-data-dimension.md)|
|Create new analysis reports for sales, purchases, and inventory, and set up analysis templates.|[Create Analysis Reports](bi-how-create-analysis-views-reports.md)|


## Finance reporting across business units or legal entities

Some organizations use [!INCLUDE [prod_short](includes/prod_short.md)] in multiple business units or legal entities. Others use [!INCLUDE [prod_short](includes/prod_short.md)] in subsidiaries that must report into parent organizations. [!INCLUDE [prod_short](includes/prod_short.md)] gives accountants tools that help them transfer general ledger entries from two or more companies (subsidiaries) into a consolidated company.  

For more information, see [Company consolidation](finance-consolidated-company-reporting.md)


## Ad-hoc analysis of finance data

Sometimes, you just need to check if the numbers add up correctly, quickly confirm or debunc a hypothosis about the business, or maybe look for anomalies in your financial data. For these ad-hoc analysis tasks, you might not have a built-in report that helps you with your questions, instead you can use these two features
- Data analysis on ledger list pages
- Open in Excel

With the *Data analysis* feature, you can open almost a list page such as General Ledger Entries, Fixed assets Ledger Entries, Check Ledger Entries, or Bank Account Ledger Entries, enter analysis mode, and then group, filter, and pivot data as you see fit, all directly in the [!INCLUDE [prod_short](includes/prod_short.md)] client. 

:::image type="content" source="media/data-analysis-gl-entries.png" alt-text="Example of how to do data analysis on the G/L entries page." lightbox="media/data-analysis-gl-entries.png":::


Similarly, using the *Open in Excel* feature, you can open a list page such as General Ledger Entries, Fixed assets Ledger Entries, Check Ledger Entries, or Bank Account Ledger Entries, optionally filter the list to a subset of the data, and then get the data in Excel. You can then do further analysis in Excel, using built-in Excel functionality such as Analyze Data, What-If Analysis, or Forecast Sheet.

:::image type="content" source="media/open-in-excel-gl-entries.png" alt-text="Example of how to do data analysis on the G/L entries data using Excel." lightbox="media/open-in-excel-gl-entries.png":::

> [!TIP]
> If your organization has configured OneDrive for system features, the Excel workbook is opened in your browser by using Excel for the web. 

For more information on how to do ad-hoc analysis on ledgers, see [Ad-hoc analysis on finance data](ad-hoc-analysis-finance.md).


## Built-in reports for finance

[!INCLUDE [prod_short](includes/prod_short.md)] includes several built-in reports, tracing functions, and tools to help auditors or controllers who are responsible for reporting to the finance department. 

To get an overview of available reports, you can click **All reports** on the top pane of your role centre. This takes you to the Role explorer limiting the features shown to the **Report & Analysis** option. For more information, see [Finding Reports with the Role Explorer](ui-role-explorer.md).

:::image type="content" source="media/report-explorer-finance.png" alt-text="Example of reports on the finance role centre." lightbox="media/report-explorer-finance.png":::

Built-in reports come in two flavors: one designed for print (pdf) and one designed for further consumption and analysis in Excel. For more information, see these overviews for reports that are relevant for finance
* [Built-in finance Excel reports](finance-analyze-excel.md)
* [Built-in key finance reports](finance-reports.md)
* [Built-in fixed assets reports](fa-reports.md)
* [Built-in accounts receivable reports](receivables-reports.md)
* [Built-in accounts payable reports](payables-reports.md)

<!-- TODO: add when we have that article
* [Built-in Cost Accounting reports](cost-accounting-reports.md) 
* [Built-in Cash Management reports](cost-accounting-reports.md) 
* [Built-in Tax and VAT reports](tax-and-vat-reports.md) 
-->


## On-screen finance task pages

[!INCLUDE [prod_short](includes/prod_short.md)] has a number of pages that you can use for getting finance overviews and tasks to perform within the finance area. 

### Show general ledger entries and balances from the Chart of Accounts page

The Chart of Accounts page shows all general ledger accounts with aggreated numbers on what has been posted to the. From this page, you can do things like:  

* View reports that show general ledger entries and balances.  
* See a list of posting groups for that account.
* View separate debit and credit balances for a single account.

:::image type="content" source="media/chart-of-accounts-page.png" alt-text="Example of how the Chart of Accounts page shows finance insights" lightbox="media/chart-of-accounts-page.png":::

For more information, see [Understand the Chart of Accounts](finance-general-ledger.md#the-chart-of-accounts)

### View actual amounts compared to budgeted amounts for all accounts and for several periods

As a part of gathering, analyzing, and sharing your company data, you might want to view actual amounts compared to budgeted amounts for all accounts and for several periods. You can do this from  the **Chart of Accounts** page, by choosing the **G/L Balance/Budget** action.

For more information, see [Analyze Actual Amounts Versus Budgeted Amounts](bi-how-analyze-actual-versus-budget.md)

### Analyzing Cash Flow 

On the Accountant Role Center, under Finance Performance, the Cash Cycle, Cash Flow, and Income & Expense charts offer ways to analyze cash flow:
- See figures for a period by using the timeline slider.
- Filter the chart by choosing the source in the legend.
- Change the length of the period, or go to the previous or next period, by choosing options on the Finance Performance drop down.

:::image type="content" source="media/cashflow-accountant-rolecentre.png" alt-text="Example of how the cash flow visuals look on the accountant role centre" lightbox="media/cashflow-accountant-rolecentre.png":::


If you want to examine the forecast, in addition to forecast entries, you can also look at the cash flow worksheet. For example, you can see how the forecast:
- Handles confirmed sales and purchases.
- Subtracts payables and adds receivables.
- Skips duplicate sales orders and purchase orders.

For more information, see [Analyzing Cash Flow in Your Company](finance-analyze-cash-flow.md)


## See also

[Handling finance reporting across business units or legal entities](finance-consolidated-company-reporting.md)   
[Financial KPIs in Business Central](bi-finance-kpis.md)   
[Prepare Financial Reports with Financial Data and Account Categories](bi-how-work-account-schedule.md)   
[Ad-hoc analysis on finance data](ad-hoc-analysis-finance.md)  
[Understand the Chart of Accounts](finance-general-ledger.md#the-chart-of-accounts)  
[Built-in finance Excel reports](finance-analyze-excel.md)  
[Built-in key finance reports](finance-reports.md)  
[Built-in fixed assets reports](fa-reports.md)  
[Built-in accounts receivable reports](receivables-reports.md)  
[Built-in accounts payable reports](payables-reports.md)  
[Finance overview](finance.md)  
[Analytics, business intelligence, and reporting overview](reports-bi-reporting.md)   
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
