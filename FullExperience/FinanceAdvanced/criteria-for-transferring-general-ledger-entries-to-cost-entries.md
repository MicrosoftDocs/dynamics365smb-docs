---
title: "Criteria for Transferring General Ledger Entries to Cost Entries"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "cost accounting, criteria for transferring"
ms.assetid: 0f6d83eb-0451-4847-9516-556d2e0a6686
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
# Criteria for Transferring General Ledger Entries to Cost Entries
It is important to understand the criteria for transferring general ledger entries to cost entries. During the transfer, the **Transfer GL Entries to CA** batch job uses the following criteria to determine if and how the general ledger entries are transferred.  
  
 General ledger entries are transferred if:  
  
-   The entries have dimension values corresponding to either a cost center or a cost object.  
  
-   The entries have dimension values that correspond to a cost center and a cost object. For these entries, the cost center takes precedence. This helps avoid a situation where a cost type appears in both a cost object and a cost center and is therefore counted twice in the statistics.  
  
-   The document number in the entries is empty, so it will appear with a document number of 0000 in the cost entries.  
  
-   The entries are transferred to a cost type that allows for combined entries and these entries are transferred as a combined entry either monthly or daily.  
  
 General ledger entries are not transferred if:  
  
-   The entries have dimension values that do not correspond to a cost center or a cost object.  
  
-   The entries have an amount of zero.  
  
-   The entries have a general ledger account that has been deleted.  
  
-   The entries have a general ledger account that is not of the type **Income Statement**.  
  
-   The entries have a general ledger account that is not assigned a cost type.  
  
-   The entries have a posting date before the **Starting Date for G\/L Transfer**.  
  
-   The entries have been posted with a closing date. These are typically entries that set back the balance of the income statement at the end of the year.  
  
## See Also  
 [How to: Transfer General Ledger Entries to Cost Entries](../Finance/how-to-transfer-general-ledger-entries-to-cost-entries.md)   
 [Transfer and Post Cost Entries](../Finance/transfer-and-post-cost-entries.md)   
 [About Cost Accounting](../Finance/about-cost-accounting.md)