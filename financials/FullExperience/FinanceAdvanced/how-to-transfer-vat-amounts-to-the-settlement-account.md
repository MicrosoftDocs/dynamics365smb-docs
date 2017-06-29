---
title: "How to: Transfer VAT Amounts to the Settlement Account"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "VAT, transferring to settlement accounts"
  - "settlement, transferring VAT"
ms.assetid: 8e12f4ab-2450-4890-a610-ecd41232febe
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
# How to: Transfer VAT Amounts to the Settlement Account
Transferring VAT amounts to the settlement account means that the purchase VAT account is credited and the sales VAT account is debited with the amounts calculated for the VAT statement period. The net amount is credited or debited, if the purchase VAT amount is larger to the VAT settlement account. You can post the settlement immediately or print a test report first.  
  
### To transfer VAT amounts to the settlement account  
  
1.  In the **Search** box, enter **VAT Statements**, and then choose the related link.  
  
2.  In the **VAT Statement** window, on the **Actions** tab, in the **Functions** group, choose **Calc. and Post VAT Settlement**.  
  
3.  On the **VAT Posting Setup** FastTab, you can enter codes in the **VAT Bus. Posting Group** and **VAT Prod. Posting Group** fields to select the entries to be processed. If you do not enter any codes, entries with all business group codes and product group codes are included.  
  
4.  On the **Options** FastTab, specify the conditions for the batch job. [!INCLUDE[bp_fieldhelp]()]  
  
5.  Choose the **Print** button to start the batch job.  
  
 If you print a test report to obtain approval before posting you must the select the **Post** field to run the batch job again.  
  
> [!IMPORTANT]  
>  If you calculate VAT on trade with the EU, you must also prepare a VIES declaration for the tax authorities.  
  
## See Also  
 [How to: Define VAT Statements](../Finance/how-to-define-vat-statements.md)   
 [How to: Print VAT Statements](../Finance/how-to-print-vat-statements.md)   
 [How to: Record VAT](../Finance/how-to-record-vat.md)