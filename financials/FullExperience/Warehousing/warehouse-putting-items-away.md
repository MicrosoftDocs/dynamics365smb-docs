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
# Putting Items Away
When setting up your warehouse, you make a number of different choices regarding how you want to operate and the level of detail and complexity you want to work with. The choices you make affect how you perform tasks in the program. One of these choices is how you want to put items away in your warehouse location.  
  
 If you decide that you want to organize and record put-away information with documents in the program, you place a check mark in the **Require Put-away** field on the location card. This indicates to the program that, when you have items coming into the warehouse location through an inbound source document, you want the put-away of those items to be handled through and recorded in the system. An inbound source document can be a purchase order, sales return order, inbound transfer order, or a production order whose output is ready for put-away.  
  
 When your location is set up to use put-away processing but not receive processing, you use the **Inventory Put-away** window to organize the put-away information, print it, enter the result of the actual put-away and post the put-away information, which in turn posts the receipt information for the source document. In the case of a production order, the posting process posts the output of the order and finishes the production order. You can view the posted put-away information in the **Posted Invt. Put-away** window. For more information on putting items away from the inventory menu, see [How to: Put Items Away with Inventory Put-aways](../how-to-put-items-away-with-inventory-put-aways.md).  
  
 If your location is set up to require receive processing as well as put-away processing, so that you have placed check marks in both the **Require Receive** and **Require Put-away** fields on the location card, there is a different process for putting items away. In this case, you will use the **Warehouse Put-away** window to handle the put-away. The Warehouse Put-away functions similarly to the Inventory Put-away, except that instead of posting the information, you register the put-away. Note that the registering of the warehouse put-away does not post the receipt of the items. It merely updates the bin content. You can view the registered put-away information in the **Registered Put-aways** window. For more information, see [How to: Put Items Away with Warehouse Put-aways](../how-to-put-items-away-with-warehouse-put-aways.md).  
  
## See Also  
 [How to: Put Items Away with Inventory Put-aways](../how-to-put-items-away-with-inventory-put-aways.md)   
 [How to: Put Items Away with Warehouse Put-aways](../how-to-put-items-away-with-warehouse-put-aways.md)