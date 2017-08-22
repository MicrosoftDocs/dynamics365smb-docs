---
    title: Move Items | Microsoft Docs
    description: While in inventory, items may need to be moved between bins to support the daily warehouse activities involved in keeping items flowing through the warehouse. Some movements happen in direct relation to internal operations, such as a production order that needs components delivered or end items put away. Other movements happen as mere warehouse space optimization or as ad-hoc movements to and from operations.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 08/22/2017
    ms.author: sgroespe

---
# Moving Items
While in inventory, items may need to be moved between bins to support the daily warehouse activities involved in keeping items flowing through the warehouse. Some movements happen in direct relation to internal operations, such as a production order that needs components delivered or end items put away. Other movements happen as mere warehouse space optimization or as ad-hoc movements to and from operations.  

 Moving items inside a location is less complicated because their inventory levels, represented by item ledger entries, do not change. Moving items to other locations, on the other hand, affects the item ledger entries and must therefore be done by transfer order. For more information, see [How to: Ship Items](warehouse-how-ship-items.md).  

 Additional movement tasks are to periodically replenish picking bins or shop floor bins and to modify bin content information.  

 The following table describes a sequence of tasks, with links to the topics that describe them.   

|**To**|**See**|  
|------------|-------------|  
|Plan which bins to fill or empty to maintain an efficient flow, such as emptying a bulk storage area before a large receipt.|[How to: Plan Warehouse Movements in Worksheets](warehouse-how-to-plan-warehouse-movements-in-worksheets.md)|  
|Use the warehouse movement worksheet to move items in advanced warehouse configurations, both for source documents and ad hoc.|[How to: Move Items in Advanced Warehouse Configurations](warehouse-how-to-move-items-in-advanced-warehousing.md)|  
|Record a movement between bins in advanced warehouse configurations after the movement has been completed.|[How to: Register Already Completed Warehouse Movements](warehouse-how-to-register-already-completed-warehouse-movements.md)|  
|Bring component items to internal operations in basic warehouse configurations as requested by source documents for those operations.|[How to: Move Components to an Operation Area in Basic Warehouse Configurations](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md)|  
|Move items between bins in basic warehouse configurations at any time and without source documents.|[How to: Move Items Ad Hoc in Basic Warehouse Configurations](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md)|
|Update the frequency at which bins, such as picking bins, must be replenished as a result of demand fluctuations.|[How to: Calculate Bin Replenishment](warehouse-how-to-calculate-bin-replenishment.md)|
|Restructure your warehouse with new bin codes and new bin characteristics and potentially move them around.|[How to: Restructure Warehouses](warehouse-how-to-restructure-warehouses.md)|  

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
