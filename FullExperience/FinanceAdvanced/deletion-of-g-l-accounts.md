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
  
 If there is a date in the **\($ T\_98\_97 Allow G\/L Acc. Deletion Before $\)** field in the **\($ N\_118 General Ledger Setup $\)** window, the account must not have ledger entries on or after that date.  
  
 If there is a check mark in the **\($ T\_98\_98 Check G\/L Account Usage $\)** field in the **\($ N\_118 General Ledger Setup $\)** window, then the account must not be used in any of the following setup tables:  
  
 [\($ T\_4 Currency $\)](assetId:///8718cd98-90eb-4fc2-974f-a25bd2d873d1)  
  
 [\($ T\_92 Customer Posting Group $\)](../Topic/\($%20T_92%20Customer%20Posting%20Group%20$\).md)  
  
 [\($ T\_93 Vendor Posting Group $\)](../Topic/\($%20T_93%20Vendor%20Posting%20Group%20$\).md)  
  
 [\($ T\_208 Job Posting Group $\)](../Topic/\($%20T_208%20Job%20Posting%20Group%20$\).md)  
  
 [\($ T\_252 General Posting Setup $\)](assetId:///8d1129f7-d16d-40a2-a351-8a1aed5953b3)  
  
 [\($ T\_277 Bank Account Posting Group $\)](assetId:///b4a12ab6-0240-49f6-9d98-c561515d25fd)  
  
 [\($ T\_325 VAT Posting Setup $\)](assetId:///5510a4f9-3ad3-461f-a53a-f3578c78a87f)  
  
 [\($ T\_5606 FA Posting Group $\)](../Topic/\($%20T_5606%20FA%20Posting%20Group%20$\).md)  
  
 [\($ T\_5813 Inventory Posting Setup $\)](../Topic/\($%20T_5813%20Inventory%20Posting%20Setup%20$\).md)  
  
 [\($ T\_5973 Service Contract Account Group $\)](../Topic/\($%20T_5973%20Service%20Contract%20Account%20Group%20$\).md)  
  
 [\($ T\_80 Gen. Journal Template $\)](assetId:///eb60bf94-fc5b-442c-acb8-91df074d20d2)  
  
 [\($ T\_232 Gen. Journal Batch $\)](assetId:///cbc7f5fe-ccd5-468c-bf25-ec1ebe2a3d12)  
  
 [\($ T\_221 Gen. Jnl. Allocation $\)](assetId:///3888da16-0a70-4d4f-aef8-4a2d7c0b924b)  
  
 [\($ T\_5615 FA Allocation $\)](../Topic/\($%20T_5615%20FA%20Allocation%20$\).md)  
  
## See Also  
 [How to: View Where General Ledger Accounts Are Used](../Finance/how-to-view-where-general-ledger-accounts-are-used.md)   
 [\($ N\_118 General Ledger Setup $\)](assetId:///40b9235c-b0d7-4a9f-9ecf-6dc97655309b)   
 [\($ T\_98\_97 Allow G\/L Acc. Deletion Before $\)](assetId:///0eddc6ee-5268-4ff9-891e-3cdc0fa06b1a)   
 [\($ T\_98\_98 Check G\/L Account Usage $\)](assetId:///9dd5b667-9aa5-44fa-be2b-ed3005667d9d)