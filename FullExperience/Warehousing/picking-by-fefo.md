---
title: "Picking by FEFO"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "picking, first-expired-first-out"
  - "first-expired-first-out"
  - "picking, by FEFO"
  - "outbound warehouse, picking"
ms.assetid: ce6ff1ab-13d1-4232-adb8-2f71aa498204
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
# Picking by FEFO
First\-Expired\-First\-Out \(FEFO\) is a sorting method that ensures that the oldest items, those with the earliest expiration dates, are picked first.  
  
 This functionality only works when the following criteria are met:  
  
-   The item must have a serial\/lot number.  
  
-   On the item’s item tracking code setup, the **SN\-Specific Warehouse Tracking** field or the **Lot\-Specific Warehouse Tracking** field must be selected.  
  
-   The item must be posted to inventory with an expiration date.  
  
-   On the location card, the **Require Pick** check box must be selected.  
  
-   On the location card, the **Pick According to FEFO** check box must be selected.  
  
-   On the location card, the **Bin Mandatory** check box must be selected.  
  
 When all the criteria are met, then serial\/lot\-numbered items to be picked are sorted with the oldest first in all picks and movements, except for items that use SN\-specific or lot\-specific tracking.  
  
> [!NOTE]  
>  If some serial\/lot\-numbered items use specific tracking, then those are respected first and under them, the remaining, non\-specific, serial\/lot numbers are listed according to FEFO.  
  
 If two serial\/lot\-numbered items have the same expiration date, then the program selects the item with the lowest serial or lot number. If the serial or lot numbers are the same, then the program selects the item that was registered first.  
  
> [!NOTE]  
>  -   When picking serial\/lot\-numbered items in locations set up for directed put\-away and pick, only quantities on bins of type *Pick* are picked according to FEFO.  
> -   To enable movements according to FEFO, either in the **Inventory Movement** window or the **Movement Worksheet** window, you must leave the **From Bin** field empty.  
> -   If the **Strict Expiration Posting** field is selected, then only items that are not expired will be included in the pick. This applies even if you are not using Pick according to FEFO.  
  
## See Also  
 [Pick Items](../WarehouseActivities/pick-items.md)   
 [\($ T\_6502\_11 SN Specific Tracking $\)](../Topic/\($%20T_6502_11%20SN%20Specific%20Tracking%20$\).md)   
 [\($ T\_14\_5727 Require Pick $\)](../Topic/\($%20T_14_5727%20Require%20Pick%20$\).md)   
 [\($ N\_7382 Inventory Movement $\)](../Topic/\($%20N_7382%20Inventory%20Movement%20$\).md)   
 [\($ N\_7351 Movement Worksheet $\)](../Topic/\($%20N_7351%20Movement%20Worksheet%20$\).md)   
 [How to: Pick Items for Warehouse Shipment](../WarehouseActivities/how-to-pick-items-for-warehouse-shipment.md)   
 [How to: Pick Items with Inventory Picks](../DesignAndEngineering/how-to-pick-items-with-inventory-picks.md)   
 [\($ T\_6502\_8 Strict Expiration Posting $\)](../Topic/\($%20T_6502_8%20Strict%20Expiration%20Posting%20$\).md)   
 [\($ T\_14\_7307 Pick According to FEFO $\)](../Topic/\($%20T_14_7307%20Pick%20According%20to%20FEFO%20$\).md)   
 [\($ T\_14\_5732 Bin Mandatory $\)](../Topic/\($%20T_14_5732%20Bin%20Mandatory%20$\).md)