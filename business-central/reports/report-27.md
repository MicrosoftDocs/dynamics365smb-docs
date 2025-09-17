---
title: Dimensions - Total (report)
description: Analyze your general ledger with dimension totals by building groups of dimensions for combinations of dimension values, and calculate a general ledger balance total for each segment.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_27_Primary
ms.date: 10/18/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/18/2024
ai.usage: ai-assisted
---

# Dimensions - Total (report)

The **Dimensions - Total** report shows calculated general ledger (G/L) balance totals for the dimension levels you specify for a given period.

You specify dimension levels by selecting an analysis view configured with dimension codes, and then creating a hierarchy of dimension groups by arranging them under one another.

You can select an Analysis View with a column layout that includes budget figures. This view shows general ledger actuals vs. budgets for each dimension level.

You can also select an Analysis View with a cash flow account source. This view shows cash flow actuals vs. forecasts for each dimension level.

## Use cases

[!INCLUDE [report-27-scenario](../includes/report-27-scenario-include.md)]

<!-- 
Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with core finance.
Format like this:    
  
As a <persona>, can use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 
Do not start lines with ""Use the data to""


## Report name
Dimensions - Total 

### What the report does
Shows calculated GL balance totals for dimension levels specified by the user, for a given date period.

Dimension levels are specified by selecting an analysis view configured with dimension codes, then picking a hierarchy of how the dimension groups are grouped under one another.

You can select an Analysis View with a column layout that includes budget figures. This will show GL actuals vs budget for each dimension level. 

You can select an Analysis View with a cash flow account source. This will show cash flow actuals vs forecast for each dimension level.

### Use cases
Analyse your general ledger with dimension totals by building a grouping of dimensions for each permutation of dimension values and calculate a GL balance total for each segment.
This report helps businesses analyze and summarize data by categorizing entries with dimensions such as department, project, or location, providing a clear view of totals for better decision-making.

Please include your data sources and URLs
-->

Financial analysts can use the report to:

* Analyze financial performance by reviewing the general ledger balance totals for different dimensions, such as department, project, or location.
* Identify areas to save cost or generate revenue, and make recommendations for improving financial performance.
* Use the report data to prepare financial reports for stakeholders such as investors or executives.

Financial accountants can use the report to:

* Use the report data to prepare financial statements, such as income statements, balance sheets, and cash flow statements.
* Verify the accuracy of the financial data by ensuring that the general ledger balance totals for different dimensions are correct and balance.
* Identify discrepancies or errors in financial data and investigate them.

Financial controllers can use the report to:

* Monitor the financial health of the business by reviewing the general ledger balance totals for different dimensions, such as department, project, or location.
* Identify areas to save cost or generate revenue, and make recommendations for improving financial performance.
* Use the report data to prepare financial reports for internal and external stakeholders such as board members or regulatory agencies.

## Try the report

Try the report here: [Dimensions - Total](https://businesscentral.dynamics.com?report=27)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Built-in key finance reports](../finance-reports.md)  
[Ad hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]