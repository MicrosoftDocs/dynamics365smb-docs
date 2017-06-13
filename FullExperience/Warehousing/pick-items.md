---
title: "Pick Items"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "items, picking"
  - "outbound warehouse, picking"
ms.assetid: 1b1a11f4-29b6-4fd1-aa92-61f5d4e036b1
caps.latest.revision: 6
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# Pick Items
The warehouse activity of picking items before they are shipped or consumed is performed in different ways, depending on how warehouse management features are configured. The [setup](../WarehouseActivities/configure-warehouse-processes.md) complexity can rank from no warehouse features, through basic warehousing for order\-by\-order handling in one or more activities only, to advanced configurations where all warehouse activities must be performed in a directed workflow.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Get an overview of the different ways to pick items depending on the complexity of the warehouse configuration.|[Picking Items](../WarehouseActivities/picking-items.md)|  
|Print a list of the items to pick for one or more orders.|[Picking List](../WarehouseActivities/-$-r_5752-picking-list-$-.md)|  
|Post the shipment of items directly in the outbound order document because no warehouse features exist. \(Works the same for sales, transfer, and production orders.\)|"Posting Sales orders" in [Processing Sales Orders](../Sales/processing-sales-orders.md)|  
|Pick items order by order and post the shipment in the same activity, in a basic warehouse configuration.|[How to: Pick Items with Inventory Picks](../DesignAndEngineering/how-to-pick-items-with-inventory-picks.md)|  
|Pick components for production at a location with basic warehouse configuration.|[How to: Pick for Production in Basic Warehousing](../WarehouseActivities/how-to-pick-for-production-in-basic-warehousing.md)|  
|Pick components for production at a location with advanced warehousing configuration.|[How to: Pick for Internal Operations in Advanced Warehousing](../WarehouseActivities/how-to-pick-for-internal-operations-in-advanced-warehousing.md)|  
|Pick items for multiple orders in an advanced warehouse configuration.|[How to: Pick Items for Warehouse Shipment](../WarehouseActivities/how-to-pick-items-for-warehouse-shipment.md)|  
|Pick components for production in an advanced warehouse configuration.|"Pick Components with the Pick Worksheet" in [Picking for Production](../WarehouseActivities/how-to-pick-for-production-in-basic-warehousing.md)|  
|Get immediate access to picks assigned to you as a warehouse worker.|[How to: Find Your Warehouse Assignments](../WarehouseActivities/how-to-find-your-warehouse-assignments.md)|  
|Plan optimized pick instructions for a number of shipments rather than have warehouse workers act directly on posted shipments.|[How to: Plan Picks in Worksheets](../WarehouseActivities/how-to-plan-picks-in-worksheets.md)|  
|Pick items technically for a special purpose, such as a production unit in need of extra components, in such a way that the items do not technically leave the warehouse.|"Create a Pick from the Internal Pick" in [Picking and Putting Away Without a Source Document](../WarehouseActivities/how-to-create-put-aways-from-internal-put-aways.md)|  
|Break a larger unit of measure into smaller units of measure when creating warehouse instructions.|"Breakbulk in Picks" in [Automatic Break Bulk for Directed Put\-away and Pick](../WarehouseActivities/automatic-breaking-bulk-with-directed-put-away-and-pick.md)|  
|Record which serial\/lot numbers are picked as items leave inventory to enable tracking of the items after they are sold.|[How to: Assign Serial Numbers and Lot Numbers During Outbound Transactions](../WarehouseActivities/how-to-assign-serial-numbers-and-lot-numbers-during-outbound-transactions.md)|  
|Pick serial\/lot numbers specified by the source sales order because, for example, the customer has requested a specific lot.|[About Picking Serial and Lot Numbers](../WarehouseActivities/about-picking-serial-and-lot-numbers.md)|  
|Split a put\-away line to place part of the put\-away quantity in available bins because the designated bin is full.|[How to: Split Warehouse Activity Lines](../WarehouseActivities/how-to-split-warehouse-activity-lines.md)|  
  
## See Also  
 [Shipping](../Topic/Shipping.md)   
 [Sales](../Sales/sales.md)   
 [Production](../Production/production.md)   
 [Design and Engineering](../DesignAndEngineering/design-and-engineering.md)