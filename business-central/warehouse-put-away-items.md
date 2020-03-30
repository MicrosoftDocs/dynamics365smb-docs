---
    title: Put Items Away | Microsoft Docs
    description: The warehouse activity of putting items away after they are received or output is performed in different ways depending on how warehouse management features are configured.
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
# Putting Items Away
The warehouse activity of putting items away after they are received or output is performed in different ways depending on how warehouse management features are configured. The complexity can rank from no warehouse features, through basic warehouse configurations for order-by order handling in one or more activities only, to advanced configurations where all warehouse activities must be performed in a directed workflow. For more information, see [Setting Up Warehouse Management](warehouse-setup-warehouse.md).

If you decide that you want to organize and record put-away information with warehouse documents, you place a check mark in the **Require Put-away** field on the location card. This indicates that when you have items coming into the warehouse location through an inbound source document, you want the put-away of those items to be controlled by the system. An inbound source document can be a purchase order, a sales return order, an inbound transfer order, or a production order whose output is ready for put-away.  

If your location is set up to use put-away processing but not receive processing, you use the **Inventory Put-away** page to organize the put-away information, print it, enter the result of the actual put-away and post the put-away information, which in turn posts the receipt information for the source document. In the case of a production order, the posting process posts the output of the order and finishes the production order.

If your location is set up to require both receive and put-away processing, so that you have placed check marks in both the **Require Receive** and the **Require Put-away** field on the location card, there is a different process for putting items away. In this case, you will use the **Warehouse Put-away** page to handle the put-away. The warehouse put-away functions similarly to the inventory put-away, except that instead of posting the information, you register the put-away. Note that the registering of the warehouse put-away does not post the receipt of the items. It merely updates the bin content. As a warehouse manager, you can use a put-away worksheets to organize put-away information before creating the individual warehouse put-away instructions.

The following table describes a sequence of tasks, with links to the topics that describe them.   

|**To**|**See**|  
|------------|-------------|  
|Post the receipt of items directly from the inbound order document and thereby record the put away, because no warehouse configuration exists.|[Receive Items](warehouse-how-receive-items.md)|  
|Put items away order by order and post the receipt in the same activity, in a basic warehouse configuration.|[Put Items Away with Inventory Put-aways](warehouse-how-to-put-items-away-with-inventory-put-aways.md)|  
|Put items away for multiple orders in an advanced warehouse configuration.|[Put Items Away with Warehouse Put-aways](warehouse-how-to-put-items-away-with-warehouse-put-aways.md)|  
|Put produced or assembled items away in a basic or an advanced warehouse configuration.|[Put Away Production or Assembly Output](warehouse-how-to-put-away-production-output.md)|
|Plan optimized put-away instructions for a number of posted warehouse receipts rather than have warehouse workers act directly on receipts.|[Plan Put-aways in Worksheets](warehouse-how-to-plan-put-aways-in-worksheets.md)|  
|Put back items that were picked technically with an internal pick, for example for a production order that did not consume the expected quantity.|[Pick and Put Away Without a Source Document](warehouse-how-to-create-put-aways-from-internal-put-aways.md)|
|Split a put-away line to place part of the put-away quantity in available bins because the designated bin is filled up.|[Split Warehouse Activity Lines](warehouse-how-to-split-warehouse-activity-lines.md)|
|Get immediate access to put-aways that are assigned to you as a warehouse worker.|[Find Your Warehouse Assignments](warehouse-how-to-find-your-warehouse-assignments.md)|    

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
