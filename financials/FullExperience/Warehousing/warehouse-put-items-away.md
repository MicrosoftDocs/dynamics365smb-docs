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
# Put Items Away
The warehouse activity of putting items away after they are received or output is performed in different ways depending on how warehouse management features are configured. The [setup](../configure-warehouse-processes.md) complexity can rank from no warehouse features, through basic warehousing for order-by order handling in one or more activities only, to advanced configurations where all warehouse activities must be performed in a directed workflow.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Get an overview of the different ways to put items away depending on the complexity of the warehouse configuration.|[Putting Items Away](../putting-items-away.md)|  
|Print a list of the items to put away for one or more orders.|Put-away List|  
|Post the receipt of items directly in the inbound order document because no warehouse features exist. \(Works the same for purchase, transfer, and production orders.\)|"Posting Purchase Orders" in [Processing Purchase Orders](../processing-purchase-orders.md)|  
|Put items away order by order and post the receipt in the same activity, in a basic warehouse configuration.|[How to: Put Items Away with Inventory Put-aways](../how-to-put-items-away-with-inventory-put-aways.md)|  
|Put produced items away in a basic warehouse configuration.|"Put Away Output from the Inventory Put-away Document" in [Putting Away Production Output](../how-to-put-away-production-output.md)|  
|Put items away for multiple orders in an advanced warehouse configuration.|[How to: Put Items Away with Warehouse Put-aways](../how-to-put-items-away-with-warehouse-put-aways.md)|  
|Put produced items away in an advanced warehouse configuration.|"Put Away Output with Internal Put-away or Movement" in [Putting Away Production Output](../how-to-put-away-production-output.md)|  
|Get immediate access to put-aways assigned to you as a warehouse worker.|[How to: Find Your Warehouse Assignments](../how-to-find-your-warehouse-assignments.md)|  
|Plan optimized put-away instructions for a number of posted warehouse receipts rather than have warehouse workers act directly on receipts.|[How to: Plan Put-aways in Worksheets](../how-to-plan-put-aways-in-worksheets.md)|  
|Put back items that were picked technically with an internal pick, for example for a production order that did not consume the expected quantity.|"Create a Put-away from the Internal Put-away" in [Picking and Putting Away Without a Source Document](../how-to-create-put-aways-from-internal-put-aways.md)|  
|Create or recreate deleted put-away lines on the basis of posted warehouse receipts lines, in an advanced warehouse configuration.|[How to: Create Put-aways from Posted Receipts](../how-to-create-put-aways-from-posted-receipts.md)|  
|Break a larger unit of measure into smaller units of measure when creating warehouse instructions.|"Breakbulk in Put-aways" in [Automatic Break Bulk for Directed Put-away and Pick](../automatic-breaking-bulk-with-directed-put-away-and-pick.md)|  
|Assign new serial\/lot numbers to items as they enter inventory to enable tracking of the items after they are sold and while they are in inventory.|[How to: Assign Serial Numbers and Lot Numbers During Inbound Transactions](../how-to-assign-serial-numbers-and-lot-numbers-during-inbound-transactions.md)|  
|Split a put-away line to place part of the put-away quantity in available bins because the designated bin is filled up.|[How to: Split Warehouse Activity Lines](../how-to-split-warehouse-activity-lines.md)|  
  
## See Also  
 [Receiving](../receiving.md)   
 [Purchasing](../purchasing.md)   
 [Production](../production.md)   
 [Design and Engineering](../design-and-engineering.md)