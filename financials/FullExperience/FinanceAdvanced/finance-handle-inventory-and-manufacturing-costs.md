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
# Handle Inventory and Manufacturing Costs
Although much of the cost accounting functionality is expressed in underlying processes with no user interaction, such as entry application and automatic cost adjustment, a number of fields, windows, and reports are aimed at users who directly or indirectly manage the cost of items or operations.  
  
 Assigning item charges to purchase documents is an example of an indirect cost accounting task. Updating the unit cost of production BOM item is an example of a more direct cost accounting task.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Initiate and view the ever-changing cost of the item as it is being traded.|Unit Cost|  
|Use functions in return orders to ensure that the cost on the original posted document lines is reversed when adding or removing the returned item in inventory.|[How to: Assign Exact Cost Reversing in Sales](../how-to-assign-exact-cost-reversing-in-sales.md)|  
|Periodically or automatically update the unit cost of one or multiple items to forward any cost changes from inbound entries, such as those for purchases or production output, to the related outbound entries, such as consumption or transfers.|Adjust Cost - Item Entries|  
|Enter an item charge, such as a freight charge, on a purchase or sales document and add that charge to the unit cost of the related items.|[How to: Assign Item Charges to Purchase Documents](../How%20to:%20Assign%20Item%20Charges%20to%20Purchase%20Documents.md)|  
|Get insight into average cost dynamics to make pricing decisions or to track cost fluctuations caused by data entry errors.|Average Cost Calc. Overview|  
|Update the unit cost and unit price of multiple items, for example, to reflect a general price increase of 5%.|Adjust Item Costs-Prices|  
|Create a manufacturing item's standard cost by entering the three cost elements: material cost, capacity cost, and subcontractor cost.|[About Calculating Standard Cost](../about-calculating-standard-cost.md)|  
|Update the standard cost of multiple items and production BOMs.|Update Unit Cost|  
|Calculate the unit cost of a BOM item based on the unit costs of its underlying components.|[How to: Calculate the Standard Cost of Assembly BOMs](../how-to-calculate-the-standard-cost-of-assembly-boms.md)|  
|Complete the costing life cycle of a produced item by adjusting the costs and reconciling the value entries with the general ledger.|[How to: Finish Production Orders](../how-to-finish-production-orders.md)|  
|Change the value of an item in inventory or the value of one item ledger entry, such as a purchase transaction.|[Inventory Revaluation](../inventory-revaluation.md)|  
|Manually undo an item application or reapply item ledger entries created by the program.|[How to: Remove and Reapply Item Entries](../how-to-remove-and-reapply-item-entries.md)|  
|Use the **Applies-from Entry** field in the item journal to manually create a fixed application between an inbound transaction and the original outbound transaction.|[How to: Close Open Item Ledger Entries Resulting from Fixed Application in the Item Journal](../how-to-close-open-item-ledger-entries-resulting-from-fixed-application-in-the-item-journal.md)|  
  
## See Also  
 [Set Up Inventory Valuation and Costing](../set-up-inventory-valuation-and-costing.md)   
 [Manage Sales Returns](../manage-sales-returns.md)   
 [Execute Production](../execute-production.md)   
 [Close Years and Periods](../close-years-and-periods.md)   
 [Design Details: Inventory Costing](design-details-inventory-costing.md)