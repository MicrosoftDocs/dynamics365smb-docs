---
title: "How to: Set Up General Ledger Accounts for Invoice Rounding Differences"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "rounding, invoices"
ms.assetid: 063a16a6-12ec-44fa-b290-45be7d3ed62f
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
# How to: Set Up General Ledger Accounts for Invoice Rounding Differences
To use the automatic invoice rounding function, you must set up the general ledger account or accounts where rounding differences will be posted. Before you can do this, you must set up VAT product posting groups.  
  
### To set up general ledger accounts for invoice rounding differences  
  
1.  In the **Search** box, enter **Chart of Accounts**, and then choose the related link.  
  
2.  Set up the account in the **Chart of Accounts** window and name it **Invoice Rounding** or something similar. [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] will use the account name as text for invoices that are rounded.  
  
3.  In the **Gen. Posting Type** field, select \<Blank\>.  
  
4.  Leave the **VAT Bus. Posting Group** field blank.  
  
5.  Fill in the **VAT Prod. Posting Group** field. You may want to set up a new group code that can be used for invoice rounding.  
  
 Now you can assign the invoice rounding account to posting groups in the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**[Customer Posting Groups](DynamicsNAV:////runpage?Page=110)** window and the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**[Vendor Posting Groups](DynamicsNAV:////runpage?Page=111)** window.  
  
## See Also  
 [How to: Set Up Rounding Rules for the LCY](../Finance/how-to-set-up-rounding-rules-for-the-lcy.md)   
 [How to: Set Up Rounding Rules for Foreign Currency](../Finance/how-to-set-up-rounding-rules-for-foreign-currency.md)   
 [How to: Enable the Invoice Rounding Function](../Finance/how-to-enable-the-invoice-rounding-function.md)   
 [How to: Set Up VAT Product Posting Groups](../Finance/how-to-set-up-vat-product-posting-groups.md)