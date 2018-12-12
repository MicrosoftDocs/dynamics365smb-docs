---
title: Count Inventory With Document-Based Functionality| Microsoft Docs
description: Describes how to perform physical counting using the Physical Order Inventory and Physical Inventory Recording pages.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: adjustment, negative, positive, increase, decrease
ms.date: 12/12/2018
ms.author: sgroespe

---
# Counting Inventory Using Documents
You can take inventory of your items using the physical inventory order and the physical inventory recording documents.  

The physical inventory order contains data for planning, realizing, and analyzing physical inventory. The item, location, and bin information are also available.  

> [!NOTE]
> This procedure describes how to perform a physical inventory using documents, which provide more control and support distributing the counting to multiple employees. You can also perform the task using journals, the **Phys. Inventory Journals** and **Whse. Phys. Inventory Journals** pages. For more information, see [Count, Adjust, and Reclassify Inventory With Journals](inventory-how-count-adjust-reclassify.md).<br /><br />
> Note that if you have locations set up with bins, you must use the **Whse. Phys. Inventory Journal** page to count your warehouse entries before synchronizing them with item ledger entries.

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
[Inventory](inventory-manage-inventory.md)
[Warehouse Management](warehouse-manage-warehouse.md)    
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
