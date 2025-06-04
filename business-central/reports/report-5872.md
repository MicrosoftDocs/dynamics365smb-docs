---
title: BOM Cost Share Distribution (report)
description: This report helps you decide whether to change component suppliers, or replace internal resources with outsourced labor (or vice versa). It also helps you review and modify an item's bill of materials.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_5872_Primary
ms.date: 10/23/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/28/2024
ai.usage: ai-assisted
---

# BOM Cost Share Distribution (report)

The **BOM Cost Share Distribution** report illustrates how an assembled or produced item's cost is distributed through its bill of materials (BOM).

The first chart in the report shows the total unit cost of the parent item's components and labor resources in up to five different cost shares. The cost share amounts display in different colors.

The pie chart with the caption **By Material/Labor** shows the proportional distribution between the parent item's material and labor costs, and its manufacturing overhead. The material cost share includes the item's material costs. The labor cost share includes capacity, capacity overhead, and subcontracted costs. The cost shares display differently depending on your choices in the **Show only** field.

The pie chart with the caption **By Direct/Indirect** shows the proportional distribution between the parent item's direct and indirect costs. The direct cost share includes the item's material, capacity, and subcontracted costs. The indirect cost share includes capacity and manufacturing overhead.

If you select the **Include Details** checkbox, the bottom of the report includes a table that shows selected values from the BOM Cost Shares page by a single level or rolled up, depending on the option that you choose in the **Show Cost Shares as** field.

## Use cases

[!INCLUDE[report-5872-scenario](../includes/report-5872-scenario-include.md)]

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
BOM Cost Share Distribution

## Report description
The *BOM Cost Share Distribution* report shows graphically how an assembled or produced item's cost is distributed through its bill of material (BOM).
The first chart in the report shows the total unit cost of the parent item's components and labor resources broken down in up to five different cost shares, and represented graphically with different colors.
The pie chart with the caption *By Material/Labor* shows the proportional distribution between the parent item's material and labor costs, as well as its own manufacturing overhead. The material cost share includes the item's material costs. The labor cost share includes capacity, capacity overhead and subcontracted costs. The cost shares are displayed differently depending on your choices in the **Show only** field.
The pie chart with the caption *By Direct/Indirect* shows the proportional distribution between the parent item's direct and indirect costs. The direct cost share includes the item's material, capacity, and subcontracted costs. The indirect cost share includes capacity overhead and manufacturing overhead.
The table at the bottom of the report is included when you select the Include Details check box. It shows selected values from the BOM Cost Shares window by single level or rolled up, depending on the option that you choose in the Show Cost Shares as field.

### What the report does

### Use cases
Help decide whether to change component suppliers, replace internal capacity usage with outsourced labor, or vice versa, or when reviewing and modifying an item's bill of material (BOM).

Please include your data sources and URLs

-->

## Try the report

Try the report here: [BOM Cost Share Distribution](https://businesscentral.dynamics.com?report=5872)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Assembly report overview](../assembly-reports.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]