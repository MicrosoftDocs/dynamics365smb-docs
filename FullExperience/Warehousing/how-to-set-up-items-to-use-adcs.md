---
title: "How to: Set Up Items to Use ADCS"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "automated data capture system, setting up items"
  - "items, automated data capture system"
ms.assetid: 3c09e66e-bb56-4274-ac2b-bb5c64deeafa
caps.latest.revision: 5
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
# How to: Set Up Items to Use ADCS
Each warehouse item that you want to use with ADCS must be assigned an identifier code to link it with its item number. For example, you can use the item's bar code as the identifier code. An item can also have multiple identifier codes. You may find this useful in the case where an item is available in various units of measures, such as pieces and pallets. In this case, assign an identifier code to each.  
  
### To specify item identifier codes  
  
1.  In the **Search** box, enter **Items**, and then choose the related link.  
  
2.  Select an item from the list that is part of your ADCS solution. On the **Home** tab, in the **Manage** group, choose **Edit**. The **\($ N\_30 Item Card $\)** window opens.  
  
3.  On the **Navigate** tab, in the **Master Data** group, choose **Identifiers**. The **\($ N\_7707 Item Identifiers List $\)** window opens.  
  
4.  On the **Home** tab, choose **New**. In the **\($ T\_7704\_1 Code $\)** field, specify the identifier for the item. For example, the identifier could be the item's bar code number.  
  
     You can also enter a **Variant Code** and a **Unit of Measure** code.  
  
     If needed, enter multiple codes for each item. Choose **New** again to specify another identifier code. Choose the **OK** button.  
  
5.  To review the information, expand the **Warehouse** FastTab and choose the **\($ T\_27\_7700 Identifier Code $\)** field. The **\($ N\_7707 Item Identifiers List $\)** window opens. You can review the information that you have entered.  
  
## See Also  
 [Use Automated Data Capture Systems \(ADCS\)](../WarehouseActivities/use-automated-data-capture-systems-adcs-.md)   
 [\($ T\_7704 Item Identifier $\)](../Topic/\($%20T_7704%20Item%20Identifier%20$\).md)   
 [\($ N\_7707 Item Identifiers List $\)](../Topic/\($%20N_7707%20Item%20Identifiers%20List%20$\).md)