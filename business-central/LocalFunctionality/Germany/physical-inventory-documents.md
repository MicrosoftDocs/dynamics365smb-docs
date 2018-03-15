---
    title: Physical Inventory Documents
    description: You can take inventory of your items using the physical inventory order and the physical inventory recording documents.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Physical Inventory Documents
You can take inventory of your items using the physical inventory order and the physical inventory recording documents.  

The physical inventory order contains data for planning, realizing, and analyzing physical inventory. The item, location, and bin information are also available.  

## Physical Inventory Recording  
The physical inventory recording contains the item names and quantities counted while taking physical inventory. An item may be counted in more than one physical inventory recording.  

A physical inventory order can be related to more than one physical inventory recording, but a physical inventory recording can be related to only one physical inventory order. For more information, see [Physical Inventory Recording - Counting Physical Inventory](physical-inventory-recording-counting-physical-inventory.md).  

After completing the physical inventory recordings and the physical inventory order, you can post the physical inventory order. The information is transferred to the physical inventory journal. After this transfer, the physical inventory order will be available as a posted physical inventory order for future retrieval.  

## Posted Physical Inventory Documents  
After posting the physical inventory order will be deleted and you can view and evaluate the document as posted physical inventory order.  

When posting the physical inventory orders also physical inventory recording headers and physical inventory recording lines and physical inventory comment lines will be transferred to posted documents.  

The posted inventory documents offer you the possibility to get a complete overview about the whole process of physical inventory. You cannot change the data of posted physical inventory order headers and posted physical inventory order lines because the documents have been already posted.  

If you have used also item tracking lines to register serial nos. and lot nos. the program will save the expected item tracking lines, the recorded item tracking lines and the posted item tracking ledger entries.  

It is possible to use the posted physical inventory order to create new physical inventory orders using the copy function.  

You can use Navigate to view the inventory ledger entries and other related ledger entries for a posted physical inventory order.  

## See Also  
 [Warehouse Management](../../warehouse-manage-warehouse.md)   
 [Physical Inventory Order Lines With Item Tracking Lines](physical-inventory-order-lines-with-item-tracking-lines.md)   
 [Physical Inventory Recording - Counting Physical Inventory](physical-inventory-recording-counting-physical-inventory.md)   
 [Set Up Physical Inventory Documents](how-to-set-up-physical-inventory-documents.md)   
 [Enter Physical Inventory Orders](how-to-enter-physical-inventory-orders.md)   
 [Create a Physical Inventory Recording](how-to-create-a-physical-inventory-recording.md)   
 [Post Physical Inventory Orders](how-to-post-physical-inventory-orders.md)   
 [Germany Local Functionality](germany-local-functionality.md)
