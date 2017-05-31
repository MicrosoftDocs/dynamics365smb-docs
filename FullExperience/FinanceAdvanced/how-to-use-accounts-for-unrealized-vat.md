---
title: "How to: Use Accounts for Unrealized VAT"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "VAT, unrealized"
  - "unrealized VAT, using accounts"
ms.assetid: 0756c764-097d-4854-acb0-9bd2e7b503b4
caps.latest.revision: 8
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
# How to: Use Accounts for Unrealized VAT
You can choose to have VAT amounts calculated and posted to a temporary general ledger account when an invoice is posted, and then posted to the correct general ledger account and included in VAT statements when the actual payment of the invoice is posted. Before you can do this, you must complete the VAT posting setup.  
  
### To use accounts for unrealized VAT  
  
1.  In the **Search** box, enter **General Ledger Setup**, and then choose the related link.  
  
2.  In the **\($ N\_118 General Ledger Setup $\)** window, on the **General** FastTab, select the **Unrealized VAT** check box.  
  
3.  Close the window.  
  
4.  In the **Search** box, enter **VAT Posting Setup**, and then choose the related link.  
  
5.  In the **\($ N\_472 VAT Posting Setup $\)** window, to view the options, choose the **Unrealized VAT Type** field, and then select an option that determines how unrealized VAT will be handled.  
  
6.  In the **Sales VAT Unreal. Account** field, enter the general ledger account for unrealized sales VAT.  
  
7.  In the **Purch. VAT Unreal. Account** field, enter the general ledger account for unrealized purchase VAT.  
  
> [!IMPORTANT]  
>  The first \<Blank\> option is the default value of the field. This means that unrealized VAT is not used. You can select one of the other options only if the **Unrealized VAT** field in the **General Ledger Setup** window is selected.  
  
## See Also  
 [How to: Set Up Combinations of VAT Business Posting Groups and VAT Product Posting Groups](../Finance/how-to-set-up-combinations-of-vat-business-posting-groups-and-vat-product-posting-groups.md)