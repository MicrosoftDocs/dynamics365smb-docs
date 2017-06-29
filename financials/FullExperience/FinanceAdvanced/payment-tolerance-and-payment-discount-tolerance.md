---
title: "Payment Tolerance and Payment Discount Tolerance"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "payment discounts, tolerance"
  - "payment tolerance, about"
  - "tolerance, payment discounts"
  - "tolerance, payments"
ms.assetid: 3ed49e27-d0b1-4d9c-8454-57885a4e8269
caps.latest.revision: 8
ms.author: "edupont"
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
# Payment Tolerance and Payment Discount Tolerance
You can set up payment tolerance to close an invoice when the payment does not fully cover the amount on the invoice.  
  
## Payment Discount Tolerance  
 You can use payment discount tolerance to grant a payment discount after the payment discount date has passed.  
  
 If you accept a payment discount after the payment discount date, then it is always posted to either the payment discount account or a payment tolerance account.  
  
 You specify the method for posting payment discount tolerance in the **G\/L Setup** window.  
  
 For more information, see [How to: Set Up Tolerances](../Finance/how-to-set-up-tolerances.md).  
  
## Payment Tolerance  
 You can use payment tolerance so that every outstanding amount has a set maximum allowed payment tolerance. If the payment tolerance is met, then the payment amount is analyzed.  
  
-   If the payment amount is an underpayment, then the outstanding amount is fully closed by the underpayment. A detailed ledger entry is posted to the payment entry so that no remaining amount is left on the applied invoice entry.  
  
-   If the payment amount is an overpayment, then a new detailed ledger entry is posted to the payment entry so that no remaining amount is left on the payment entry.  
  
## Applying Payment Tolerance to Multiple Documents  
 A single document has the same payment tolerance whether it is applied on its own or with other documents. Acceptance of a late payment discount when you are applying payment tolerance to multiple documents automatically occurs for each document where the following rule is true:  
  
 payment discount date \< payment date on the selected entry \<\= payment tolerance date  
  
 This rule also applies to determine whether to display warnings when you apply payment tolerance to multiple documents. The payment discount tolerance warning is displayed for each entry that meets the date criteria.  
  
 You can choose to display a warning that is based on different tolerance situations.  
  
-   The first warning is for the payment discount tolerance. You are informed that you can accept a late payment discount. You can then choose whether to accept tolerance on the discount date.  
  
-   The second warning is for the payment tolerance. You are informed that all entries can be closed because the difference is in the sum of the maximum payment tolerance for the applied entries. You can then choose whether to accept tolerance on the payment amount.  
  
 For more information, see [How to: Enable or Disable Payment Tolerance Warnings](../Finance/how-to-enable-or-disable-payment-tolerance-warnings.md).  
  
## See Also  
 [How to: Set Up Tolerances](../Finance/how-to-set-up-tolerances.md)   
 [How to: Block Payment Tolerances for a Customer or a Vendor](../Finance/how-to-block-payment-tolerances-for-a-customer-or-a-vendor.md)   
 [How to: Enable or Disable Payment Tolerance Warnings](../Finance/how-to-enable-or-disable-payment-tolerance-warnings.md)   
 [\($ B\_34 Change Payment Tolerance $\)](../Topic/\($%20B_34%20Change%20Payment%20Tolerance%20$\).md)   
 [Example  \- Tolerance Calculations for Single Document](../Finance/example----tolerance-calculations-for-single-document.md)   
 [Example  \- Tolerance Calculations for Multiple Document](../Finance/example----tolerance-calculations-for-multiple-document.md)