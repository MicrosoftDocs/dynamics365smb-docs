---
title: Business Intelligence and Reporting Overview
description: Provides an overview of all the business intelligence and reporting features supported in Business Central.
author: KennieNP
ms.topic: get-started
ms.devlang: al
ms.search.keywords: feature overview
ms.reviewer: bholtorf
ms.date: 09/22/2022
ms.author: kepontop
ms.service: dynamics-365-business-central
---

# Business Intelligence and Reporting Overview

Small and mid-sized companies rely on built-in analytics and reporting capabilities they can use out-of-the-box to help keep track of their business. [!INCLUDE[prod_short](includes/prod_short.md)] supports common business processes as well as more complex processes for such organizations. Each of these processes includes reports and analytics tools. You can also do ad-hoc analysis directly from your home page.  

## Analytics needs in organizations

When thinking of analytics needs in organizations, it might help to use a mental model based on  personas described on a high-level and their different analytics needs.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg" alt-text="Illustration of different personas for analytics" lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg":::

The model is based on the observation that different roles in an organization have different needs when it comes to data: the higher the role is placed in the org chart, the more data needs to be aggregated for them to do their work. 

Each of the roles has some preferred/typical ways to consume/analyze data, ways that reflect the level of data aggregation needed in their role as shown in this illustration and table.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg" alt-text="Illustration of how different personas have different analytics needs." lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg":::

In the paragraphs below, you can learn more about each of the ways to consume data from [!INCLUDE[prod_short](includes/prod_short.md)]

- KPIs and dashboards
- Ad-hoc analysis
- Reports

## Using Financial reporting to produce financial statements and KPIs

The *Financial reporting* feature in [!INCLUDE[prod_short](includes/prod_short.md)] gives you insight into the financial data stored in your chart of accounts (COA). You can setup financial reports to analyze figures in general ledger (G/L) accounts, and compare general ledger entries with budget entries. The results display in charts and reports in your Role Center, such as the cash flow chart and income statement and balance sheet reports.

<!-- Screenshot here when available -->

Using the **Dimensions** functionality in [!INCLUDE[prod_short](includes/prod_short.md)] plays an important role in business intelligence. A dimension is data that you can add to an entry as a parameter. As such, you can use it to group entries that have similar characteristics, such as customers, regions, products, and salesperson, and easily retrieve these groups for analysis. Among other purposes, you use dimensions when defining analysis views and creating financial reports. Learn more at [Work with Dimensions](finance-dimensions.md).

For more information about financial statements and KPIs, see [Using Financial reporting to produce financial statements and KPIs](bi.md)


## What is a KPI and why should I care?
A key performance indicator (KPI) is a measurable value that shows how effectively you’re meeting your goals. Think of KPIs as your company’s scorecard, a way of measuring whether or not you’re delivering on your objectives.

Identifying and tracking KPIs lets you know if your business is on the right path—or if you should change course to avoid losing valuable time and money. When used properly, KPIs are powerful tools that help you:

- Monitor company financial health.
- Measure progress against strategic goals.
- Spot problems early on.
- Make timely adjustments to tactics.
- Motivate team members.
- Make better decisions, faster.

For more info, [Using key performance indicators (KPIs) to meet your business goals](./analytics-about-kpis.md)


## Ad-hoc data analysis 

Sometimes, you just need to check if the numbers add up correctly, quickly confirm or debunc a hypothosis about the business, or maybe look for anomalies in your financial data. For these ad-hoc analysis tasks, you might not have a built-in report that helps you with your questions, instead you can use these two features
- Data analysis on ledger list pages
- Open in Excel

With the *Data analysis* feature, you can open almost a list page such as General Ledger Entries or , Customer Ledger Entries, enter analysis mode, and then group, filter, and pivot data as you see fit, all directly in the [!INCLUDE [prod_short](includes/prod_short.md)] client. 

:::image type="content" source="media/data-analysis-gl-entries.png" alt-text="Example of how to do data analysis on the G/L entries page." lightbox="media/data-analysis-gl-entries.png":::

Similarly, using the *Open in Excel* feature, you can open a list page such as General Ledger Entries  or Customer Ledger Entries, optionally filter the list to a subset of the data, and then get the data in Excel. You can then do further analysis in Excel, using built-in Excel functionality such as Analyze Data, What-If Analysis, or Forecast Sheet.

:::image type="content" source="media/open-in-excel-gl-entries.png" alt-text="Example of how to do data analysis on the G/L entries data using Excel." lightbox="media/open-in-excel-gl-entries.png":::

> [!TIP]
> If your organization has configured OneDrive for system features, the Excel workbook is opened in your browser by using Excel for the web. 

For more information, see [Ad-hoc data analysis](reports-adhoc-analysis.md).


## Reports in [!INCLUDE[prod_short](includes/prod_short.md)]

A report in [!INCLUDE[prod_short](includes/prod_short.md)] gathers information based on a specified set of criteria. It organizes and presents the information in an easy-to-read format you can print or save as a file.  

The following table covers topis related to using built-in reports in [!INCLUDE[prod_short](includes/prod_short.md)].

| To  | See |
| --- | --- |
| Learn how to use with reports (bookmark, run, print, schedule, and change the layout). | [Use Reports in Daily Work](reports-use-reports.md) |
| Learn about which built-in reports are available in [!INCLUDE[prod_short](includes/prod_short.md)]. |[Report Overview](reports-available-reports.md)|


## External business intelligence and reporting tools

In case you prefer to use business intelligence tools that are not embedded in [!INCLUDE[prod_short](includes/prod_short.md)], the following table provides links to guidance on tools and methods to achieve this.

| To  | See |
| --- | --- |
| Use Power BI with Business Central | [Use Power BI with Business Central](admin-powerbi.md) |
| Integrate external business intelligence tools with [!INCLUDE[prod_short](includes/prod_short.md)].| [External Business Intelligence Tools](reports-external-analysis.md) |
| Extract data to data warehouses or data lakes| [Extract data to data warehouses or data lakes](/dynamics365/business-central/dev-itpro/performance/performance-developer#efficient-extracts-to-data-lakes-or-data-warehouses) |
| Analyze data with Microsoft Fabric| [Introduction to Microsoft Fabric and Business Central](admin-fabric.md) |
| Read data with the Business Central API | [Read data with the Business Central API](/dynamics365/business-central/dev-itpro/api-reference/v2.0/) |


## See also

[Using Financial reporting to produce financial statements and KPIs](bi.md)  
[Using key performance indicators (KPIs) to meet your business goals](analytics-about-kpis.md) 
[Doing ad-hoc data analysis](reports-adhoc-analysis.md)  
[Use reports in your daily work](reports-use-reports.md) 
[Overview of built-in reports](reports-available-reports.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
