---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Design Details: Average Cost
The average cost of an item is calculated with a periodic weighted average, based on the average cost period that is set up in [!INCLUDE[d365fin](includes/d365fin_md.md)].  
  
 The valuation date is set automatically.  
  
## Setting Up Average Cost Calculation  
 The following table describes the two fields in the **Inventory Setup** window that must be filled to enable average cost calculation.  
  
|ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
|---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

-----------------------------------------|--------------------------------|------------------------------------------------|----------------------------------|  
|01-01-20|1|10.00|1|  
|01-02-20|1|20.00|2|  
|02-15-20|-1|-15.00|3|  
|02-16-20|-1|-15.00|4|  
  
 The user posts an inventory increase \(entry number 5\) with a valuation date \(01-03-20\) that comes before one or more inventory decreases. To balance the inventory, the average cost must be recalculated and adjusted to 17.00.  
  
 The following table shows the value entries that exist for the item after entry number 5 is introduced.  
  
|Valuation Date|Quantity|Cost Amount \(Actual\)|Entry No.|  
|-----------------------------------------|--------------------------------|------------------------------------------------|----------------------------------|  
|01-01-20|1|10.00|1|  
|01-02-20|1|20.00|2|  
|01-03-20|1|21.00|5|  
|02-15-20|-1|-17.00|3|  
|02-16-20|-1|-17.00|4|  
  
## See Also  
 [Design Details: Inventory Costing](design-details-inventory-costing.md)   
 [Design Details: Costing Methods](design-details-costing-methods.md)   
 [Design Details: Cost Adjustment](design-details-cost-adjustment.md)   
 [Design Details: Item Application](design-details-item-application.md)