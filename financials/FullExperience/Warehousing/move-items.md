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
# Move Items
While in inventory, items may need to be moved between bins to support the daily warehouse activities involved in keeping items flowing through the warehouse. Some movements happen in direct relation to internal operations, such as a production order that needs components delivered or end items put away. Other movements happen as mere warehouse space optimization or as ad-hoc movements to and from operations.  
  
 Moving items inside a location is less complicated because their inventory levels, represented by item ledger entries, do not change. Moving items to other locations, on the other hand, affects the item ledger entries and must therefore be done by transfer order. This is described in [Shipping](../Topic/Shipping.md).  
  
 Additional movement tasks are to periodically replenish picking bins or shop floor bins and to modify bin content information.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Plan which bins to fill or empty to maintain an efficient flow, such as emptying a bulk storage area before a large receipt.|[How to: Plan Warehouse Movements in Worksheets](../WarehouseActivities/how-to-plan-warehouse-movements-in-worksheets.md)|  
|Use the warehouse movement worksheet to move items in advanced warehouse configurations, both for source documents and ad hoc.|[How to: Move Items in Advanced Warehousing](../WarehouseActivities/how-to-move-items-in-advanced-warehousing.md)|  
|Record a movement between bins in advanced warehouse configurations after the movement has been completed.|[How to: Register Already Completed Warehouse Movements](../WarehouseActivities/how-to-register-already-completed-warehouse-movements.md)|  
|Update the frequency at which bins, such as picking bins, must be replenished as a result of demand fluctuations.|[How to: Calculate Bin Replenishment](../WarehouseActivities/how-to-calculate-bin-replenishment.md)|  
|Bring component items to internal operations in basic warehouse configurations as requested by source documents for those operations.|[How to: Move Components to an Operation Area in Basic Warehousing](../WarehouseActivities/how-to-move-components-to-an-operation-area-in-basic-warehousing.md)|  
|Move items between bins in basic warehouse configurations at any time and without source documents.|[How to: Move Items Ad Hoc in Basic Warehousing](../WarehouseActivities/how-to-move-items-ad-hoc-in-basic-warehousing.md)|  
  
## See Also  
 [Design and Engineering](../DesignAndEngineering/design-and-engineering.md)   
 [Perform Warehouse Activities](../WarehouseActivities/perform-warehouse-activities.md)   
 [Shipping](../Topic/Shipping.md)