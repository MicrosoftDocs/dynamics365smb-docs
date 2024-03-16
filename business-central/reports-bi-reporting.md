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

## Using Financial reporting to produce financial statements and KPIs

The *Financial reporting* feature gives you insight into the financial data stored in your chart of accounts (COA). You can setup financial reports to analyze figures in general ledger (G/L) accounts, and compare general ledger entries with budget entries. The results display in charts and reports in your Role Center, such as the cash flow chart and income statement and balance sheet reports.

For more info, see...


## What is a KPI and why should I care?
A key performance indicator (KPI) is a measurable value that shows how effectively you’re meeting your goals. Think of KPIs as your company’s scorecard, a way of measuring whether or not you’re delivering on your objectives.

Identifying and tracking KPIs lets you know if your business is on the right path—or if you should change course to avoid losing valuable time and money. When used properly, KPIs are powerful tools that help you:

- Monitor company financial health.
- Measure progress against strategic goals.
- Spot problems early on.
- Make timely adjustments to tactics.
- Motivate team members.
- Make better decisions, faster.

For more info, see...


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

## Built-in reports

A report in [!INCLUDE[prod_short](includes/prod_short.md)] gathers information based on a specified set of criteria. It organizes and presents the information in an easy-to-read format you can print or save as a file.  

More text here and some references.

| Work with standard reports (bookmark, run, print, schedule, and change the layout). | [Use Reports in Daily Work](reports-use-reports.md) |


## Key business intelligence and reporting functionality

The following table covers key business intelligence and reporting functionality in [!INCLUDE[prod_short](includes/prod_short.md)] you can learn to use.

| To | See |
| --- | --- |
| Work with standard reports (bookmark, run, print, schedule, and change the layout). | [Use Reports in Daily Work](reports-use-reports.md) |
| Learn about built-in reports in [!INCLUDE[prod_short](includes/prod_short.md)]. |[Report Overview](reports-available-reports.md)|
| Do ad-hoc data analysis using in-client features or Microsoft Excel. | [Ad-hoc Data Analysis](reports-adhoc-analysis.md) |
| Work with built-in analytics tools in [!INCLUDE[prod_short](includes/prod_short.md)].| [Built-in Analytics](reports-built-in-analytics.md) |
| Integrate external business intelligence tools with [!INCLUDE[prod_short](includes/prod_short.md)].| [External Business Intelligence Tools](reports-external-analysis.md) |
|Modify report layouts or even develop your own reports from scratch. |[Developing reports](reports-develop-reports.md)|
|Analyze data with Microsoft Fabric| [Introduction to Microsoft Fabric and Business Central](admin-fabric.md) |


## See also

[Financial Business Intelligence](bi.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
