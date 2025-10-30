---
title: Analytics in purchasing
description: Learn how to use Business Central's analytics features to monitor purchasing KPIs, perform ad-hoc analysis, and create financial reports.
author: kennienp
ms.author: kepontop
ms.reviewer: v-soumramani
ms.topic: article
ms.search.keywords: bi, power BI, analysis, KPI
ms.search.form: 9306, 9307, 518, 29, 36996, 37009, 37010, 37011, 37012, 37013, 37014, 37015, 37016, 37017, 37018, 37019, 37020, 37021, 37025, Report_307, Report_308, Report_311, Report_312, Report_313, Report_409, Report_716, Report_319, Report_320, Report_707, Report_709, Report_714, Report_716, Report_720
ms.date: 10/03/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Analytics in purchasing

Businesses capture lots of data during daily activities that supports business intelligence (BI) for purchasing managers:

- Purchase quotes
- Purchase orders
- Purchase invoices

[!INCLUDE[prod_short](includes/prod_short.md)] provides features to help you gather, analyze, and share your organization's purchasing data:

- Power BI reports for purchasing
- Ad-hoc analysis on lists
- Ad-hoc analysis of data in Excel (using open in Excel)
- Built-in sales reports

Each of these features has advantages and disadvantages, depending on the type of data analysis and the role of the user. Learn more in [Analytics, business intelligence, and reporting overview](reports-bi-reporting.md).

This article introduces how you can use these analytical features to gain purchasing insights.

## Analytics needs in purchasing

When you think about the analytics needs in purchasing, it might help to use a persona-based model that describes different analytics needs at a high-level.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg" alt-text="Illustration of different personas for analytics" lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg":::

People in different roles have different needs when it comes to data, and they use the data in different ways. For example, people in asset management and finance interact with data differently than people in sales.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg" alt-text="Illustration of how different personas have different analytics needs." lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg":::

| Role | Data aggregation | Typical ways to consume data |
|--|--|--|
| COO / CSO / CFO / CEO | Performance data | KPIs <br> Dashboards <br> Financial reports |
| Purchasing Manager | Trends, summaries | Built-in managerial reports <br> Ad-hoc analysis |
| Purchasing Officer / Purchasing Agent | Detailed data | Built-in operational reports <br> On-screen task data |

## Using Power BI to monitor purchasing KPIs

A key performance indicator (KPI) is a measurable value that shows how effectively you’re meeting your goals. In procurement, people often use the following KPIs to monitor their procurement organization's performance:

- Outstanding Amount (excluding VAT)
- Amount Received but Not Invoiced (excluding VAT)
- Period-over-Period Purchases Growth (Amount or in percentage)
- Purchases by Item/Vendor/Location/Purchaser
- Actual purchases vs Budget

:::image type="content" source="media/purchases/purchases-overview.png" alt-text="Screenshot of the Purchases Overview Power BI report" lightbox="media/purchases/purchases-overview.png":::

These purchasing KPIs, and more, are available in the Power BI Purchasing app for [!INCLUDE [prod_short](includes/prod_short.md)]. Learn more in [Power BI Purchasing app](purchases-powerbi-app.md).

[!INCLUDE [power-bi-purchasing-app](includes/power-bi-purchasing-app.md)]

## Use financial reporting to produce financial statements and KPIs (related to purchasing)

The **Financial Reporting** feature gives you insights into the financial data shown on your chart of accounts (COA). You can set up financial reports to analyze figures in general ledger (G/L) accounts, and compare general ledger entries with budget entries. Specifically for purchasing, you can set up financial reports on the general ledger (G/L) accounts that you use to track purchase postings.

Dimensions play an important role in business intelligence. A dimension is data that you can add to an entry as a parameter. Dimensions let you group entries that have similar characteristics, such as customers, regions, and products, and easily retrieve these groups for analysis. Among other purposes, use dimensions when you define analysis views and create financial reports. Learn more in [Work with Dimensions](finance-dimensions.md).

Learn more about financial reports in [Prepare Financial Reports with Financial Data and Account Categories](bi-how-work-account-schedule.md).

## Finance reporting across business units or legal entities (related to purchasing)

Some organizations use [!INCLUDE [prod_short](includes/prod_short.md)] in multiple business units or legal entities. Others use [!INCLUDE [prod_short](includes/prod_short.md)] in subsidiaries that report to parent organizations. [!INCLUDE [prod_short](includes/prod_short.md)] gives accountants tools that help them transfer general ledger entries from two or more companies (subsidiaries) into a consolidated company. Specifically for purchasing management, you might want to consolidate general ledger entries for your purchasing accounts to track sales KPIs across business units or legal entities.

Learn more in [Company consolidation](finance-consolidated-company-reporting.md).

## Ad-hoc analysis of purchasing data

Sometimes, you just need to check whether the numbers add up correctly, or quickly confirm a figure. The following features are great for ad-hoc analyses:

- Data analysis on ledger list pages
- Open in Excel

The **Data Analysis** feature lets you open almost any list page, such as **Purchase Orders**, **Posted Purchase Invoices**, **Vendor Ledger Entries**, or **General Ledger Entries**, enter analysis mode, and then group, filter, and pivot data as you see fit.

:::image type="content" source="media/data-analysis-vendor-ledger-entries.png" alt-text="Example of how to do data analysis on the Customer Ledger Entries page." lightbox="media/data-analysis-vendor-ledger-entries.png":::

Similarly, you can use the **Open in Excel** action to open a list page, filter the list to a subset of the data, and then use Excel to work with the data. For example, by using features such as Analyze Data, What-If Analysis, or Forecast Sheet.

:::image type="content" source="media/open-in-excel-vendor-ledger-entries.png" alt-text="Example of how to do data analysis on the Customer Ledger Entries data using Excel." lightbox="media/open-in-excel-vendor-ledger-entries.png":::

> [!TIP]
> If you configure OneDrive for system features, the Excel workbook opens in your browser.

Learn more in [Ad hoc analysis of purchasing data](ad-hoc-analysis-purchasing.md) for information about how to do ad-hoc analysis on purchasing data.

## Built-in reports for purchasing

[!INCLUDE [prod_short](includes/prod_short.md)] includes several built-in reports, tracing functions, and tools to help purchasing organizations report on their data.

[!INCLUDE [purchasing_reports_report_explorer](includes/purchasing-reports-report-explorer-include.md)]

## On-screen purchasing analytics

[!INCLUDE [prod_short](includes/prod_short.md)] has several pages that give you purchasing overviews and tasks to do. Here's an example to get you started:

- [View the Availability of Items](inventory-how-availability-overview.md)  
- [Calculate Dates for purchases](purchasing-date-calculation-for-purchases.md)
- [View purchase ledger entries](purchasing-how-record-purchases.md#viewing-ledger-entries)

### Show purchasing-related general ledger entries and balances from the Chart of Accounts page

The Chart of Accounts page shows all general ledger accounts with aggregated numbers posted to the general ledger. From this page, you can do things like:  

- View reports that show general ledger entries and balances.  
- Review a list of posting groups for that account.
- View separate debit and credit balances for a single account.

Specifically for purchasing, you can create a view on the Chart of Accounts page that only shows the accounts you use to post purchasing entries.

:::image type="content" source="media/chart-of-accounts-page.png" alt-text="Example of how the Chart of Accounts page shows finance insights" lightbox="media/chart-of-accounts-page.png":::

Learn more in [Understand the Chart of Accounts](finance-general-ledger.md#the-chart-of-accounts).

### Analyze data by dimensions (related to purchasing)

Dimensions are values that categorize entries so you can track and analyze them on documents, such as purchase orders. Dimensions can, for example, indicate the project or department an entry came from.  

So, instead of setting up separate general ledger accounts for each department or location, you can use dimensions as a basis for analysis and avoid having to create a complicated chart of accounts structure.

Learn more in [Analyze Data by Dimensions](bi-how-analyze-data-dimension.md).

## Related information

[Company consolidation](finance-consolidated-company-reporting.md)  
[Power BI Purchasing app](purchases-powerbi-app.md)  
[Prepare Financial Reports with Financial Data and Account Categories](bi-how-work-account-schedule.md)  
[Handling finance reporting across business units or legal entities](finance-consolidated-company-reporting.md)  
[Ad hoc analysis of purchasing data](ad-hoc-analysis-purchasing.md)  
[Built-in purchasing reports](purchase-reports.md)  
[Understand the Chart of Accounts](finance-general-ledger.md#the-chart-of-accounts)  
[Analyze Data by Dimensions](bi-how-analyze-data-dimension.md)  
[Analytics, business intelligence, and reporting overview](reports-bi-reporting.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
