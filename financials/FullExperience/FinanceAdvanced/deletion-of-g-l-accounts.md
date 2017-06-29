---
title: "Deletion of G-L Accounts"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "chart of accounts, deleting"
ms.assetid: a146eae5-cfa7-402b-9f86-daeb7a1516d3
caps.latest.revision: 4
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
  - "en-my"
  - "en-nz"
  - "en-ph"
  - "en-sg"
  - "en-zw"
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
# Deletion of G-L Accounts
Before a G\/L account can be deleted, the following criteria must be met:  
  
 The balance on the account must be zero.  
  
 If there is a date in the **Allow G\/L Acc. Deletion Before** field in the **General Ledger Setup** window, the account must not have ledger entries on or after that date.  
  
 If there is a check mark in the **Check G\/L Account Usage** field in the **General Ledger Setup** window, then the account must not be used in any of the following setup tables:  
  
 Currency  
  
 Customer Posting Group  
  
 Vendor Posting Group  
  
 Job Posting Group  
  
 General Posting Setup  
  
 Bank Account Posting Group  
  
 VAT Posting Setup  
  
 FA Posting Group  
  
 Inventory Posting Setup  
  
 Service Contract Account Group  
  
 Gen. Journal Template  
  
 Gen. Journal Batch  
  
 Gen. Jnl. Allocation  
  
 FA Allocation  
  
## See Also  
 [How to: View Where General Ledger Accounts Are Used](../Finance/how-to-view-where-general-ledger-accounts-are-used.md)   
 General Ledger Setup   
 Allow G\/L Acc. Deletion Before   
 Check G\/L Account Usage