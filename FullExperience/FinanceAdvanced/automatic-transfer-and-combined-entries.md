---
title: "Automatic Transfer and Combined Entries"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "cost accounting, combined entries"
ms.assetid: 0446bcbe-8ba3-4500-855a-7225f9bec1ef
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
# Automatic Transfer and Combined Entries
In cost accounting, you can transfer general ledger entries to a cost type by using a combined posting. You can specify if a cost type receives combined entries in the **Combine Entries** field in the cost type definition. The following table describes the different options.  
  
|Combine entries|Description|  
|---------------------|-----------------|  
|None|Each general ledger entry is transferred individually to the corresponding cost type.|  
|Day|General ledger entries with the same posting date are transferred as one entry to the corresponding cost type.|  
|Month|All general ledger entries in the same calendar month are transferred as one entry to the corresponding cost type.|  
  
> [!IMPORTANT]  
>  If you have selected the **Auto Transfer from G\/L** check box in the **Cost Accounting Setup** window, [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] updates the cost accounting after every posting in the general ledger. Combined entries are not possible.  
  
## See Also  
 [How to: Transfer General Ledger Entries to Cost Entries](../Finance/how-to-transfer-general-ledger-entries-to-cost-entries.md)   
 [Criteria for Transferring General Ledger Entries to Cost Entries](../Finance/criteria-for-transferring-general-ledger-entries-to-cost-entries.md)   
 [Results of the Transfer](../Finance/results-of-the-transfer.md)   
 [Transfer and Post Cost Entries](../Finance/transfer-and-post-cost-entries.md)   
 [Cost Accounting Setup](assetId:///e96b49f0-9859-461b-a7c8-f4039281860a)