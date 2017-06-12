---
title: "How to: Put Items Away with Inventory Put-aways"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "putting away, inventory put-away"
  - "inventory put-aways, putting items away"
  - "put-aways, inventory"
  - "inbound warehouse, putting away"
  - "inventory management, put-aways"
ms.assetid: eef7a658-c3a0-4c1f-8cba-f12fa700d0e5
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
# How to: Put Items Away with Inventory Put-aways
When your location is setup to require put\-away processing but not receive processing, you use the **Inventory Put\-away** document to record and post put\-away and receipt information for your source documents. The inbound source document can be a purchase order, a sales return order, an inbound transfer order, or a production order whose output is ready for put\-away.  
  
### To put items away with the inventory put\-away  
  
1.  In the **Search** box, enter **Inventory Put\-away**, and then choose the related link.  
  
2.  To begin working on the put\-away document, you can either open a put\-away document that has already been created, or you can create a new document. For more information on creating an Inventory Put\-away, see [How to: Create Inventory Put\-aways](../DesignAndEngineering/how-to-create-inventory-put-aways.md).  
  
     To open a previously created put\-away document, select one from the **Inventory Put\-aways** list.  
  
3.  In the put\-away lines, if you are using bins, the bin is specified to which the item should be picked by suggesting the item's default bin in the **Bin Code** field. You can change the bin in this window if necessary.  
  
4.  To create a printed put\-away list for the lines in the window, on the **Actions** tab, in the **General** group, choose **Print**.  
  
5.  Perform the put\-away and enter the information for the actual quantity put away in the **Qty. to Handle** field.  
  
     If it is necessary to place the items for one line in more than one bin, use the **Split Line** function on the **Lines** FastTab. For more information about splitting lines, see [How to: Split Warehouse Activity Lines](../WarehouseActivities/how-to-split-warehouse-activity-lines.md).  
  
6.  When you have performed the put\-away, on the **Actions** tab, in the **Posting** group, choose **Post** to post the put\-away document.  
  
 The posting process will post the receipt, or for production orders, the output, of the source document lines that have been put away, and if the location uses bins, the posting will also create warehouse entries to post the bin quantity changes.  
  
 You can see the posted put\-away information in the **Posted Invt. Put\-away List** window. On the **Navigate** tab, in the **Put away** group, choose **Posted Put\-Aways**.  
  
## See Also  
 [How to: Create Inventory Put\-aways](../DesignAndEngineering/how-to-create-inventory-put-aways.md)   
 [Put Items Away](../WarehouseActivities/put-items-away.md)