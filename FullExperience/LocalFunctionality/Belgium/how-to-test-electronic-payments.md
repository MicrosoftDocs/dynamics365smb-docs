---
title: "How to: Test Electronic Payments"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "electronic payments, testing"
  - "payments, electronic"
ms.assetid: 6bb62d6c-19de-4070-8d01-548047351dcb
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "fr-be"
  - "nl-be"
---
# How to: Test Electronic Payments
After you have set up electronic banking and generated payment suggestions, you can test the payment journal lines for errors before posting them.  
  
 Some of the information that is validated includes:  
  
-   Bank accounts numbers are valid.  
  
-   Positive payment lines are present.  
  
-   If domestic and international payments are made from only one bank account.  
  
-   If only one bank account can be used for Isabel.  
  
-   If payment lines are in Euro for SEPA.  
  
-   If a number series has been defined for SEPA.  
  
 You can view any errors in the **\($ N\_2000006 Export Check Error Logs $\)** window.  
  
> [!IMPORTANT]  
>  You have to correct all errors before you can post the lines.  
  
### To test payment journal lines  
  
1.  In the **Search** box, enter **Payment Journals**, and then choose the related link.  
  
2.  In the **\($ N\_2000001\_1010026 Batch Name $\)** field, select the required journal batch.  
  
3.  In the **\($ N\_2000001\_1010028 Export Protocol $\)** field, select the export protocol.  
  
4.  Enter the payment journal line information. On the **Home** tab, in the **Process** group, choose **Check Payment Lines** to validate the payment journal lines. The validation that is performed on the journal lines depends on the type of check that is specified in the **\($ N\_2000005 Export Protocols $\)** window.  
  
## See Also  
 [Belgian Electronic Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/belgian-electronic-payments.md)   
 [How to: Set Up Vendors for Automatic Payment Suggestions](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-vendors-for-automatic-payment-suggestions.md)   
 [How to: Generate Payment Suggestions](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-generate-payment-suggestions.md)   
 [How to: Print Payment Files](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-print-payment-files.md)