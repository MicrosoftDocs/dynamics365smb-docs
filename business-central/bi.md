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

Businesses capture a tremendous amount of data during daily activities. This data, which reflects such things as the organization's sales figures, purchases, operational expenses, employee salaries, and budgets, represents valuable information, or business intelligence (BI), for decision makers. [!INCLUDE[prod_short](includes/prod_short.md)] contains many features to help you gather, analyze, and share your company data:

- Financial reporting (for financial statements and KPIs)
- Ad-hoc analysis on lists
- Ad-hoc analysis of data in Excel (using open in Excel)
- Built-in finance reports

Each of these features has its own advantages and disadvantages, depending on the type of data analysis and the role of the user. In this article, we introduce these analytical features and how they can be used differently in an organization to provide financial insights.

## Analytics needs in finance

When thinking of analytics needs in finance, it might help to use a mental model based on  personas described on a high-level and their different analytics needs.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg" alt-text="Illustration of different personas for analytics" lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg":::

The model is based on the observation that different roles in an organization have different needs when it comes to data: the higher the role is placed in the org chart, the more data needs to be aggregated for them to do their work. 

Each of the roles has some preferred/typical ways to consume/analyze data, ways that reflect the level of data aggregation needed in their role as shown in this illustration and table.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg" alt-text="Illustration of how different personas have different analytics needs." lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg":::

| Role              | Data aggregation  | Typical ways to consume data                | 
|-------------------|-------------------| --------------------------------------------|
|CFO / CEO          | Performance data  | KPIs <br> Dashboards <br> Financial reports |
|Finance Management | Trends, summaries | Managerial reports <br> Ad-hoc analysis     | 
|Bookkepper         | Detailed data     | Operational reports <br> On-screen task data|


## Financial reporting

The *Financial reporting* feature gives you insight into the financial data stored in your chart of accounts (COA). You can setup financial reports to analyze figures in general ledger (G/L) accounts, and compare general ledger entries with budget entries. The results display in charts and reports in your Role Center, such as the cash flow chart and income statement and balance sheet reports.

The **Dimensions** functionality plays an important role in business intelligence. A dimension is data that you can add to an entry as a parameter. As such, you can use it to group entries that have similar characteristics, such as customers, regions, products, and salesperson, and easily retrieve these groups for analysis. Among other purposes, you use dimensions when defining analysis views and creating financial reports. Learn more at [Work with Dimensions](finance-dimensions.md).

> [!TIP]
> As a quick way to analyze transactional data, you can filter totals in the chart of accounts and all entries in **Entries** pages by dimensions. Look for the **Set Dimension Filter** action.  

The following table describes a sequence of tasks, with links to the articles that describe them.  

| To | See |
| --- | --- |
|View actual amounts compared to budgeted amounts for all accounts and for several periods.|[Analyze Actual Amounts Versus Budgeted Amounts](bi-how-analyze-actual-versus-budget.md)|
|Create new financial reports to define financial statements for reporting or to display as charts.|[Prepare Financial Reports with Financial Data and Account Categories](bi-how-work-account-schedule.md)|
|Analyze your financial performance by setting up key performance indicators (KPIs) based on financial reports, which you then publish as web services. The published financial reports KPIs can be viewed on a web site or imported to Microsoft Excel using OData web services.|[Set Up and Publish KPI Web Services Based on Financial Reports](bi-how-to-set-up-and-publish-kpi-web-services-based-on-account-schedules.md)|
|Set up views to analyze data using dimensions.|[Analyze Data by Dimensions](bi-how-analyze-data-dimension.md)|
|Create new analysis reports for sales, purchases, and inventory, and set up analysis templates.|[Create Analysis Reports](bi-how-create-analysis-views-reports.md)|

## Ad-hoc analysis of financial data

CoA page

Data analysis on ledgers


## Built-in reports for finance



## See also

[Finance](finance.md)  
[Use Business Central as a Power BI Data Source](across-how-use-financials-data-source-powerbi.md)  
[Closing Fiscal Periods](year-close-years-periods.md)  
[Importing Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Business Intelligence and Reporting Overview](reports-bi-reporting.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
