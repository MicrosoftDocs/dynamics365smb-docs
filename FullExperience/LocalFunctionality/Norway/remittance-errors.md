---
title: "Remittance Errors"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "remittance, errors"
ms.assetid: f14eb656-c642-4104-b856-f711d5664ce1
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "nb-no"
---
# Remittance Errors
Remittance errors for payments may occur when data is transferred and after payments have been sent to the bank. Both kinds of errors are reported in the **\($ N\_15000013 Return Error $\)** window.  
  
 The remittance system handles all error codes which can be sent through the return files. It is not required to manually cancel payments rejected by the bank.  
  
## Types of Errors  
 There are two types of remittance errors:  
  
-   Transfer error  
  
-   Rejection  
  
### Transfer Errors  
 If errors occur during transfer and no return data is created, payments have not been received by the bank.  
  
 If the payment file cannot be sent to the bank, you must cancel the payment order in the remittance system.  
  
### Rejections  
 If there is an error or information is missing with a payment that was sent to the bank, the return will contain a rejection of the payment.  
  
> [!NOTE]  
>  Rejections vary from bank to bank. Contact your bank regarding how to handle rejection of payments.  
  
 If there is a rejection, the error code from the bank and an explanation is displayed for the payment in the **\($ N\_15000005 Waiting Journal $\)** window. You will have to handle the rejection based how the remittance agreement was set up. For more information, see [How to: Set Up Remittance Agreements](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-set-up-remittance-agreements.md).  
  
## See Also  
 [Electronic Payments to Vendors in Norway](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/electronic-payments-to-vendors-in-norway.md)   
 [How to: Set Up Remittance Agreements](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-set-up-remittance-agreements.md)   
 [How to: Create Remittance Accounts](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-create-remittance-accounts.md)   
 [How to: Set Up Vendors for Remittance](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-set-up-vendors-for-remittance.md)   
 [Recipient Reference Codes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/recipient-reference-codes.md)   
 [How to: Create Remittance Suggestions](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-create-remittance-suggestions.md)   
 [How to: Create Manual Remittance Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-create-manual-remittance-payments.md)   
 [How to: Set Up Payment Line Information](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-set-up-payment-line-information.md)   
 [How to: Test Remittance Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-test-remittance-payments.md)   
 [How to: Export Remittance Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-export-remittance-payments.md)   
 [Types of Payment Returns Files](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/types-of-payment-returns-files.md)   
 [How to: Import Payment Return Data](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-import-payment-return-data.md)   
 [How to: Delete Remittance Payment Orders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-delete-remittance-payment-orders.md)   
 [How to: View Remittance Error Codes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-view-remittance-error-codes.md)   
 [How to: Cancel Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-cancel-payments.md)