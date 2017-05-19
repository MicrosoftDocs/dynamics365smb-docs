---
title: "How to: Create a VAT Combination Setup"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "VAT, setting up"
  - "VAT, combination setup"
  - "VAT product posting groups, setting up"
  - "VAT business posting groups, setting up"
ms.assetid: ce01b559-af0f-4092-b2dc-43f7ad863c3f
caps.latest.revision: 13
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
# How to: Create a VAT Combination Setup
This topic describes how to create a VAT combination setup.  
  
#### To create a VAT combination setup  
  
1.  In the **Search** box, enter **VAT Posting Setup**, and then choose the related link.  
  
2.  In the **\($ N\_472 VAT Posting Setup $\)** window, insert a new line, and then enter values in the **VAT Bus. Posting Group**, **VAT Prod. Posting Group**, and **VAT Identifier** fields.  
  
3.  On the **Actions** tab, in the **General** group, choose **Copy**.  
  
4.  In the **\($ B\_85 Copy \- VAT Posting Setup $\)** batch job, specify the **VAT Bus. Posting Group** and **VAT Prod. Posting Group** values of the line that you want to copy from.  
  
5.  In the **Copy** field, select one of the following values.  
  
    |[!INCLUDE[bp_optionsheading](../DesignAndEngineering/includes/bp_optionsheading_md.md)]|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |-------------------------------------|---------------------------------------|  
    |**All Fields**|Copies all fields|  
    |**Selected Fields**|Selects one or more of the following fields:<br /><br /> -   **VAT% etc.**<br />-   **Sales Accounts**<br />-   **Purchase Accounts**|  
  
6.  Choose the **OK** button to copy the information.  
  
 For more information, see [\($ B\_85 Copy \- VAT Posting Setup $\)](../Topic/\($%20B_85%20Copy%20-%20VAT%20Posting%20Setup%20$\).md).  
  
## See Also  
 [About Setting Up VAT](../Finance/about-setting-up-vat.md)   
 [How to: Enter Basic Information on Reverse Charge VAT for Purchases](../Finance/how-to-enter-basic-information-on-reverse-charge-vat-for-purchases.md)   
 [How to: Record VAT](../Finance/how-to-record-vat.md)   
 [How to: Revert VAT on Payment Discounts](../Finance/how-to-revert-vat-on-payment-discounts.md)   
 [How to: Set Up Codes for Import VAT](../Finance/how-to-set-up-codes-for-import-vat.md)   
 [How to: Set Up General Ledger Accounts for Invoice Rounding Differences](../Finance/how-to-set-up-general-ledger-accounts-for-invoice-rounding-differences.md)   
 [How to: Use Accounts for Unrealized VAT](../Finance/how-to-use-accounts-for-unrealized-vat.md)   
 [\($ N\_472 VAT Posting Setup $\)](assetId:///a96dd9fe-bfcb-46d8-874f-1046a0dcc1f7)   
 [\($ B\_85 Copy \- VAT Posting Setup $\)](../Topic/\($%20B_85%20Copy%20-%20VAT%20Posting%20Setup%20$\).md)