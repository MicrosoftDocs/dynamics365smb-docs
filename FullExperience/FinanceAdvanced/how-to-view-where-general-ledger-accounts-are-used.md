---
title: "How to: View Where General Ledger Accounts Are Used"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "chart of accounts, for general ledger"
ms.assetid: 96e9989a-4148-4709-8e2b-7944f0a6caab
caps.latest.revision: 7
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
# How to: View Where General Ledger Accounts Are Used
Sometimes you may want to see an overview of the setup tables that cause [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] to automatically post to a specific account. When you do the setup, you fill in setup tables, such as the posting group tables, to specify which general ledger accounts are used as posting accounts for which types of transactions. Later, you may want to see which setup tables contain references to a certain general ledger account.  
  
### To get an overview of where general ledger accounts are used  
  
1.  In the **Search** box, enter **Chart of Accounts**, and then choose the related link.  
  
2.  In the **Chart of Accounts** window, select the line with an account for which you want an overview. On the **Navigate** tab, in the **Account** group, choose **Where\-Used List**.  
  
     The **G\/L Account Where\-Used List** window shows every line that refers to the general ledger account in the following setup tables:  
  
     [Currency](assetId:///8718cd98-90eb-4fc2-974f-a25bd2d873d1)  
  
     [Customer Posting Group](../Topic/\($%20T_92%20Customer%20Posting%20Group%20$\).md)  
  
     [Vendor Posting Group](../Topic/\($%20T_93%20Vendor%20Posting%20Group%20$\).md)  
  
     [Job Posting Group](../Topic/\($%20T_208%20Job%20Posting%20Group%20$\).md)  
  
     [General Posting Setup](assetId:///8d1129f7-d16d-40a2-a351-8a1aed5953b3)  
  
     [Bank Account Posting Group](assetId:///b4a12ab6-0240-49f6-9d98-c561515d25fd)  
  
     [VAT Posting Setup](assetId:///5510a4f9-3ad3-461f-a53a-f3578c78a87f)  
  
     [FA Posting Group](../Topic/\($%20T_5606%20FA%20Posting%20Group%20$\).md)  
  
     [Inventory Posting Setup](../Topic/\($%20T_5813%20Inventory%20Posting%20Setup%20$\).md)  
  
     [Service Contract Account Group](../Topic/\($%20T_5973%20Service%20Contract%20Account%20Group%20$\).md)  
  
     [Gen. Journal Template](assetId:///eb60bf94-fc5b-442c-acb8-91df074d20d2)  
  
     [Gen. Journal Batch](assetId:///cbc7f5fe-ccd5-468c-bf25-ec1ebe2a3d12)  
  
     [Gen. Jnl. Allocation](assetId:///3888da16-0a70-4d4f-aef8-4a2d7c0b924b)  
  
     [FA Allocation](../Topic/\($%20T_5615%20FA%20Allocation%20$\).md)  
  
3.  Repeat the procedure for each relevant account.