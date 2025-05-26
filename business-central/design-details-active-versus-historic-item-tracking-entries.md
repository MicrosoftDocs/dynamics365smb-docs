---
title: Design Details - Active versus Historic Item Tracking Entries
description: When parts of a document line quantity are posted, only that quantity is transferred to the item ledger entries and its item tracking numbers.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords:
ms.date: 06/15/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Design Details: Active versus Historic Item Tracking Entries
When parts of a document line quantity are posted, only that particular quantity is transferred to the item ledger entries and its item tracking numbers. However, you will want to access all relevant item tracking information directly from the active document line. That is, not only will you want to see the entries that are related to the remaining quantity, you will also want information about the units that have been posted. When you view or modify the **Item Tracking Lines** page, the collective contents of the **Tracking Specification** table (T336) and **Reservation Entry** table (T337) are presented in a temporary version of T336. This ensures that historic and active item tracking data is accessed as one.  

 The following table shows how T336 and T337 are used in a purchase scenario. The bold figures represent values that the user manually enters on the **Item Tracking Lines** page.  

 Step 1: Create a purchase order line of seven pieces with item tracking numbers.  

||**Quantity (Base)**|**Qty. to Handle**|**Qty. to Invoice (Base)**|**Quantity Handled (Base)**|**Quantity Invoiced (Base)**|  
|-|----------------------------------------------|--------------------------------------------|------------------------------------------------------|-------------------------------------------------------|--------------------------------------------------------|  
|**T337**|7|0|0|0|0|  
|**T336**|0|0|0|0|0|  

 Step 2: Receive four pieces.  

||**Quantity (Base)**|**Qty. to Handle**|**Qty. to Invoice (Base)**|**Quantity Handled (Base)**|**Quantity Invoiced (Base)**|  
|-|----------------------------------------------|--------------------------------------------|------------------------------------------------------|-------------------------------------------------------|--------------------------------------------------------|  
|**Item Tracking Lines** page|7|**4**|**0**|0|0|  
|**T337**|3|0|0|0|0|  
|**T336**|4|0|0|4|0|  

 Step 3: Receive two pieces and invoice two pieces.  

||**Quantity (Base)**|**Qty. to Handle**|**Qty. to Invoice (Base)**|**Quantity Handled (Base)**|**Quantity Invoiced (Base)**|  
|-|----------------------------------------------|--------------------------------------------|------------------------------------------------------|-------------------------------------------------------|--------------------------------------------------------|  
|**Item Tracking Lines** page|7|**2**|**2**|4|0|  
|**T337**|1|0|0|0|0|  
|**T336**|6|0|0|6|2|  

 Step 4: Receive one piece.  

||**Quantity (Base)**|**Qty. to Handle**|**Qty. to Invoice (Base)**|**Quantity Handled (Base)**|**Quantity Invoiced (Base)**|  
|-|----------------------------------------------|--------------------------------------------|------------------------------------------------------|-------------------------------------------------------|--------------------------------------------------------|  
|**Item Tracking Lines** page|7|**1**|**0**|6|2|  
|**T336**|7|0|0|7|2|  

 Invoice 5 pieces.  

||**Quantity (Base)**|**Qty. to Handle**|**Qty. to Invoice (Base)**|**Quantity Handled (Base)**|**Quantity Invoiced (Base)**|  
|-|----------------------------------------------|--------------------------------------------|------------------------------------------------------|-------------------------------------------------------|--------------------------------------------------------|  
|**Item Tracking Lines** page|7|0|**5**|7|2|  
|**T336**|7|0|0|7|7|  

## Related information  
 [Design Details: Item Tracking](design-details-item-tracking.md)   
 [Design Details: Item Tracking Lines Page](design-details-item-tracking-lines-window.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
