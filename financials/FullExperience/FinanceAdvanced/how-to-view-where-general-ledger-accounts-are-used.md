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
Sometimes you may want to see an overview of the setup tables that cause FIX INCLUDE HERE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] --> to automatically post to a specific account. When you do the setup, you fill in setup tables, such as the posting group tables, to specify which general ledger accounts are used as posting accounts for which types of transactions. Later, you may want to see which setup tables contain references to a certain general ledger account.  
  
### To get an overview of where general ledger accounts are used  
  
1.  In the **Search** box, enter **Chart of Accounts**, and then choose the related link.  
  
2.  In the **Chart of Accounts** window, select the line with an account for which you want an overview. On the **Navigate** tab, in the **Account** group, choose **Where\-Used List**.  
  
     The **G\/L Account Where\-Used List** window shows every line that refers to the general ledger account in the following setup tables:  
  
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
  
3.  Repeat the procedure for each relevant account.