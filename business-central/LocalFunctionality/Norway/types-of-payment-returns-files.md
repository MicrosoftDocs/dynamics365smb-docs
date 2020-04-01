---
    title: Types of Payment Returns Files
    description: Norwegian enhancements include two types of payment return files that can be imported.

    services: project-madeira 
    documentationcenter: ''
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
# Types of Payment Returns Files
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] includes two types of payment return files that can be imported:  

- Receipt returns  
- Settlement returns  

You can also choose to not use return files by selecting the **Return File Is Not In Use** field in the **Remittance Agreement** table. For more information, see [Set Up Remittance Agreements](how-to-set-up-remittance-agreements.md).  

## Receipt Returns  
The receipt return is received from the bank after you have sent the remittance file to the bank. When data is imported, information about the number of invoices that are received correctly and the number that are received with error is displayed. After you import a receipt return, the status of the payments in the **Waiting Journal** table is set to **Approved**.  

> [!NOTE]  
>  You may also receive a rejected return from the bank. If the remittance is rejected, the settlement return will not be received.  

## Settlement Returns  
The settlement return is received from the bank after the payment is executed. When data is imported, information about the number of settled invoices is displayed.  

The following occurs when the settlement return is imported:  

- Payment status in the **Waiting Journal** table is set to **Settled**.  
- Information will be transferred from the **Waiting Journal** page to the payment journal.  
- A balancing account will be created for each transaction.  
- Document numbers will be inserted for each transaction.  

## Exchange Rates by Settlement  
For a payment, the exchange rates are managed in the following ways:  

- Payment from an account in local currency - If a payment in another currency is from an account in LCY, the bank will flag the settlement return with a warning about the exchange rate between LCY and the currency that is used as payment.  

- Payment from a currency account - If payment is made from a currency account, the exchange rate for this currency and LCY is used. This is because the bank does not inform the system about the exchange rate.  

## Warnings on Settlement Returns  
When the settlement return is imported, warnings can occur. Payment journal lines with warnings are marked with a symbol. To view the information about the warning, you can open the **Settlement Info** page.  

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
 [Import Payment Return Data](how-to-import-payment-return-data.md)   
 [Delete Remittance Payment Orders](how-to-delete-remittance-payment-orders.md)   
 [Remittance Errors](remittance-errors.md)   
 [View Remittance Error Codes](how-to-view-remittance-error-codes.md)   
 [Cancel Payments](how-to-cancel-payments.md)
