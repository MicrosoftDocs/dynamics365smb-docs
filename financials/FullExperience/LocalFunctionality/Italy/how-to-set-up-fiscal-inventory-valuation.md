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
# How to: Set Up Fiscal Inventory Valuation
To use fiscal inventory valuation, you must set up inventory valuation methods.  
  
### To set up fiscal inventory valuation for item costing  
  
1.  In the **Search** box, enter **Item Costing Setup**, and then choose the related link.  
  
2.  On the **General** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Components Valuation**|Specify the fiscal inventory valuation method.|  
    |**Estimated WIP Consumption**|Select to include the finished production orders or the released production orders for the cost calculation.<br /><br /> If this field is cleared, then consumption and capacity ledger entries are filtered by posting date.|  
  
3.  Choose the **OK** button.  
  
### To set up fiscal inventory valuation for an item  
  
1.  In the **Search** box, enter **Items**, and then choose the related link.  
  
2.  In the **Item List** window select each item, and then, on the **General** FastTab, in the **Inventory Valuation** field, specify the inventory valuation type.  
  
3.  Choose the **OK** button.  
  
## See Also  
 [Fiscal Inventory Valuation](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/fiscal-inventory-valuation.md)   
 Item Costing Setup   
 Item Card   
 Item