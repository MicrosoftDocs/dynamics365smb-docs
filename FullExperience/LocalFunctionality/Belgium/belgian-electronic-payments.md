---
title: "Belgian Electronic Payments"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "electronic payments, in Belgium"
  - "electronic payments, correcting payment lines"
ms.assetid: c9f0b743-4f66-4acc-99b5-e03ae2012924
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "fr-be"
  - "nl-be"
---
# Belgian Electronic Payments
In the electronic banking module in [!INCLUDE[nav_current_short](../../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_current_short_md.md)], you can make domestic, international, SEPA, and non\-Euro SEPA electronic payments.  
  
|Electronic payment|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
|------------------------|---------------------------------------|  
|Domestic|These payments are in the local currency \(LCY\) and are processed by a local financial institution for beneficiaries who have accounts that have a local financial institution. The validity of the bank account numbers will be verified by [!INCLUDE[nav_current_short](../../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_current_short_md.md)].|  
|International|These payments are either in foreign currencies or in LCY and are processed by a local financial institution for beneficiaries who have accounts that have foreign financial institutions. The validity of the bank account numbers will not be verified by [!INCLUDE[nav_current_short](../../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_current_short_md.md)].|  
|SEPA|These payments are in euro and are processed in countries\/regions that accept SEPA payments. The validity of the bank account numbers will be verified by [!INCLUDE[nav_current_short](../../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_current_short_md.md)].|  
|Non\-Euro SEPA|These payments are in currency other than euro and made to a country\/region outside the European Economic Association \(EEA\). The validity of the bank account numbers will be verified by [!INCLUDE[nav_current_short](../../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_current_short_md.md)].|  
  
 In electronic banking, because the standard for electronic payments is different for countries\/regions, electronic payments created in [!INCLUDE[nav_current_short](../../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_current_short_md.md)] can only be processed by financial institutions in Belgium. For international payments, the local financial institutions will then have to process the payment with the foreign institutions.  
  
> [!NOTE]  
>  Credit memos cannot be processed separately because payments must not have a negative balance. To process a credit memo, the credit memo must be added to one or more invoices by summarizing payments.  
  
 Before you can make electronic payments, you must set up use electronic banking in [!INCLUDE[nav_current_short](../../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_current_short_md.md)]. For more information, see [How to: Set Up Electronic Banking](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-electronic-banking.md).  
  
## Correcting Payment Lines  
 You must correct all errors before you can post the electronic payment lines. You can correct payment lines in the following ways.  
  
|Correction|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
|----------------|---------------------------------------|  
|Add a payment journal line|If the payment journal already contains many lines and you want to add an additional line, you can enter the journal line manually. For example, if you want to reimburse a credit memo to a customer. These types of customer payments are not suggested automatically by the **Suggest Vendor Payments** batch job.|  
|Edit a payment journal line|If you have not assigned a bank account to the payment journal or if you have not specified a preferred bank account on the Vendor card, you will have to manually enter this information on each journal line before posting the journal. If you specify a bank account for a vendor, the bank account will be copied to all payment journal lines for that vendor. For more information, see [How to: Set Up Electronic Banking](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-electronic-banking.md).|  
|Delete a payment journal line|The **Suggest Vendor Payments** batch job creates payment suggestions for all vendors matching the specified criteria. If you want to prevent payment for a specific vendor ledger entry or vendor, you can delete the corresponding journal lines.|  
  
 For more information, see [How to: Manage Electronic Payment Lines](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-manage-electronic-payment-lines.md).  
  
## See Also  
 [Belgian Electronic Banking](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/belgian-electronic-banking.md)   
 [How to: Set Up Electronic Banking](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-electronic-banking.md)   
 [How to: Set Up IBLC\-BLWI Transaction Codes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-iblc-blwi-transaction-codes.md)   
 [How to: Set Up Vendors for Automatic Payment Suggestions](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-vendors-for-automatic-payment-suggestions.md)   
 [How to: Generate Payment Suggestions](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-generate-payment-suggestions.md)   
 [How to: Create Payment Journal Templates and Batches](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-create-payment-journal-templates-and-batches.md)   
 [How to: Test Electronic Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-test-electronic-payments.md)   
 [How to: Manage Electronic Payment Lines](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-manage-electronic-payment-lines.md)   
 [How to: Print Payment Files](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-print-payment-files.md)