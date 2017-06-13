---
title: "How to: Fill In Revaluation Journals Manually"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "revaluing inventory, filling in journals"
  - "journals, revaluation"
  - "inventory, revaluation"
ms.assetid: 9f8ce5b8-593c-40b5-9935-cf13030c29e3
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
# How to: Fill In Revaluation Journals Manually
If you want to appreciate or depreciate an item or a specific item ledger entry, you must use the revaluation journal.  
  
 First, you must fill in the revaluation journal with information about the current, calculated value of the specified item. You can do this manually or use the **Calculate Inventory Value** batch job.  
  
> [!NOTE]  
>  If you entered a line manually, the journal will revalue all units that are linked to this item ledger entry, regardless of their posting date.  
  
### To fill in the revaluation journal manually  
  
1.  In the **Search** box, enter **Revaluation Journal**, and then choose the related link.  
  
2.  Select the **Item No.** field to open the **Item List** window.  
  
3.  Select the item that you want to revalue, and choose the **OK** button.  
  
4.  Select the **Applies\-to Entry** field to open the **Item Ledger Entries** window. All item ledger entries relating to this item are displayed.  
  
5.  Select the specific item ledger entry that you want to revalue, and choose the **OK** button.  
  
6.  Repeat the procedure for each item that you want to revalue.  
  
 You can now revalue the selected item ledger entries. When you have filled in the revaluation journal, you can post the journal.  
  
### To post a revaluation journal  
  
1.  In the **Search** box, enter **Revaluation Journal**, and then choose the related link.  
  
2.  On the **Actions** tab, in the **Posting** group, choose **Post** or **Post and Print** to post the journal.  
  
3.  The value entries are created to reflect the revaluing. You can see these from the item card.  
  
## See Also  
 [Inventory Revaluation](../DesignAndEngineering/inventory-revaluation.md)   
 [How to: Enter New Values When Revaluing Items](../DesignAndEngineering/how-to-enter-new-values-when-revaluing-items.md)   
 [How to: Fill In the Revaluation Journal with the Batch Job](../DesignAndEngineering/how-to-fill-in-the-revaluation-journal-with-the-batch-job.md)