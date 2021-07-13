---
title: Assembly Reports and Analytics in Business Central
description: See which assembly reports and analytics are available in the standard version of Business Central so that you can keep track of your business.
author: AndreiPanko

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: reporting
ms.date: 06/01/2021
ms.author: andreipa

---
# Assembly Reports and Analytics in Business Central

Assembly reporting in [!INCLUDE [prod_short](includes/prod_short.md)] allows production and business professionals to get insights and statistics about current and past assembly activities.  

## Reports

The following table describes some of the key reports in assembly reporting.

|Report |Object ID|Description  |
|---------|---------|---------|
|**Assembly BOMs**|801|Displays a list of BOMs: name, BOM number, BOM components, and any other BOMs that are part of the BOM. The BOM components are defined in the BOM Component table. You will see here also the unit of measure and the needed quantity of each component per base unit of measure. |
|**Item – Able to Make (Time)**|5871|Shows how five different key availability figures change over time for a BOM item. These figures change according to expected supply and demand events and to supply that is based on available components that can be assembled or produced.<br>You can use the report to see whether you can fulfill a sales order for an item on a specified date by looking at its current availability in combination with the potential quantities that its components can supply if an assembly order were started. The report shows you when and how many units of an assembly and production item you can make based on component availability and the item’s current availability. This is shown as the total quantity.<br>The information is shown in a graph where each availability figure is a line that progresses along the timeline and moves up and down as quantities change. The quantity figures come from the same engine that provides information to the **Item Availability by BOM Level** window. |
|**BOM Cost Share Distribution**|5872|Shows graphically how an assembled or produced item’s cost is distributed through its BOM.<br>Such information can be useful in deciding whether to change component suppliers, replace internal capacity usage with outsourced labor, or vice versa, or when reviewing and modifying an item’s bill of material, for example.<br>The first chart in the report shows the total unit cost of the parent item’s components and labor resources broken down in up to five different cost shares, and represented graphically with different colors.<br>The pie chart with the caption *By Material/Labor* shows the proportional distribution between the parent item’s material and labor costs, as well as its own manufacturing overhead. The material cost share includes the item’s material costs. The labor cost share includes capacity, capacity overhead and subcontracted costs. The cost shares are displayed differently depending on your choices in the **Show only** field.<br>The pie chart with the caption *By Direct/Indirect* shows the proportional distribution between the parent item’s direct and indirect costs. The direct cost share includes the item’s material, capacity, and subcontracted costs. The indirect cost share includes capacity overhead and manufacturing overhead.<br>The table at the bottom of the report is included when you select the Include Details check box. It shows selected values from the BOM Cost Shares window by single level or rolled up, depending on the option that you choose in the Show Cost Shares as field.|
|**Where-used list**|809|Displays a list of the BOMs that the selected items are components of. A helpful overview in case you must change a component in a BOM that is inserted in an assembly item. For example, if your vendor can no longer deliver a specific item that you used for your assembly/production. In such scenarios, this report provides you with an easy overview of which BOMs the component is included in. You can set a filter for the number of the component.|
|**BOM – Raw Materials**|810|This report can give you an overview about the needed components, both for assembly and for production. You will see the inventory, base unit of measure, the main vendor if the vendor no. is written in the item card itself, and the lead time calculation.|
|**BOM – Sub-Assemblies**|811|If you produce and/or assemble sub-assemblies, use this report to get an overview about this type of component. This report shows you the base unit of measure, the inventory, unit costs, and an alternative item number. |
|**Assembly BOM - End Items**|812|Shows a list of items or BOMs that are not components of BOMs. **Note**: This report is not restricted to BOM only, so remember to set filter in the **Assembly BOM** field or the **Replenishment System** fields|
|**Assemble to order – Sales**|915|Shows key sales figures for assembly component items that can be sold both as part of an assembly in assemble-to-order sales and as a separate item directly from inventory.<br>Use this report to analyze the quantity, cost, sales, and profit figures of assembly components to support your decisions, such as whether to price a kit differently or to stop or start using a particular item in assemblies.<br>The **In Assembly** row shows sales figures for the total quantity that is sold as part of an assembly item. The specific assembly item sales that sum up to this total are shown if you select the **Show Assembly Details** field.<br>The focus is on the assembly components, but the figures are calculated from the profit margin of their parent, the assembly item. Accordingly, the sales amount of each component is calculated from its own cost and the profit margin of its parent in the following formula.<br>The report shows information for items that meet one or both of the following criteria:<br>- Exist in the assembly BOM of an item that uses the Assemble-to-Order assembly policy.<br>- Has been sold as part of assemble-to-order sale.|

## Tasks

The following articles describe some of the key tasks for analyzing the state of your business:

* [View the Availability of Items](inventory-how-availability-overview.md)

## See also

[Assembly Management](assembly-assemble-items.md)  
[Work with Bills of Material](inventory-how-work-boms.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
