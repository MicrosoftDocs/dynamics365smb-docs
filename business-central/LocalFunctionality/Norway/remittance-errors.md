---
    title: Remittance Errors
    description: Remittance errors for payments may occur when data is transferred and after payments have been sent to the bank. Both kinds of errors are reported on the Return Error page.

    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Remittance Errors
Remittance errors for payments may occur when data is transferred and after payments have been sent to the bank. Both kinds of errors are reported on the **Return Error** page.  

The remittance system handles all error codes which can be sent through the return files. It is not required to manually cancel payments rejected by the bank.  

## Types of Errors  
There are two types of remittance errors:  

- Transfer error  
- Rejection  

## Transfer Errors  
If errors occur during transfer and no return data is created, payments have not been received by the bank.  

If the payment file cannot be sent to the bank, you must cancel the payment order in the remittance system.  

## Rejections  
If there is an error or information is missing with a payment that was sent to the bank, the return will contain a rejection of the payment.  

> [!NOTE]  
>  Rejections vary from bank to bank. Contact your bank regarding how to handle rejection of payments.  

If there is a rejection, the error code from the bank and an explanation is displayed for the payment on the **Waiting Journal** page. You will have to handle the rejection based how the remittance agreement was set up. For more information, see [Set Up Remittance Agreements](how-to-set-up-remittance-agreements.md).  

## See Also  
 [Electronic Payments to Vendors in Norway](electronic-payments-to-vendors-in-norway.md)   
 [Set Up Remittance Agreements](how-to-set-up-remittance-agreements.md)   
 [Create Remittance Accounts](how-to-create-remittance-accounts.md)   
 [Set Up Vendors for Remittance](how-to-set-up-vendors-for-remittance.md)   
 [Recipient Reference Codes](recipient-reference-codes.md)   
 [Create Remittance Suggestions](how-to-create-remittance-suggestions.md)   
 [Create Manual Remittance Payments](how-to-create-manual-remittance-payments.md)   
 [Set Up Payment Line Information](how-to-set-up-payment-line-information.md)   
 [Test Remittance Payments](how-to-test-remittance-payments.md)   
 [Export Remittance Payments](how-to-export-remittance-payments.md)   
 [Types of Payment Returns Files](types-of-payment-returns-files.md)   
 [Import Payment Return Data](how-to-import-payment-return-data.md)   
 [Delete Remittance Payment Orders](how-to-delete-remittance-payment-orders.md)   
 [View Remittance Error Codes](how-to-view-remittance-error-codes.md)   
 [Cancel Payments](how-to-cancel-payments.md)
