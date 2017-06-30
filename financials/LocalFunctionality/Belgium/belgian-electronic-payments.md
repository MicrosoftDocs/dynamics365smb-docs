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
# Belgian Electronic Payments
In the electronic banking module in ADD INCLUDE<!--[!INCLUDE[nav_current_short](../../includes/nav_current_short_md.md)]-->, you can make domestic, international, SEPA, and non-Euro SEPA electronic payments.  
  
|Electronic payment|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../includes/bp_tabledescription_md.md)]-->|  
|------------------------|---------------------------------------|  
|Domestic|These payments are in the local currency \(LCY\) and are processed by a local financial institution for beneficiaries who have accounts that have a local financial institution. The validity of the bank account numbers will be verified by ADD INCLUDE<!--[!INCLUDE[nav_current_short](../../includes/nav_current_short_md.md)]-->.|  
|International|These payments are either in foreign currencies or in LCY and are processed by a local financial institution for beneficiaries who have accounts that have foreign financial institutions. The validity of the bank account numbers will not be verified by ADD INCLUDE<!--[!INCLUDE[nav_current_short](../../includes/nav_current_short_md.md)]-->.|  
|SEPA|These payments are in euro and are processed in countries\/regions that accept SEPA payments. The validity of the bank account numbers will be verified by ADD INCLUDE<!--[!INCLUDE[nav_current_short](../../includes/nav_current_short_md.md)]-->.|  
|Non-Euro SEPA|These payments are in currency other than euro and made to a country\/region outside the European Economic Association \(EEA\). The validity of the bank account numbers will be verified by ADD INCLUDE<!--[!INCLUDE[nav_current_short](../../includes/nav_current_short_md.md)]-->.|  
  
 In electronic banking, because the standard for electronic payments is different for countries\/regions, electronic payments created in ADD INCLUDE<!--[!INCLUDE[nav_current_short](../../includes/nav_current_short_md.md)]--> can only be processed by financial institutions in Belgium. For international payments, the local financial institutions will then have to process the payment with the foreign institutions.  
  
> [!NOTE]  
>  Credit memos cannot be processed separately because payments must not have a negative balance. To process a credit memo, the credit memo must be added to one or more invoices by summarizing payments.  
  
 Before you can make electronic payments, you must set up use electronic banking in ADD INCLUDE<!--[!INCLUDE[nav_current_short](../../includes/how-to-set-up-electronic-banking.md).  
  
## Correcting Payment Lines  
 You must correct all errors before you can post the electronic payment lines. You can correct payment lines in the following ways.  
  
|Correction|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../includes/bp_tabledescription_md.md)]-->|  
|----------------|---------------------------------------|  
|Add a payment journal line|If the payment journal already contains many lines and you want to add an additional line, you can enter the journal line manually. For example, if you want to reimburse a credit memo to a customer. These types of customer payments are not suggested automatically by the **Suggest Vendor Payments** batch job.|  
|Edit a payment journal line|If you have not assigned a bank account to the payment journal or if you have not specified a preferred bank account on the Vendor card, you will have to manually enter this information on each journal line before posting the journal. If you specify a bank account for a vendor, the bank account will be copied to all payment journal lines for that vendor. For more information, see [How to: Set Up Electronic Banking](../how-to-set-up-electronic-banking.md).|  
|Delete a payment journal line|The **Suggest Vendor Payments** batch job creates payment suggestions for all vendors matching the specified criteria. If you want to prevent payment for a specific vendor ledger entry or vendor, you can delete the corresponding journal lines.|  
  
 For more information, see [How to: Manage Electronic Payment Lines](../how-to-manage-electronic-payment-lines.md).  
  
## See Also  
 [Belgian Electronic Banking](../belgian-electronic-banking.md)   
 [How to: Set Up Electronic Banking](../how-to-set-up-electronic-banking.md)   
 [How to: Set Up IBLC-BLWI Transaction Codes](../how-to-set-up-iblc-blwi-transaction-codes.md)   
 [How to: Set Up Vendors for Automatic Payment Suggestions](../how-to-set-up-vendors-for-automatic-payment-suggestions.md)   
 [How to: Generate Payment Suggestions](../how-to-generate-payment-suggestions.md)   
 [How to: Create Payment Journal Templates and Batches](../how-to-create-payment-journal-templates-and-batches.md)   
 [How to: Test Electronic Payments](../how-to-test-electronic-payments.md)   
 [How to: Manage Electronic Payment Lines](../how-to-manage-electronic-payment-lines.md)   
 [How to: Print Payment Files](../how-to-print-payment-files.md)