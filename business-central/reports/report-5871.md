---
title: Item - Able to Make (Time) (report)
description: Check whether you can fulfill a sales order for an item by a specified date. Look at its current availability in combination with quantities that its components can supply if someone starts an assembly order. 
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_5871_Primary
ms.date: 10/23/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/28/2024
ai.usage: ai-assisted
---

# Item - Able to Make (Time) (report)

The **Item - Able to Make (Time)** report tracks the availability of bill of materials (BOM) items over time, based on five key figures that adjust according to supply and demand, and the availability of components for assembly or production.

Use this report to determine whether you can fulfill a sales order by a certain date. The report looks at your current inventory and the amount you can produce from available parts.

The data displays in a graph that shows the total quantity you can produce at any given time.

This report uses the same calculation engine as the **Item Availability by BOM Level** page to determine availability for BOM items.

## Use cases

[!INCLUDE[report-5871-scenario](../includes/report-5871-scenario-include.md)]

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
Item - Able to Make (Time)

## Report description
The *Item - Able to Make (Time)* report shows how five different key availability figures change over time for a Bill of Material (BOM) item. 
These figures change according to expected supply and demand events and to supply that is based on available components that can be assembled or produced.
The report shows you when and how many units of an assembly and production item you can make based on component availability and the item's current availability. This is shown as the total quantity.
The information is shown in a graph where each availability figure is a line that progresses along the timeline and moves up and down as quantities change. The quantity figures come from the same engine that provides information to the **Item Availability by BOM Level** window.

### What the report does
The *Item - Able to Make (Time)* report tracks the availability of Bill of Material (BOM) items over time, based on five key figures that adjust according to supply and demand, as well as the availability of components for assembly or production. 
Use this report to determine if a sales order can be fulfilled by a certain date. The report looks at your current inventory and the amount you can produce from available parts.
The data is displayed in a graph, showing the total quantity you can produce at any given time, based on these changing figures.
This report uses the same calculation engine as the **Item Availability by BOM Level Window** to determine the availability figures for BOM items.

### Use cases
Check whether you can fulfill a sales order for an item on a specified date by looking at its current availability in combination with the potential quantities that its components can supply if an assembly order were started. 

Please include your data sources and URLs

-->

## Try the report

Try the report here: [Item - Able to Make (Time)](https://businesscentral.dynamics.com?report=5871)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Assembly report overview](../assembly-reports.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]