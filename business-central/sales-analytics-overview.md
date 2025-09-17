---
title: Sales analytics
description: Business Central offers features that can help you gather, analyze, and share valuable sales data for business intelligence and decision-making in the sales organization.
author: kennienp
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: bi, power BI, analysis, KPI
ms.search.form: 516, 9300, 5119, 9301, 9305, 36997, 36998, 36999, 37000, 37001, 37002, 37003, 37004, 37005, 37006, 37007, 37008, Report_107, Report_108, Report_111, Report_112, Report_113, Report_119, Report_121, Report_129, Report_209, Report_708, Report_713, Report_718, Report_813, Report_7313
ms.date: 11/11/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Sales analytics

Businesses capture lots of data during daily activities that supports business intelligence (BI) for sales managers:

- Opportunities
- Sales quotes
- Sales orders
- Sales invoices

[!INCLUDE[prod_short](includes/prod_short.md)] provides features to help you gather, analyze, and share your organization's sales data:

- Power BI reports for sales
- Ad-hoc analysis on lists
- Ad-hoc analysis of data in Excel (using Open in Excel)
- Built-in sales analytics tools
- Built-in sales reports

Each of these features has its advantages and disadvantages, depending on the type of data analysis and the role of the user. To learn more, go to [Analytics, business intelligence, and reporting overview](reports-bi-reporting.md).

This article introduces how you can use these analytical features to gain sales insights.

## Analytics needs in sales

When you think about the analytics needs in sales management, it might help to use a persona-based model that describes different analytics needs at a high-level.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg" alt-text="Illustration of different personas for analytics" lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg":::

People in different roles have different needs when it comes to data, and they use the data in different ways. For example, people in asset management and finance interact with data differently than people in sales.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg" alt-text="Illustration of how different personas have different analytics needs." lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg":::

| Role              | Data aggregation  | Typical ways to consume data                          | 
|-------------------|-------------------| ----------------------------------------------------- |
|CCO / CFO / CEO    | Performance data  | KPIs <br> Dashboards <br> Financial reports           |
|Sales Manager      | Trends, summaries | Built-in managerial reports <br> Ad-hoc analysis      | 
|Account Manager / Sales Person | Detailed data     | Built-in operational reports <br> On-screen task data |

<!-- 
## Sales KPIs

A key performance indicator (KPI) is a measurable value that shows how effectively you’re meeting your goals. In sales management, people often use the following KPIs to monitor their organization's sales performance:

- TODO  
-->

## Using Power BI to monitor sales KPIs

A key performance indicator (KPI) is a measurable value that shows how effectively you’re meeting your goals. In sales, people often use the following KPIs to monitor their sales organization's performance:

- Gross Profit
- Gross Profit Margin
- Sales by period
- Sales vs. budget
- Number of new customers
- Period-over-Period Sales Amount Growth
- Sales by item/customer/location/sales person

:::image type="content" source="media/powerbi/sales/sales-overview.png" alt-text="Screenshot of the Sales Overview Power BI report" lightbox="media/powerbi/sales/sales-overview.png":::

These sales KPIs, and more, are available in the Power BI Sales app for [!INCLUDE [prod_short](includes/prod_short.md)]. To learn more, go to [Power BI sales app](sales-powerbi-app.md).

[!INCLUDE [power-bi-sales-app](includes/power-bi-sales-app.md)]

## Use financial reporting to produce financial statements and KPIs related to sales

The **Financial Reporting** feature gives you insights into the financial data shown on your chart of accounts (COA). You can set up financial reports to analyze figures in general ledger (G/L) accounts, and compare general ledger entries with budget entries. Specifically for sales management, you can set up financial reports on the general ledger (G/L) accounts that you use to track sales postings.

Dimensions play an important role in business intelligence. A dimension is data that you add to an entry as a parameter. Dimensions let you group entries that have similar characteristics, such as customers, regions, products, and salesperson. Among other purposes, use dimensions when you define analysis views and create financial reports. To learn more, go to [Work with Dimensions](finance-dimensions.md).

To learn more about financial reports, go to [Prepare Financial Reports with Financial Data and Account Categories](bi-how-work-account-schedule.md).

## Finance reporting across business units or legal entities related to sales

Some organizations use [!INCLUDE [prod_short](includes/prod_short.md)] in multiple business units or legal entities. Others use [!INCLUDE [prod_short](includes/prod_short.md)] in subsidiaries that report to parent organizations. [!INCLUDE [prod_short](includes/prod_short.md)] gives accountants tools that help them transfer general ledger entries from two or more companies (subsidiaries) into a consolidated company. Specifically for sales management, you might want to consolidate general ledger entries for your sales accounts to be able to track sales KPIs across business units or legal entities.

To learn more, go to [Company consolidation](finance-consolidated-company-reporting.md).

## Ad-hoc analysis of sales data

Sometimes, you just need to check whether the numbers add up correctly, or quickly confirm a figure. The following features are great for ad-hoc analyses:

- Data analysis on ledger list pages
- Open in Excel

The Data Analysis feature lets you open almost any list page, such as **General Ledger Entries**, **Customer Ledger Entries**, **Item Ledger Entries**, or **Posted Invoices**, enter analysis mode, and then group, filter, and pivot data as you see fit.

:::image type="content" source="media/data-analysis-customer-ledger-entries.png" alt-text="Example of how to do data analysis on the Customer Ledger Entries page." lightbox="media/data-analysis-customer-ledger-entries.png":::

Similarly, you can use the **Open in Excel** action to open a list page, optionally filter the list to a subset of the data, and then use Excel to work with the data. For example, by using features such as Analyze Data, What-If Analysis, or Forecast Sheet.

:::image type="content" source="media/open-in-excel-customer-ledger-entries.png" alt-text="Example of how to do data analysis on the Customer Ledger Entries data using Excel." lightbox="media/open-in-excel-customer-ledger-entries.png":::

> [!TIP]
> If you configure OneDrive for system features, the Excel workbook opens in your browser.

To learn more about how to do ad-hoc analysis on sales data, go to [Ad hoc analysis of sales data](ad-hoc-analysis-sales.md).

## Built-in reports for sales

[!INCLUDE [prod_short](includes/prod_short.md)] includes several built-in reports, tracing functions, and tools to help sales organizations report on their data.

[!INCLUDE [sales_reports_report_explorer](includes/sales-reports-report-explorer-include.md)]

## On-screen sales analytics

[!INCLUDE [prod_short](includes/prod_short.md)] has several pages that give you sales overviews and tasks to do. Here are some examples to get you started:

- [Open the Sales Quotes list](https://businesscentral.dynamics.com/?page=9300)
- [Open the Sales Orders list](https://businesscentral.dynamics.com/?page=9305)
- [Open the Posted Sales Invoices list](https://businesscentral.dynamics.com/?page=143)
- [Open the Sales Return Orders list](https://businesscentral.dynamics.com/?page=9304)
- [Calculate order promising dates](sales-how-to-calculate-order-promising-dates.md)
- [Calculate delivery dates for sales orders](sales-date-calculation-for-sales.md)
- [Track packages](sales-how-track-packages.md)
- [View the Availability of Items](inventory-how-availability-overview.md)
- [Blanket sales order status](sales-how-to-create-blanket-sales-orders.md#to-view-the-status-of-a-blanket-sales-order)
- [View unposted and posted blanket sales order lines](sales-how-to-create-blanket-sales-orders.md#to-view-unposted-and-posted-blanket-sales-order-lines)

### Show sales-related general ledger entries and balances from the Chart of Accounts page

The **Chart of Accounts** page shows all general ledger accounts with aggregated numbers posted to the general ledger. From this page, you can do things like:  

- View reports that show general ledger entries and balances.  
- Review a list of posting groups for that account.
- View separate debit and credit balances for a single account.

Specifically for sales, you can create a view that only shows the accounts you use for posting sales entries.

:::image type="content" source="media/chart-of-accounts-page.png" alt-text="Example of how the Chart of Accounts page shows finance insights" lightbox="media/chart-of-accounts-page.png":::

To learn more, go to [Understand the Chart of Accounts](finance-general-ledger.md#the-chart-of-accounts).

### Analyze data by dimensions (related to sales)

Dimensions are values that categorize entries so you can track and analyze them on documents, such as sales orders. Dimensions can, for example, indicate the project or department an entry came from.  

So, instead of setting up separate general ledger accounts for each department or location, you can use dimensions as a basis for analysis and avoid having to create a complicated chart of accounts structure.

To learn more, go to [Analyze Data by Dimensions](bi-how-analyze-data-dimension.md).

## Related information

[Company consolidation](finance-consolidated-company-reporting.md)  
[Power BI sales app](sales-powerbi-app.md)  
[Prepare Financial Reports with Financial Data and Account Categories](bi-how-work-account-schedule.md)  
[Handling finance reporting across business units or legal entities](finance-consolidated-company-reporting.md)  
[Ad hoc analysis of sales data](ad-hoc-analysis-sales.md)  
[Built-in sales reports](sales-reports.md)  
[Understand the Chart of Accounts](finance-general-ledger.md#the-chart-of-accounts)  
[Analyze Data by Dimensions](bi-how-analyze-data-dimension.md)  
[Analytics, business intelligence, and reporting overview](reports-bi-reporting.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
