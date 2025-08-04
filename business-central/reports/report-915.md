---
title: About Assemble to order - Sales (report)
description: Analyze the quantity, cost, sales, and profit figures of assembly components. Analyses can support decisions such as whether to price a kit differently, or to stop or start using a particular item in assemblies.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_915_Primary
ms.date: 10/23/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/28/2024
ai.usage: ai-assisted
---

# About Assemble to order - Sales (report)

The **About Assemble to order - Sales** report shows key sales figures for assembly component items that you sell both as parts of assemblies in assemble-to-order sales and as separate items directly from inventory.

The **In Assembly** row shows sales figures for the total quantity that is sold as part of an assembly item. The report shows the specific assembly item sales that sum up to this total if you select the **Show Assembly Details** field.

The focus is on the assembly components, but the figures are calculated from the profit margin of the assembly item. Accordingly, the sales amount of each component is calculated from its own cost and the profit margin of its parent.

The report shows information for items that meet one or both of the following criteria:

- They exist in the assembly BOM of an item that uses the assemble-to-order assembly policy.
- They were sold as part of an assemble-to-order sale.

## Use cases

[!INCLUDE[report-915-scenario](../includes/report-915-scenario-include.md)]

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
About Assemble to order - Sales

## Report description
The *About Assemble to order - Sales* report shows key sales figures for assembly component items that can be sold both as part of an assembly in assemble-to-order sales and as a separate item directly from inventory.
The **In Assembly** row shows sales figures for the total quantity that is sold as part of an assembly item. The specific assembly item sales that sum up to this total are shown if you select the **Show Assembly Details** field.
The focus is on the assembly components, but the figures are calculated from the profit margin of their parent, the assembly item. Accordingly, the sales amount of each component is calculated from its own cost and the profit margin of its parent in the following formula.
The report shows information for items that meet one or both of the following criteria:
- Exist in the assembly BOM of an item that uses the Assemble-to-Order assembly policy.
- Has been sold as part of assemble-to-order sale.

### What the report does

### Use cases
Analyze the quantity, cost, sales, and profit figures of assembly components to support your decisions, such as whether to price a kit differently or to stop or start using a particular item in assemblies.

Please include your data sources and URLs

-->

## Try the report

Try the report here: [About Assemble to order - Sales](https://businesscentral.dynamics.com?report=915)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Assembly report overview](../assembly-reports.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]