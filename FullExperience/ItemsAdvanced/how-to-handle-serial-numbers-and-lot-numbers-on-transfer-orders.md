---
title: "How to: Handle Serial Numbers and Lot Numbers on Transfer Orders"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "lot numbers, transfer orders"
  - "purchase orders, serial numbers"
  - "serial numbers, handling on transfer orders"
  - "transfers, orders"
  - "item tracking, handling on transfer orders"
  - "purchase orders, lot numbers"
ms.assetid: 28de447d-804e-496a-9caa-bf594b37322d
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
# How to: Handle Serial Numbers and Lot Numbers on Transfer Orders
Procedures for handling serial and lot numbers that are being transferred between different locations are similar to those applied when items are sold and purchased.  
  
 However, the transfer order is unique in that shipment and receipt are both done from the same transfer line and, therefore, use the same instance of the **Item Tracking Lines** window. This means that item tracking numbers shipped from one location must be received unchanged at the other location.  
  
 The exact rules for handling item tracking numbers across your company are governed by the setup of the  **Item Tracking Code** table.  
  
### To handle serial\/lot numbers on transfer orders  
  
1.  In the **Search** box, enter **Transfer Orders**, and then choose the related link.  
  
2.  Open the transfer order you want to process. On the **Lines** FastTab, choose **Actions**, choose **Line**, choose **Item Tracking Lines**, and then choose **Shipment**.  
  
3.  In the **Item Tracking Lines** window, assign or select serial or lot numbers as for any other outbound item transaction.  
  
     When handling serial and lot numbers for transfer items, the items typically have numbers already assigned to them. Therefore, the process typically consists of selecting from existing serial or lot numbers.  
  
4.  Post the transfer order, first ship and then receive, to record that the items are transferred carrying their item tracking entries.  
  
 During the transfer, the **Item Tracking Lines** window remains locked for writing.  
  
## See Also  
 [How to: Assign Serial Numbers and Lot Numbers During Inbound Transactions](../WarehouseActivities/how-to-assign-serial-numbers-and-lot-numbers-during-inbound-transactions.md)   
 [How to: Assign Serial Numbers and Lot Numbers During Outbound Transactions](../WarehouseActivities/how-to-assign-serial-numbers-and-lot-numbers-during-outbound-transactions.md)   
 [How to: Select from Existing Serial Numbers and Lot Numbers](../DesignAndEngineering/how-to-select-from-existing-serial-numbers-and-lot-numbers.md)