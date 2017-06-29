---
title: "How to: Handle Item Tracking Lines with the Get Lines Function"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "item tracking, handling lines"
ms.assetid: f4e9eec5-8e4b-4e58-9bea-c0ec901e41df
caps.latest.revision: 8
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
# How to: Handle Item Tracking Lines with the Get Lines Function
When you use functionality to get posted receipt or shipment lines from related invoices or credit memos, then any item tracking lines on the warehouse documents are transferred automatically, however, they are processed in a special way. For more information about getting lines, see [\($ N\_5709 Get Receipt Lines $\)](../Topic/\($%20N_5709%20Get%20Receipt%20Lines%20$\).md).  
  
 The functionality supports the following inbound processes:  
  
-   **Get Receipt Lines** \- from a purchase invoice.  
  
-   **Get Return Shipment Lines** \- from a purchase credit memo.  
  
 The functionality supports the following outbound processes:  
  
-   **Get Shipment Lines** \- from a sales invoice or combined shipments.  
  
-   **Get Return Receipt Lines** \- from a sales credit memo.  
  
 In these situations, the existing item tracking lines are copied automatically to the invoice or credit memo, but the **Item Tracking Lines** window does not permit changes to the serial or lot numbers. Only the quantities can be changed.  
  
### To handle item tracking lines when getting receipt lines from a purchase invoice  
  
1.  In the **Search** box, enter **Purchase Invoices**, and then select the related link.  
  
2.  Open a purchase invoice for items that are purchase with serial or lot numbers.  
  
3.  From a purchase invoice line, on the **Lines** FastTab, choose **Functions**, and then choose **Get Receipt Lines**.  
  
4.  In the **Get Receipt Lines** window, select a receipt lines that has item tracking lines, and then choose the **OK** button.  
  
     The source document is copied to the purchase invoice as a new line, and its item tracking lines are copied to the underlying **Item Tracking Lines** window.  
  
5.  In the purchase invoice, select the transferred receipt line.  
  
6.  On the **Lines** FastTab, choose **Line**, and then choose **Item Tracking Lines** to see the transferred item tracking lines.  
  
 The contents of the **Serial No.** and **Lot No.** fields are not editable. However, you can delete complete lines or change the quantities to match changes being made on the source line.  
  
## See Also  
 [How to: Set Up Item Tracking Codes](../DesignAndEngineering/how-to-set-up-item-tracking-codes.md)   
 [How to: Assign Serial Numbers and Lot Numbers During Inbound Transactions](../WarehouseActivities/how-to-assign-serial-numbers-and-lot-numbers-during-inbound-transactions.md)   
 [How to: Assign Serial Numbers and Lot Numbers During Outbound Transactions](../WarehouseActivities/how-to-assign-serial-numbers-and-lot-numbers-during-outbound-transactions.md)