---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# How to: Cancel Payments
ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> includes Norwegian enhancements that allow you to cancel payments. If the payment has been sent to the bank, the bank must be contacted to cancel the remittance that they received.  
  
-   A payment order can be canceled if the payments are not received by the bank and a new remittance must be made. You can also cancel a payment order if you do not want to transfer the payments to the bank, for example if the payments are incorrect. Only open payment orders can be canceled.  
  
-   An individual payment can be canceled if the payment cannot be processed by the bank and a new remittance has to be made. You can also cancel a payment if you do not want to process the payment. Settled payments cannot be canceled.  
  
### To cancel a payment order  
  
1.  In the **Search** box, enter **Remittance Payment Order**, and then choose the related link.  
  
2.  Select the payment order, and on the **Navigate** tab, in the **Payment order** group, choose **Export**, and then select **Cancel payment order**.  
  
3.  Choose the **Yes** button.  
  
### To cancel a payment  
  
1.  In the **Search** box, enter **Waiting Journal**, and then choose the related link.  
  
2.  Select the payment, and on the **Navigate** tab, in the **Waiting Journal** group, choose **Cancel Payment**.  
  
3.  Choose the **Yes** button.  
  
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
 [Remittance Errors](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/remittance-errors.md)   
 [How to: View Remittance Error Codes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-view-remittance-error-codes.md)