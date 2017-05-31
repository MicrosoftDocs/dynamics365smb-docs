---
title: "Put Items Away"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "items, putting away"
  - "inbound warehouse, putting away"
  - "warehouse, putting items away"
  - "putting away, about"
ms.assetid: e5fff20b-cc3d-4f20-bbdf-ded9a40044ab
caps.latest.revision: 4
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
# Put Items Away
The warehouse activity of putting items away after they are received or output is performed in different ways depending on how warehouse management features are configured. The [setup](../WarehouseActivities/configure-warehouse-processes.md) complexity can rank from no warehouse features, through basic warehousing for order\-by order handling in one or more activities only, to advanced configurations where all warehouse activities must be performed in a directed workflow.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Get an overview of the different ways to put items away depending on the complexity of the warehouse configuration.|[Putting Items Away](../WarehouseActivities/putting-items-away.md)|  
|Print a list of the items to put away for one or more orders.|[\($ R\_5751 Put\-away List $\)](../WarehouseActivities/-$-r_5751-put-away-list-$-.md)|  
|Post the receipt of items directly in the inbound order document because no warehouse features exist. \(Works the same for purchase, transfer, and production orders.\)|"Posting Purchase Orders" in [Processing Purchase Orders](../Receiving/processing-purchase-orders.md)|  
|Put items away order by order and post the receipt in the same activity, in a basic warehouse configuration.|[How to: Put Items Away with Inventory Put\-aways](../DesignAndEngineering/how-to-put-items-away-with-inventory-put-aways.md)|  
|Put produced items away in a basic warehouse configuration.|"Put Away Output from the Inventory Put\-away Document" in [Putting Away Production Output](../Production/how-to-put-away-production-output.md)|  
|Put items away for multiple orders in an advanced warehouse configuration.|[How to: Put Items Away with Warehouse Put\-aways](../WarehouseActivities/how-to-put-items-away-with-warehouse-put-aways.md)|  
|Put produced items away in an advanced warehouse configuration.|"Put Away Output with Internal Put\-away or Movement" in [Putting Away Production Output](../Production/how-to-put-away-production-output.md)|  
|Get immediate access to put\-aways assigned to you as a warehouse worker.|[How to: Find Your Warehouse Assignments](../WarehouseActivities/how-to-find-your-warehouse-assignments.md)|  
|Plan optimized put\-away instructions for a number of posted warehouse receipts rather than have warehouse workers act directly on receipts.|[How to: Plan Put\-aways in Worksheets](../WarehouseActivities/how-to-plan-put-aways-in-worksheets.md)|  
|Put back items that were picked technically with an internal pick, for example for a production order that did not consume the expected quantity.|"Create a Put\-away from the Internal Put\-away" in [Picking and Putting Away Without a Source Document](../WarehouseActivities/how-to-create-put-aways-from-internal-put-aways.md)|  
|Create or recreate deleted put\-away lines on the basis of posted warehouse receipts lines, in an advanced warehouse configuration.|[How to: Create Put\-aways from Posted Receipts](../WarehouseActivities/how-to-create-put-aways-from-posted-receipts.md)|  
|Break a larger unit of measure into smaller units of measure when creating warehouse instructions.|"Breakbulk in Put\-aways" in [Automatic Break Bulk for Directed Put\-away and Pick](../WarehouseActivities/automatic-breaking-bulk-with-directed-put-away-and-pick.md)|  
|Assign new serial\/lot numbers to items as they enter inventory to enable tracking of the items after they are sold and while they are in inventory.|[How to: Assign Serial Numbers and Lot Numbers During Inbound Transactions](../WarehouseActivities/how-to-assign-serial-numbers-and-lot-numbers-during-inbound-transactions.md)|  
|Split a put\-away line to place part of the put\-away quantity in available bins because the designated bin is filled up.|[How to: Split Warehouse Activity Lines](../WarehouseActivities/how-to-split-warehouse-activity-lines.md)|  
  
## See Also  
 [Receiving](../Receiving/receiving.md)   
 [Purchasing](../Purchasing/purchasing.md)   
 [Production](../Production/production.md)   
 [Design and Engineering](../DesignAndEngineering/design-and-engineering.md)