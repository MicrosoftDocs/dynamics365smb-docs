---
title: Maintenance - Next Service (report)
description: Review the next service dates recorded on fixed asset cards, filter by a service date range, and identify active assets due for maintenance.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_5635_Primary
ms.date: 11/13/2026
ms.service: dynamics-365-business-central
ms.custom:
  - ai-gen-docs-bap
ai-seo-date: 10/23/2024
ai-usage: ai-assisted
---

# Maintenance - Next Service (report)

The **Maintenance - Next Service** report shows the next date on which service and repairs are planned for each asset.

For each asset, the report gets this date from the **Next Service Date** field on the **Fixed Asset Card** page.

You can define a period for the assets to include in the report.

- **Starting Date** excludes assets with an earlier next service date.
- **Ending Date** excludes assets with a later next service date.

Inactive assets, budgeted assets, and assets without a next service date are excluded. The report reads the date on the asset card; it doesn't calculate a maintenance schedule.

## Use cases

[!INCLUDE[report-5635-scenario](../includes/report-5635-scenario-include.md)]

<!-- 

Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with fixed asset management or finance for fixed assets.

Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

Do not start lines with "Use the data to"

## Report name
Maintenance - Next Service

## Report description

### What the report does

### Use cases

Please include your data sources and URLs

-->

## Try the report

Try the report here: [Maintenance - Next Service](https://businesscentral.dynamics.com?report=5635)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Fixed assets report overview](../fa-reports.md)  
[Ad hoc analysis of fixed assets data](../ad-hoc-analysis-fa.md)  
[Fixed assets analytics overview](../fa-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]