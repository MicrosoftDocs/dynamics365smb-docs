---
title: Analytics, business intelligence, and reporting overview
description: Provides an overview of all the analytics, business intelligence, and reporting features supported in Business Central.
author: KennieNP
ms.topic: get-started
ms.devlang: al
ms.search.keywords: feature overview
ms.reviewer: bholtorf
ms.search.form: 36984, 36985, 36986, 36987, 36988, 36989, 36990, 36991, 36992, 36993, 36994, 36995, 36996, 36997, 36998, 36999, 37000, 37001, 37002, 37003, 37004, 37005, 37006, 37007, 37008, 37009, 37010, 37011, 37012, 37013, 37014, 37015, 37016, 37017, 37018, 37019, 37020, 37021, 37022, 37023, 37024, 37025, 37026, 37027, 37028, 37029, 37030, 37031, 37032, 37033, 37034, 37035, 37036, 37037, 37038, 37039, 37040, 37041, 37042, 37043, 37044, 37045, 37046, 37047, 37048, 37049, 37055, 37056, 37057, 37058
ms.date: 11/13/2024
ms.author: kepontop
ms.service: dynamics-365-business-central
---

# Analytics, business intelligence, and reporting overview

Small and mid-sized companies rely on built-in analytics and reporting capabilities they can use out-of-the-box to help keep track of their business. [!INCLUDE[prod_short](includes/prod_short.md)] provides reports and analytics tools that cover basic and complex business processes.

## Analytics needs in organizations

When you think about analytics in your organization, it might help to use a persona-based model to outline different needs.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg" alt-text="Illustration of different personas for analytics" lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg":::

The model is based on the fact that different roles in an organization have different needs when it comes to data. The higher a role is placed in the organizational chart, the more aggregated data someone in the role needs to do their work.

Roles often have preferred ways to consume and analyze data, ways that reflect the level of data aggregation they need.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg" alt-text="Illustration of how different personas have different analytics needs." lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg":::

Use the following sections to learn more about ways to consume data from [!INCLUDE[prod_short](includes/prod_short.md)]:

- Financial Reports
- KPIs and dashboards
- Power BI apps
- Ad-hoc analysis
- Reports

## Using Financial Reports to produce financial statements and KPIs

The Financial Reports feature gives you insight into the financial data stored in your chart of accounts (COA). You can set up financial reports to analyze figures in general ledger (G/L) accounts, and compare general ledger entries with budget entries.

:::image type="content" source="media/acc_schedule_13_columns.jpg" alt-text="Screenshot of a financial report." lightbox="media/acc_schedule_13_columns.jpg":::

Dimensions play an important role in business intelligence. A dimension is data that you can add to an entry as a parameter. Dimensions let you group entries that have similar characteristics. For example, groups of customers, regions, products, and salesperson. Groups make it easier to retrieve data for analysis. Among other purposes, you use dimensions when you define analysis views and create financial reports. Learn more at [Work with Dimensions](finance-dimensions.md).

To learn more about financial statements and KPIs, go to [Using Financial reporting to produce financial statements and KPIs](bi.md).

## Using key performance indicators to meet your business goals

A key performance indicator (KPI) is a measurable value that shows how effectively you’re meeting your goals. Think of KPIs as your company’s scorecard, a way to measure whether you’re delivering on your objectives.

Identifying and tracking KPIs lets you know whether your business is on the right path, or whether you should change course. When used properly, KPIs are powerful tools that help you:

- Monitor company financial health.
- Measure progress against strategic goals.
- Spot problems early on.
- Make timely adjustments to tactics.
- Motivate team members.
- Make better decisions, faster.

To learn more about KPIs, go to [Using key performance indicators to meet your business goals](./analytics-about-kpis.md)

## Built-in Power BI apps 

[!INCLUDE [powerbi-apps-overview](includes/powerbi-apps-overview.md)]

:::image type="content" source="media/finance/financial-overview.png" alt-text="Screenshot of the Finance Overview report" lightbox="media/finance/financial-overview.png":::

To learn more, go to [Power BI apps/reports by functional area](across-powerbi-apps-by-functional-area.md)

## Ad-hoc data analysis

You might just want to check whether the numbers add up correctly, quickly confirm or debunk a hypothesis about the business, or maybe look for anomalies in your financial data. For ad-hoc analyses, you might not have a built-in report that helps answer your questions. For ad-hoc analyses, use these two features:

- Data analysis on ledger list pages
- Open in Excel

The Data analysis feature lets you open almost any list page, such as the General Ledger Entries or Customer Ledger Entries pages, enter analysis mode, and then group, filter, and pivot data as you see fit. 

:::image type="content" source="media/data-analysis-gl-entries.png" alt-text="Example of how to do data analysis on the G/L entries page." lightbox="media/data-analysis-gl-entries.png":::

Similarly, you can use the **Open in Excel** action to open a list page, optionally filter the list to a subset of the data, and then use Excel to work with the data. For example, by using features such as Analyze Data, What-If Analysis, or Forecast Sheet.

:::image type="content" source="media/open-in-excel-gl-entries.png" alt-text="Example of how to do data analysis on the G/L entries data using Excel." lightbox="media/open-in-excel-gl-entries.png":::

[!INCLUDE [onedrive-excel-online](includes/onedrive-excel-online.md)]

To learn more about ad-how analyses, go to [Ad hoc data analysis](reports-adhoc-analysis.md).

## Reports

A report in [!INCLUDE[prod_short](includes/prod_short.md)] gathers information based on a specified set of criteria. Reports organize and present the information in an easy-to-read format you can use in Excel, print, or save as a file.  

As an example of an interactive report in Excel, the **Aged Accounts Receivable** report lets you analyze what your customers owe you and when payments are due.

:::image type="content" source="media/aged-accounts-receivables-excel.png" alt-text="Example of the interactive aged accounts receivables report in Excel." lightbox="media/aged-accounts-receivables-excel.png":::

For aged accounts receivables, [!INCLUDE[prod_short](includes/prod_short.md)] also includes a report designed for print. The ability to print is handy if you prefer to have the data in a .pdf file.

:::image type="content" source="media/aged-accounts-receivables-pdf.png" alt-text="Example of the  aged accounts receivables report in pdf." lightbox="media/aged-accounts-receivables-pdf.png":::

[!INCLUDE[prod_short](includes/prod_short.md)] comes with more than 300 built-in reports that you can use to support your business processes with data-driven insights. To get a quick overview of all the reports that are available for your role, you can open the report explorer from the role center and all list pages and from **Tell Me**.

:::image type="content" source="media/report-explorer-finance.png" alt-text="Example of how the report explorer shows all reports for a role." lightbox="media/report-explorer-finance.png":::

To learn more about using the report explorer to see all built-in reports, go to [Exploring reports per Role](ui-role-explorer.md).

The following table lists articles about how to use built-in reports in [!INCLUDE[prod_short](includes/prod_short.md)].

| To  | See |
| --- | --- |
| Learn how to use reports (bookmark, run, print, schedule, and change the layout). | [Use Reports in Daily Work](reports-use-reports.md) |
| Learn about which built-in reports are available in [!INCLUDE[prod_short](includes/prod_short.md)]. |[Report Overview](reports-available-reports.md)| 
| Use the Report Explorer to see all built-in reports. | [Exploring reports per Role](ui-role-explorer.md) |

## External business intelligence and reporting tools

If you prefer, you can use business intelligence tools that aren't embedded in [!INCLUDE[prod_short](includes/prod_short.md)]. The following table provides links to guidance and ways to use external tools.

| To  | See |
| --- | --- |
| Use Power BI with Business Central data | [Using Power BI with Business Central](admin-powerbi.md) |
| Integrate external business intelligence tools with [!INCLUDE[prod_short](includes/prod_short.md)].| [External Business Intelligence Tools](reports-external-analysis.md) |
| Extract data to data warehouses or data lakes| [How to extract data to data warehouses or data lakes](/dynamics365/business-central/dev-itpro/performance/performance-developer#efficient-extracts-to-data-lakes-or-data-warehouses) |
| Analyze Business Central data with Microsoft Fabric| [Introduction to Microsoft Fabric and Business Central](admin-fabric.md) |
| Read data from Business Central using APIs | [Business Central API v2.0](/dynamics365/business-central/dev-itpro/api-reference/v2.0/) |

## Analytics by functional area

The content in this general article is also available in special versions for many functional areas in [!INCLUDE[prod_short](includes/prod_short.md)].

[!INCLUDE [analytics-by-functional-areas-overview-table](includes/analytics-by-functional-areas-overview-table.md)]

## Related information

[Using Financial reporting to produce financial statements and KPIs](bi.md)  
[Using key performance indicators (KPIs) to meet your business goals](analytics-about-kpis.md)  
[Power BI apps/reports by functional area](across-powerbi-apps-by-functional-area.md)  
[Doing ad-hoc data analysis](reports-adhoc-analysis.md)  
[Use reports in your daily work](reports-use-reports.md)  
[Overview of built-in reports](reports-available-reports.md)  
[Exploring reports per Role](ui-role-explorer.md)  
[Analytics by functional area](analytics-by-functional-area.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
