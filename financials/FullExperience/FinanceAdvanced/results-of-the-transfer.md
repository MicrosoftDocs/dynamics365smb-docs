---
title: "Results of the Transfer"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "cost accounting, results"
ms.assetid: c57ad796-ad42-4292-b806-5c918d970b67
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
# Results of the Transfer
During the transfer of general ledger entries to cost entries, FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] --> --> --> --> --> --> creates connections in the entries in the **G\/L Entry** table, the **Cost Entry** table, and the **Cost Register** table to make it possible to trace the connections between cost entries and general ledger entries.  
  
## General Ledger Entries  
 For each general ledger entry that is transferred to cost accounting, [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] fills the cost **Entry No.** field.  
  
## Cost Entries  
 For each cost entry, [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] saves the entry number of the corresponding general ledger entry in the **G\/L Entry No.** field in the **Cost Entry** table.  
  
 For combined cost entries, [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] saves the entry number of the last general ledger entry, which is the entry with the highest entry number.  
  
 The **G\/L Account** field in the **Cost Entry** table contains the number of the general ledger account that the cost entry came from.  
  
 For single cost entries, [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] transfers the posting text from the general ledger entry to the **Description** text field. For combined entries, the text field shows these entries are transferred as combined entries. For example, for a combined entry for the month of October in 2013, the text can be **Combined Entries, October 2013**.  
  
## Cost Register  
 In the **Cost Register** table, [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] creates an entry with the source transfer from general ledger. The entry records the first and last entry numbers of the general ledger entries that are transferred, in addition to the first and last entry numbers of the cost entries that are created.  
  
## See Also  
 [How to: Transfer General Ledger Entries to Cost Entries](../Finance/how-to-transfer-general-ledger-entries-to-cost-entries.md)   
 [Criteria for Transferring General Ledger Entries to Cost Entries](../Finance/criteria-for-transferring-general-ledger-entries-to-cost-entries.md)   
 [Automatic Transfer and Combined Entries](../Finance/automatic-transfer-and-combined-entries.md)   
 [Transfer and Post Cost Entries](../Finance/transfer-and-post-cost-entries.md)   
 Cost Accounting Setup