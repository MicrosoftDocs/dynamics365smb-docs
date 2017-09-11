---
    title: Remittance Errors | Microsoft Docs
    description: Remittance errors for payments may occur when data is transferred and after payments have been sent to the bank. Both kinds of errors are reported in the **Return Error** window.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Remittance Errors
Remittance errors for payments may occur when data is transferred and after payments have been sent to the bank. Both kinds of errors are reported in the **Return Error** window.  
  
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
  
 If there is a rejection, the error code from the bank and an explanation is displayed for the payment in the **Waiting Journal** window. You will have to handle the rejection based how the remittance agreement was set up. For more information, see [How to: Set Up Remittance Agreements](how-to-set-up-remittance-agreements.md).  
  
## See Also  
 [Electronic Payments to Vendors in Norway](electronic-payments-to-vendors-in-norway.md)   
 [How to: Set Up Remittance Agreements](how-to-set-up-remittance-agreements.md)   
 [How to: Create Remittance Accounts](how-to-create-remittance-accounts.md)   
 [How to: Set Up Vendors for Remittance](how-to-set-up-vendors-for-remittance.md)   
 [Recipient Reference Codes](recipient-reference-codes.md)   
 [How to: Create Remittance Suggestions](how-to-create-remittance-suggestions.md)   
 [How to: Create Manual Remittance Payments](how-to-create-manual-remittance-payments.md)   
 [How to: Set Up Payment Line Information](how-to-set-up-payment-line-information.md)   
 [How to: Test Remittance Payments](how-to-test-remittance-payments.md)   
 [How to: Export Remittance Payments](how-to-export-remittance-payments.md)   
 [Types of Payment Returns Files](types-of-payment-returns-files.md)   
 [How to: Import Payment Return Data](how-to-import-payment-return-data.md)   
 [How to: Delete Remittance Payment Orders](how-to-delete-remittance-payment-orders.md)   
 [How to: View Remittance Error Codes](how-to-view-remittance-error-codes.md)   
 [How to: Cancel Payments](how-to-cancel-payments.md)