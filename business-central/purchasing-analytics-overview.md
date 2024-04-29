---
title: Purchasing Analytics in Business Central
description: Business Central contains many features to help you gather, analyze, and share valuable sales data for business intelligence and decision-making within the purchasing organization.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: bi, power BI, analysis, KPI
#TODO ms.search.form: 103, 108, 198, 490
ms.date: 04/29/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Purchasing Analytics in Business Central

Businesses capture a tremendous amount of data during daily activities that's supports valuable business intelligence (BI) for purchasing managers: 

- Purchase Quotes
- Purchase Orders
- Purchase Invoices

[!INCLUDE[prod_short](includes/prod_short.md)] contains many features to help you gather, analyze, and share your organization's purchasing data:

- Ad-hoc analysis on lists
- Ad-hoc analysis of data in Excel (using open in Excel)
- Built-in sales reports

Each of these features has its own advantages and disadvantages, depending on the type of data analysis and the role of the user. To learn more, go to [Analytics, business intelligence, and reporting overview](reports-bi-reporting.md).

This article introduces you can use these analytical features to provide purchasing insights.

## Analytics needs in purchasing

When thinking of analytics needs in purchasing management, it might help to use a mental model based on personas described on a high-level and their different analytics needs.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg" alt-text="Illustration of different personas for analytics" lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg":::

People in different roles have different needs when it comes to data, and they use the data in different ways. For example, people in asset management and finance interact with data differently than people in sales.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg" alt-text="Illustration of how different personas have different analytics needs." lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg":::

| Role              | Data aggregation  | Typical ways to consume data                          | 
|-------------------|-------------------| ----------------------------------------------------- |
|COO / CFO / CEO    | Performance data  | KPIs <br> Dashboards <br> Financial reports           |
|Purchasing Manager      | Trends, summaries | Built-in managerial reports <br> Ad-hoc analysis      | 
|**WHO IS THIS** | Detailed data     | Built-in operational reports <br> On-screen task data |

<!-- 
## Purchasing KPIs

A key performance indicator (KPI) is a measurable value that shows how effectively you’re meeting your goals. In purchasing management, people often use the following KPIs to monitor their organization's purchasing performance:

- TODO  
-->


## Using financial reporting to produce financial statements and KPIs (related to purchasing)

The **Financial Reporting** feature gives you insights into the financial data shown on your chart of accounts (COA). You can set up financial reports to analyze figures in general ledger (G/L) accounts, and compare general ledger entries with budget entries. Specifically for purchasing management, you can setup financial reports on the general ledger (G/L) accounts that you use for tracking purchase postings.

Dimensions play an important role in business intelligence. A dimension is data that you can add to an entry as a parameter. Dimensions let you group entries that have similar characteristics, such as customers, regions, and products, and easily retrieve these groups for analysis. Among other purposes, you use dimensions when you define analysis views and create financial reports. Learn more at [Work with Dimensions](finance-dimensions.md).

For more information, see [Prepare Financial Reports with Financial Data and Account Categories](bi-how-work-account-schedule.md).


## Finance reporting across business units or legal entities (related to purchasing)

Some organizations use [!INCLUDE [prod_short](includes/prod_short.md)] in multiple business units or legal entities. Others use [!INCLUDE [prod_short](includes/prod_short.md)] in subsidiaries that must report into parent organizations. [!INCLUDE [prod_short](includes/prod_short.md)] gives accountants tools that help them transfer general ledger entries from two or more companies (subsidiaries) into a consolidated company. Specifically for purchasing management, you might want to consolidate general ledger entries for your purchasing accounts to be able to track sales KPIs across business units or legal entities.

To learn more, go to [Company consolidation](finance-consolidated-company-reporting.md).


## Ad-hoc analysis of purchasing data

Sometimes, you just need to check whether the numbers add up correctly, or quickly confirm a figure. The following features are great for ad-hoc analyses:

- Data analysis on ledger list pages
- Open in Excel

The Data analysis feature lets you open almost a list page, such as **General Ledger Entries**, **Vendor Ledger Entries**, or **TODO**, enter analysis mode, and then group, filter, and pivot data as you see fit.

:::image type="content" source="media/data-analysis-vendor-ledger-entries.png" alt-text="Example of how to do data analysis on the Customer Ledger Entries page." lightbox="media/data-analysis-vendor-ledger-entries.png":::



Similarly, you can use the **Open in Excel** action to open a list page, optionally filter the list to a subset of the data, and then use Excel to work with the data. For example, by using features such as Analyze Data, What-If Analysis, or Forecast Sheet.

:::image type="content" source="media/open-in-excel-customer-ledger-entries.png" alt-text="Example of how to do data analysis on the Customer Ledger Entries data using Excel." lightbox="media/open-in-excel-customer-ledger-entries.png":::

> [!TIP]
> If you configure OneDrive for system features, the Excel workbook opens in your browser by using Excel for the web. 

For more information on how to do ad-hoc analysis on purchasing data, see [Ad-hoc analysis of purchasing data](ad-hoc-analysis-purchasing.md).


## Built-in reports for purchasing

[!INCLUDE [prod_short](includes/prod_short.md)] includes several built-in reports, tracing functions, and tools to help purchasing organizations report on their data.

To get an overview of available reports, you can click **All reports** on the top pane of your home page. This takes you to the Role explorer, which is filtered to the features in the **Report & Analysis** option. To learn more, go to [Finding Reports with the Role Explorer](ui-role-explorer.md). 

:::image type="content" source="media/report-explorer-sales.png" alt-text="Example of reports on the XXX role centre." lightbox="media/report-explorer-sales.png":::

<!-- Built-in reports come in two flavors:

- Designed for print (pdf).
- Designed for analysis in Excel. -->

For more information about reports that are relevant for purchasing, see [Built-in purchasing reports](purchase-reports.md).


## On-screen purchasing analytics

[!INCLUDE [prod_short](includes/prod_short.md)] has a number of pages that give you sales overviews and tasks to do. Here are an example to get you started:

- [Calculate Dates for purchases](purchasing-date-calculation-for-purchases.md)


### Show general ledger entries and balances from the Chart of Accounts page (related to sales)

The Chart of Accounts page shows all general ledger accounts with aggregated numbers on what's posted to the general ledger. From this page, you can do things like:  

- View reports that show general ledger entries and balances.  
- Review a list of posting groups for that account.
- View separate debit and credit balances for a single account.

Specifically for purchasing, you can create a view on the Chart of Accounts page that only shows the accounts you use for posting purchasing entries.

:::image type="content" source="media/chart-of-accounts-page.png" alt-text="Example of how the Chart of Accounts page shows finance insights" lightbox="media/chart-of-accounts-page.png":::

To learn more, go to [Understand the Chart of Accounts](finance-general-ledger.md#the-chart-of-accounts).


### Analyze data by dimensions (related to purchasing)

Dimensions are values that categorize entries so you can track and analyze them on documents, such as purchase orders. Dimensions can, for example, indicate the project or department an entry came from.  

So, instead of setting up separate general ledger accounts for each department or location, you can use dimensions as a basis for analysis and avoid having to create a complicated chart of accounts structure.

For more information, see [Analyze Data by Dimensions](bi-how-analyze-data-dimension.md).


## See also

[Company consolidation](finance-consolidated-company-reporting.md)   
[Prepare Financial Reports with Financial Data and Account Categories](bi-how-work-account-schedule.md)  
[Handling finance reporting across business units or legal entities](finance-consolidated-company-reporting.md)  
[Ad-hoc analysis of purchasing data](ad-hoc-analysis-purchasing.md)  
[Built-in purchasing reports](purchase-reports.md)   
[Understand the Chart of Accounts](finance-general-ledger.md#the-chart-of-accounts)  
[Analyze Data by Dimensions](bi-how-analyze-data-dimension.md)  
[Analytics, business intelligence, and reporting overview](reports-bi-reporting.md)   
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]