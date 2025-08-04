---
title: Types of payment returns files [NO]
description: The Norwegian Business Central allows importing receipt returns and settlement returns payment files.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: receipt returns, settlement returns, payment files types, payment files, Norwegian version
ms.search.form: 15000000, 15000002, 15000004, 15000006, 15000007, 15000010
ms.date: 05/16/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Types of payment returns files in the Norwegian version

[!INCLUDE[prod_short](../../includes/prod_short.md)] includes two types of payment return files that can be imported:  

- Receipt returns  
- Settlement returns  

You can also choose to not use return files by selecting the **Return File Is Not In Use** field in the **Remittance Agreement** table. Learn more in [Set Up Remittance Agreements](how-to-set-up-remittance-agreements.md).  

## Receipt returns

The receipt return is received from the bank after you send the remittance file to the bank. When data is imported, information about the number of invoices that are received correctly, and the number that are received with error are displayed. After you import a receipt return, the status of the payments in the **Waiting Journal** table is set to **Approved**.  

> [!NOTE]  
> You may also receive a rejected return from the bank. If the remittance is rejected, you'll not receive the settlement return.  

## Settlement returns

The settlement return is received from the bank after the payment is executed. When data is imported, information about the number of settled invoices is displayed.  

The following events occur when the settlement return is imported:  

- Payment status in the **Waiting Journal** table is set to **Settled**.  
- Information is transferred from the **Waiting Journal** page to the payment journal.  
- A balancing account is created for each transaction.  
- Document numbers are inserted for each transaction.  

## Exchange rates by settlement

For a payment, the exchange rates are managed in the following ways:  

- Payment from an account in local currency - If a payment in another currency is from an account in LCY, the bank flags the settlement return with a warning about the exchange rate between LCY and the currency that is used as payment.  

- Payment from a currency account - If payment is made from a currency account, the exchange rate for this currency and LCY is used. This is because the bank doesn't inform the system about the exchange rate.  

## Warnings on settlement returns

When the settlement return is imported, warnings can occur. Payment journal lines with warnings are marked with a symbol. To view the information about the warning, you can open the **Settlement Info** page.  

## Related information

- [Electronic Payments to Vendors in Norway](electronic-payments-to-vendors-in-norway.md)
- [Set Up Remittance Agreements](how-to-set-up-remittance-agreements.md)
- [Create Remittance Accounts](how-to-create-remittance-accounts.md)
- [Set Up Vendors for Remittance](how-to-set-up-vendors-for-remittance.md)
- [Recipient Reference Codes](recipient-reference-codes.md)
- [Create Remittance Suggestions](how-to-create-remittance-suggestions.md)
- [Create Manual Remittance Payments](how-to-create-manual-remittance-payments.md)
- [Set Up Payment Line Information](how-to-set-up-payment-line-information.md)
- [Test Remittance Payments](how-to-test-remittance-payments.md)
- [Export Remittance Payments](how-to-export-remittance-payments.md)
- [Import Payment Return Data](how-to-import-payment-return-data.md)
- [Delete Remittance Payment Orders](how-to-delete-remittance-payment-orders.md)
- [Remittance Errors](remittance-errors.md)
- [View Remittance Error Codes](how-to-view-remittance-error-codes.md)
- [Cancel Payments](how-to-cancel-payments.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
