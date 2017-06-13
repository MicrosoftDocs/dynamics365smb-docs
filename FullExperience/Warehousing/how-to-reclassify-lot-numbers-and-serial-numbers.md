---
title: "How to: Reclassify Lot Numbers and Serial Numbers"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "reclassifying, serial numbers"
  - "reclassifying, lot numbers"
  - "item tracking, reclassifying"
  - "lot numbers, reclassifying"
  - "reclassifying, item tracking"
  - "serial numbers, reclassifying"
ms.assetid: 40c61d72-1c1d-4680-bc90-4e1197582d27
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
# How to: Reclassify Lot Numbers and Serial Numbers
Reclassifying item tracking for an item means changing a lot or serial number to a new lot or serial number or changing the expiration date to a new expiration date. If you are working with lots, you can also merge multiple lots into one. You perform these tasks using the item reclassification journal.  
  
### To reclassify item tracking  
  
1.  In the **Search** box, enter **Item Reclass. Journal**, and then choose the related link.  
  
2.  Fill in the line with the relevant information. On the **Navigate** tab, in the **Line** group, choose **Item Tracking Lines**.  
  
3.  In the **Serial No.** or **Lot No.** field, select the current serial or lot number.  
  
4.  If you want to enter a new item tracking number, enter it in the **New Serial No.** or **New Lot No.** field. If you want, you can merge one or more lots to one new or existing lot.  
  
    > [!NOTE]  
    >  Be aware that when you reclassify expiration dates, then the items with the earliest expiration dates for outbound transactions are suggested first. For more information, see [Picking by FEFO](../WarehouseActivities/picking-by-fefo.md).  
  
5.  If you would like to enter a new expiration date for the serial or lot number, enter it in the **New Expiration Date** field.  
  
    > [!IMPORTANT]  
    >  If you are reclassifying a lot to the same lot number but with a different expiration date, you must reclassify the entire lot, using one item reclassification journal line. If you are reclassifying more than one lot to one new lot number, meaning that you are merging more than one lot into one new lot, you must enter the same new expiration date for all the lots. If you are reclassifying one existing lot to a second existing lot that has a different expiration date, you must use the expiration date from the second lot. If you leave the **New Expiration Date** field blank, the lot or serial number will be reclassified with a blank expiration date.  
  
6.  If you have existing information on the old serial or lot number, you can copy it to the new serial or lot number.  
  
    1.  In the **Item Tracking Lines** window, on the **Navigate** tab, in the **Line** group, choose **New Serial No. Information** or **New Lot No. Information**.  
  
    2.  To copy information from the old lot or serial number, on the **Actions** tab, in the **Functions** group, choose **Copy Info**.  
  
    3.  In the information list window, select the lot or serial number that you would like to copy from, and choose the **OK** button.  
  
7.  If you want to modify the existing information for the lot or serial number, you can record lot or serial information.  
  
8.  Post the journal to link the renewed item tracking numbers or expiration dates to the associated item ledger entry.  
  
## See Also  
 [How to: Assign Serial Numbers and Lot Numbers During Inbound Transactions](../WarehouseActivities/how-to-assign-serial-numbers-and-lot-numbers-during-inbound-transactions.md)   
 [How to: Assign Serial Numbers and Lot Numbers During Outbound Transactions](../WarehouseActivities/how-to-assign-serial-numbers-and-lot-numbers-during-outbound-transactions.md)   
 [How to: Record Serial Number and Lot Number Information](../DesignAndEngineering/how-to-record-serial-number-and-lot-number-information.md)