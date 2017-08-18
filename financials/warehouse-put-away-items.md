---
    title: Put Items Away | Microsoft Docs
    description: The warehouse activity of putting items away after they are received or output is performed in different ways depending on how warehouse management features are configured.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 08/16/2017
    ms.author: sgroespe

---
# Putting Items Away
The warehouse activity of putting items away after they are received or output is performed in different ways depending on how warehouse management features are configured. The complexity can rank from no warehouse features, through basic warehouse configurations for order-by order handling in one or more activities only, to advanced configurations where all warehouse activities must be performed in a directed workflow. For more information, see [Setting Up Warehouse Management](warehouse-setup-warehouse.md).

When setting up your warehouse, you make a number of different choices regarding how you want to operate and the level of detail and complexity you want to work with. The choices you make affect how you perform tasks in the program. One of these choices is how you want to put items away in your warehouse location.  

If you decide that you want to organize and record put-away information with documents in the program, you place a check mark in the **Require Put-away** field on the location card. This indicates to the program that, when you have items coming into the warehouse location through an inbound source document, you want the put-away of those items to be handled through and recorded in the system. An inbound source document can be a purchase order, sales return order, inbound transfer order, or a production order whose output is ready for put-away.  

When your location is set up to use put-away processing but not receive processing, you use the **Inventory Put-away** window to organize the put-away information, print it, enter the result of the actual put-away and post the put-away information, which in turn posts the receipt information for the source document. In the case of a production order, the posting process posts the output of the order and finishes the production order. You can view the posted put-away information in the **Posted Invt. Put-away** window.

If your location is set up to require receive processing as well as put-away processing, so that you have placed check marks in both the **Require Receive** and **Require Put-away** fields on the location card, there is a different process for putting items away. In this case, you will use the **Warehouse Put-away** window to handle the put-away. The Warehouse Put-away functions similarly to the Inventory Put-away, except that instead of posting the information, you register the put-away. Note that the registering of the warehouse put-away does not post the receipt of the items. It merely updates the bin content. You can view the registered put-away information in the **Registered Put-aways** window.

The following table describes a sequence of tasks, with links to the topics that describe them.   

|**To**|**See**|  
|------------|-------------|  
|Post the receipt of items directly from the inbound order document and thereby record the put away, because no warehouse configuration exists.|[How to: Receive Items](warehouse-how-receive-items.md)|  
|Put items away order by order and post the receipt in the same activity, in a basic warehouse configuration.|[How to: Put Items Away with Inventory Put-aways](warehouse-how-to put-items-away-with-inventory-put-aways.md)|  
|Put items away for multiple orders in an advanced warehouse configuration.|[How to: Put Items Away with Warehouse Put-aways](warehouse-how-to-put-items-away-with-warehouse-put-aways.md)|  
|Put produced items away in a basic or an advanced warehouse configuration.|[Putting Away Production Output](warehouse-how-to-put-away-production-output.md)|
|Plan optimized put-away instructions for a number of posted warehouse receipts rather than have warehouse workers act directly on receipts.|[How to: Plan Put-aways in Worksheets](warehouse-how-to-plan-put-aways-in-worksheets.md)|  
|Put back items that were picked technically with an internal pick, for example for a production order that did not consume the expected quantity.|"Create an Internal Put-away" in [Picking and Putting Away Without a Source Document](warehouse-how-to-create-put-aways-from-internal-put-aways.md)|  
|Split a put-away line to place part of the put-away quantity in available bins because the designated bin is filled up.|[How to: Split Warehouse Activity Lines](warehouse-how-to-split-warehouse-activity-lines.md)|
|Get immediate access to put-aways that are assigned to you as a warehouse worker.|[How to: Find Your Warehouse Assignments](warehouse-how-to-find-your-warehouse-assignments.md)|    

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
