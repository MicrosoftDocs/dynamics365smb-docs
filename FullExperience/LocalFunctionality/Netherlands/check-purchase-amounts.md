---
title: "Check Purchase Amounts"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "purchase amounts, validating"
  - "purchase amounts, checking"
ms.assetid: 9bee732a-1879-430a-9de1-785f6c1daa5c
caps.latest.revision: 9
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "nl-nl"
---
# Check Purchase Amounts
Before posting a purchase invoice or credit memo, the program checks if the 'amount including VAT' and the 'VAT amount' stated on the purchase document is equal to the total amount of the inserted purchase lines. To do this, the [\($ T\_38\_11301 Doc. Amount Incl. VAT $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-t_38_11301-doc.-amount-incl.-vat-$-.md) and [\($ T\_38\_11302 Doc. Amount VAT $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-t_38_11302-doc.-amount-vat-$-.md) fields must be filled in on the [\($ N\_51 Purchase Invoice $\)](../Topic/\($%20N_51%20Purchase%20Invoice%20$\).md) or [\($ N\_52 Purchase Credit Memo $\)](../Topic/\($%20N_52%20Purchase%20Credit%20Memo%20$\).md) window.  
  
 In case there is only one purchase line or in case all lines are subject to the same VAT %, the correct **\($ T\_38\_11302 Doc. Amount VAT Field $\)** will be calculated automatically when you have inserted the purchase lines and the **\($ T\_38\_11301 Doc. Amount Incl. VAT Field $\)**. In case several lines exist with different VAT percentages, the **\($ T\_38\_11302 Doc. Amount VAT Field $\)** must be changed manually.  
  
 Default the program will check the purchase document total amounts, but you can switch it off by removing the check mark in the field [\($ T\_312\_11320 Check Doc. Total Amounts $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-t_312_11320-check-doc.-total-amounts-$-.md) on the [\($ N\_460 Purchases & Payables Setup $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-n_460-purchases-payables-setup-window-$-.md) window.  
  
 To determine the reason of the difference between the document total amounts and the total amounts of the inserted purchase lines, you have the possibility to let the program calculate the total amount, total base amount, total VAT amount and total amount including VAT of the inserted purchase lines and show them at the bottom of the purchase invoice or purchase credit memo window.  
  
 Default the program will not show these total amounts, but you can switch it on by inserting a check mark in the field [\($ T\_312\_11312 Show Totals on Purch. Inv.\-CM. $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-t_312_11312-show-totals-on-purch.-inv.-cm.-$-.md) on the [\($ N\_460 Purchases & Payables Setup $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-n_460-purchases-payables-setup-window-$-.md) window.  
  
> [!NOTE]  
>  If you activate this field, totals on all purchase invoices and credit memos must be recalculated. This can be a time\-consuming process depending on the number of documents that must be recalculated. You can not activate this field in case purchase invoices and\/or credit memos exist without any purchase lines or in case you have purchase invoices and\/or purchase credit memos with no quantity specified on the lines.  
  
## See Also  
 [How to: Set Up Validation of Purchase Amounts](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/how-to-set-up-validation-of-purchase-amounts.md)