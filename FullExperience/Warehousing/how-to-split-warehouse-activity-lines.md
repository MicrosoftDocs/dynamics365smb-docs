---
title: "How to: Split Warehouse Activity Lines"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "bins, splitting lines for bin quantities"
  - "picking, splitting lines"
  - "splitting, lines for bin quantities"
  - "movements, splitting lines"
  - "adjusting, splitting lines"
  - "putting away, splitting lines"
ms.assetid: abd573ec-e7f8-438e-ab3b-d16b2885d57a
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
# How to: Split Warehouse Activity Lines
In warehouse put\-aways, movements, or picks, and in inventory put\-aways and inventory picks, bins are suggested for the picking or putting away of items. The actual quantity in the bin suggested may not be sufficient, or there is not enough room in the suggested bin to put away the required quantity. In these cases, you need to split the line, so that the items for one line are either taken from or placed into more than one bin.  
  
 The following procedure applies to all document lines that are managed in the **Warehouse Activity Line** table, such as warehouse put\-away, movement, and pick lines, or inventory put\-away, movement, and pick lines.  
  
### To split warehouse activity lines  
  
1.  Open a warehouse activity line where you are trying to handle an insufficient quantity.  
  
2.  In the **Qty. to Handle** field, enter the reduced quantity that you are able to handle.  
  
3.  On the **Lines** FastTab, choose the **Actions** button, choose **Functions**, and then choose **Split Line**. A new line appears, which is a copy of the original line, except that the **Qty. to Handle** field contains the quantity that you removed from the original line.  
  
4.  Assign an appropriate bin and, if you are using directed put\-away and pick, a zone, to this new line, or continue splitting the line as necessary until you find appropriate bins for all of the quantity.  
  
> [!NOTE]  
>  If the location uses directed put\-away and pick and you split the lines, you must be familiar with the warehouse and be able to choose a bin that matches the storage requirements of the item and that fulfills the general requirements of the warehouse document. For example, you would not split a line on a pick document and place some items in the bulk storage.  
  
## See Also  
 [Perform Warehouse Activities](../WarehouseActivities/perform-warehouse-activities.md)   
 [Qty. to Handle](../Topic/\($%20T_5767_26%20Qty.%20to%20Handle%20$\).md)   
 [Warehouse Activity Line](../Topic/\($%20T_5767%20Warehouse%20Activity%20Line%20$\).md)