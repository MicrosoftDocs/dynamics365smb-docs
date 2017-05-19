---
title: "How to: Renumber Document Numbers in Journals"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 148de0e4-544d-4ea7-8f9c-e983d791e96a
caps.latest.revision: 8
ms.author: "sgroespe"
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
# How to: Renumber Document Numbers in Journals
To make sure that you do not receive posting errors because of the document number order, you can use the **Renumber Document Numbers** function before you post a journal.  
  
 In all journals that are based on the general journal, the **\($ T\_81\_7 Document No. $\)** field is editable so that you can specify different document numbers for different journal lines or the same document number for related journal lines.  
  
 If the **\($ T\_232\_7 No. Series $\)** field on the journal batch is filled, then the posting function in general journals requires that the document number on individual or grouped journal lines be in sequential order. To make sure that you do not receive posting errors because of the document number order, you can use the **Renumber Document Numbers** function before you post the journal. If related journal lines were grouped by document number before you used the function, they will remain grouped but may be assigned a different document number.  
  
 This function also works on filtered views.  
  
 Any renumbering of document numbers will respect related applications, such as a payment application that has been made from the document on the journal line to a vendor account. Accordingly, the **\($ T\_81\_48 Applies\-to ID $\)** and **\($ T\_81\_36 Applies\-to Doc. No. $\)** fields on the affected ledger entries may be updated.  
  
> [!NOTE]  
>  The following procedure is based on the **\($ N\_39 General Journal $\)** window, but applies to all other journals that are based on the general journal, such as the **\($ N\_256 Payment Journal $\)** window.  
  
### To renumber document numbers  
  
1.  In the **Search** box, enter **General Journals**, and then choose the related link.  
  
2.  When you are ready to post the journal, on the **Actions** tab, in the **Functions** group, choose **Renumber Document Numbers**.  
  
 Values in the **\($ T\_81\_7 Document No. $\)** field are changed, where required, so that the document number on individual or grouped journal lines are in sequential order. After documents are renumbered, you can proceed to post the journal.  
  
## See Also  
 [\($ T\_232\_7 No. Series $\)](assetId:///faad082a-a1a4-498f-82b0-e9c0eb124a58)   
 [\($ T\_81\_7 Document No. $\)](assetId:///772f606f-4b98-44fa-b294-7ace39854813)   
 [\($ N\_39 General Journal $\)](assetId:///a60a346f-f336-47bb-b046-55a1595e1555)   
 [Work with General Journals](../Finance/work-with-general-journals.md)