---
title: "How to: Reverse Output Posting"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "posting, reversing output"
ms.assetid: 04588043-178d-441b-9a45-b4d158ac631b
caps.latest.revision: 2
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
# How to: Reverse Output Posting
There are times when output posting must be reversed. An example of this would be if a data entry error occurred and an incorrect amount of output is posted to a production order.  
  
### To reverse an output posting  
  
1.  In the **Search** box, enter **Output Journal**, and then choose the related link. Select your batch.  
  
2.  In the **Posting Date** field, type the posting date of the entry to reverse.  
  
3.  In the **Prod. Order No.** field, select the production order of the entry to reverse.  
  
4.  In the **Item No.** field, select the item number of the entry to reverse.  
  
5.  In the **Operation No.** field, type the operation number of the entry to reverse.  
  
6.  In the **Run Time** field, type a negative quantity.  
  
7.  In the **Output Quantity** field, type a negative quantity, if a value was entered into this field during posting.  
  
8.  In the **Applies\-To Entry** field, select the associated item ledger entry. This reverses the capacity and item ledger entries.  
  
9. Post the reversal.  
  
 The output journal entries are posted to the item ledger as a positive adjustment.  
  
## See Also  
 Output Journal   
 Production Journal   
 [About Production Orders](../Production/about-production-orders.md)   
 [How to: Post Output Quantity](../Production/how-to-post-output-quantity.md)   
 [How to: Post Run Times](../Production/how-to-post-run-times.md)   
 [How to: Release Production Orders Automatically](../OperationsPlanning/how-to-release-production-orders-automatically.md)   
 [How to: Release Production Orders by Status Change](../OperationsPlanning/how-to-release-production-orders-by-status-change.md)