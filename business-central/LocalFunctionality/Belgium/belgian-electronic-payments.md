---
title: Belgian Electronic Payments
description: In the electronic banking module in the Belgian version of Business Central, you can make domestic, international, SEPA, and non-Euro SEPA electronic payments.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.author: sgroespe

---
# Belgian Electronic Payments
In the electronic banking module in [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can make domestic, international, SEPA, and non-Euro SEPA electronic payments.  

|Electronic payment|Description|  
|------------------------|---------------------------------------|  
|Domestic|These payments are in the local currency (LCY) and are processed by a local financial institution for beneficiaries who have accounts that have a local financial institution. The validity of the bank account numbers will be verified by [!INCLUDE[d365fin](../../includes/d365fin_md.md)].|  
|International|These payments are either in foreign currencies or in LCY and are processed by a local financial institution for beneficiaries who have accounts that have foreign financial institutions. The validity of the bank account numbers will not be verified by [!INCLUDE[d365fin](../../includes/d365fin_md.md)].|  
|SEPA|These payments are in euro and are processed in countries/regions that accept SEPA payments. The validity of the bank account numbers will be verified by [!INCLUDE[d365fin](../../includes/d365fin_md.md)].|  
|Non-Euro SEPA|These payments are in currency other than euro and made to a country/region outside the European Economic Association (EEA). The validity of the bank account numbers will be verified by [!INCLUDE[d365fin](../../includes/d365fin_md.md)].|  

 In electronic banking, because the standard for electronic payments is different for countries/regions, electronic payments created in [!INCLUDE[d365fin](../../includes/d365fin_md.md)] can only be processed by financial institutions in Belgium. For international payments, the local financial institutions will then have to process the payment with the foreign institutions.  

> [!NOTE]  
>  Credit memos cannot be processed separately because payments must not have a negative balance. To process a credit memo, the credit memo must be added to one or more invoices by summarizing payments.  

Before you can make electronic payments, you must set up use electronic banking in [!INCLUDE[d365fin](../../includes/d365fin_md.md)].  

## Correcting Payment Lines  
You must correct all errors before you can post the electronic payment lines. You can correct payment lines in the following ways.  

|Correction|Description|  
|----------------|---------------------------------------|  
|Add a payment journal line|If the payment journal already contains many lines and you want to add an additional line, you can enter the journal line manually. For example, if you want to reimburse a credit memo to a customer. These types of customer payments are not suggested automatically by the **Suggest Vendor Payments** batch job.|  
|Edit a payment journal line|If you have not assigned a bank account to the payment journal or if you have not specified a preferred bank account on the Vendor card, you will have to manually enter this information on each journal line before posting the journal. If you specify a bank account for a vendor, the bank account will be copied to all payment journal lines for that vendor. For more information, see [Set Up Electronic Banking](how-to-set-up-electronic-banking.md).|  
|Delete a payment journal line|The **Suggest Vendor Payments** batch job creates payment suggestions for all vendors matching the specified criteria. If you want to prevent payment for a specific vendor ledger entry or vendor, you can delete the corresponding journal lines.|  

For more information, see [Manage Electronic Payment Lines](how-to-manage-electronic-payment-lines.md).  

## See Also  
[Belgium Local Functionality](belgium-local-functionality.md)  
[Belgian Electronic Banking](belgian-electronic-banking.md)   
[Set Up Electronic Banking](how-to-set-up-electronic-banking.md)   
[Set Up IBLC-BLWI Transaction Codes](how-to-set-up-iblc-blwi-transaction-codes.md)   
[Set Up Vendors for Automatic Payment Suggestions](how-to-set-up-vendors-for-automatic-payment-suggestions.md)   
[Generate Payment Suggestions](how-to-generate-payment-suggestions.md)   
[Create Payment Journal Templates and Batches](how-to-create-payment-journal-templates-and-batches.md)   
[Test Electronic Payments](how-to-test-electronic-payments.md)   
[Manage Electronic Payment Lines](how-to-manage-electronic-payment-lines.md)   
[Print Payment Files](how-to-print-payment-files.md)
