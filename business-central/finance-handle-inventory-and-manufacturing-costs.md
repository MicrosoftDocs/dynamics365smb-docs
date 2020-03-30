---
    title: Handle Inventory and Manufacturing Costs | Microsoft Docs
    description: Although much of the cost accounting functionality is expressed in underlying processes with no user interaction, such as entry application and automatic cost adjustment, a number of fields, pages, and reports are aimed at users who directly or indirectly manage the cost of items or operations.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Handling Inventory and Manufacturing Costs
Although much of the cost accounting functionality is expressed in underlying processes with no user interaction, such as entry application and automatic cost adjustment, a number of fields, pages, and reports are aimed at users who directly or indirectly manage the cost of items or operations.  

 Assigning item charges to purchase documents is an example of an indirect cost accounting task. Updating the unit cost of assembly or production BOM item is an example of a more direct cost accounting task.  

 The following table describes a sequence of tasks, with links to the topics that describe them.   

|**To**|**See**|  
|------------|-------------|  
|Periodically or automatically update the unit cost of one or multiple items to forward any cost changes from inbound entries, such as those for purchases or production output, to the related outbound entries, such as consumption or transfers.|[Adjust Item Costs](inventory-how-adjust-item-costs.md)|  
|Get insight into average cost dynamics to make pricing decisions or to track cost fluctuations caused by data entry errors.|[Register New Items](inventory-how-register-new-items.md)|  
|Create a manufacturing item's standard cost by entering the three cost elements: material cost, capacity cost, and subcontractor cost.|[About Calculating Standard Cost](finance-about-calculating-standard-cost.md)|  
|Calculate the unit cost of a BOM item based on the unit costs of its underlying components.|[Work with Bills of Material](inventory-how-work-BOMs.md)|  
|Complete the costing life cycle of a produced item by adjusting the costs and reconciling the value entries with the general ledger.|[About Finished Production Order Costs](finance-about-finished-production-order-costs.md)|  
|Change the value of an item in inventory or the value of one item ledger entry, such as a purchase transaction.|[Revalue Inventory](inventory-how-revalue-inventory.md)|
|Manually undo an item application or reapply item ledger entries created by application.|[Remove and Reapply Item Ledger Entries](finance-how-to-remove-and-reapply-item-entries.md)|  
|Use the **Applies-from Entry** field in the item journal to manually create a fixed application between an inbound transaction and the original outbound transaction.|[Close Open Item Ledger Entries Resulting from Fixed Application in the Item Journal](finance-how-to-close-open-item-ledger-entries-resulting-from-fixed-application-in-the-item-journal.md)|  

## See Also  
[Manage Inventory Costs](finance-manage-inventory-costs.md)
[Design Details: Inventory Costing](design-details-inventory-costing.md)
