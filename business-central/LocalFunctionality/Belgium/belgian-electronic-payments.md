---
title: Belgian electronic payments
description: The electronic banking module in the Belgian version of Business Central enables users to process domestic, international, SEPA, and non-Euro SEPA electronic payments.
author: brentholtorf
ms.topic: article
ms.search.keywords: electronic banking, Belgian version, electronic payments, SEPA, non-Euro SEPA, domestic payments, international payments
ms.search.form: 2000006
ms.date: 04/01/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Belgian electronic payments

In the Belgian version of [!INCLUDE[prod_short](../../includes/prod_short.md)], you can make the following types of electronic payments:  

|Electronic payment|Description|  
|------------------------|---------------------------------------|  
|Domestic|A local financial institution process these payments in the local currency (LCY) for beneficiaries who have accounts that have a local financial institution. [!INCLUDE[prod_short](../../includes/prod_short.md)] verifies the validity of the bank account numbers.|  
|International|A local financial institution process these payments that are either in foreign currencies or in LCY for beneficiaries who have accounts that have foreign financial institutions. [!INCLUDE[prod_short](../../includes/prod_short.md)] verifies the validity of the bank account numbers.|  
|SEPA|These payments are in Euro and are processed in countries/regions that accept SEPA payments. [!INCLUDE[prod_short](../../includes/prod_short.md)] verifies the validity of the bank account numbers.|  
|Non-Euro SEPA|These payments are in currency other than Euro and made to a country/region outside the European Economic Association (EEA). [!INCLUDE[prod_short](../../includes/prod_short.md)] verifies the validity of the bank account numbers.|  

Because the standard for electronic payments is different for countries/regions, only financial institutions in Belgium can process electronic payments created in the Belgian version of [!INCLUDE[prod_short](../../includes/prod_short.md)]. The local financial institutions process the payment with the foreign institutions for international payments.  

> [!NOTE]  
> Credit memos can't be processed separately because payments must not have a negative balance. To process a credit memo, the credit memo must be added to one or more invoices by summarizing payments.  

Before you can make electronic payments, you must set up use electronic banking. Learn more in [Setup](belgian-electronic-banking.md#setup). You must also specify the relevant export protocols. Learn more in [Set Up Export Protocols](how-to-set-up-export-protocols.md).  

## Activate SEPA payments

[!INCLUDE [activate-sepa-payments](../includes/BENL/activate-sepa-payments.md)]

You can now make SEPA payments. Learn more in [Exporting Payments to a Bank File](../../finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#exporting-payments-to-a-bank-file). If you don't use the AC Banking 365 capability, you can export payment journal lines to a file. Learn more in [Export Payment Files](how-to-print-payment-files.md).  

## File non-Euro SEPA payments

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can file non-Euro SEPA payments with the bank. This is useful when you make payments to other countries/regions that don't use SEPA and for currencies other than the Euro.  

Before you can file a non-Euro SEPA payment, you must complete the following administration tasks:  

1. Set up a new export protocol for a non-Euro SEPA.  
1. In the **Country/Region** table, clear the **SEPA Allowed** field for each country that belongs to the EEA zone.  
1. In the **General Ledger Setup** page, verify that the **Currency Euro** field is blank, and that the **SEPA Non-Euro Export** field is selected.  
1. Verify that the vendor's **Preferred Bank Account** field in the **Vendor** table contains the IBAN and SWIFT code.  

## File a non-Euro SEPA payment  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **File Non Euro SEPA Payments**, and then choose the related link.  
1. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Journal Template Name**|Specify the general journal template for the non-Euro SEPA payment report.|  
    |**Journal Batch**|Specify the general journal batch for the non-Euro SEPA payment report.|  
    |**Post General Journal Lines**|Specify if you want to transfer the payment lines to the general ledger.|  
    |**Include Dimensions**|Enter the dimensions that you want to include in the non-Euro SEPA payment report. The option is available only if the **Summarize Gen. Jnl. Lines** field on the **Electronic Banking Setup** page is selected.|  
    |**Execution Date**|Enter an execution date if you want an execution date that differs from the posting date on the payment lines.|  
    |**File Name**|Enter the name of the file, including the drive and folder, to which you want to print the report.|  

## Correct payment lines

You must correct all errors before you can post the electronic payment lines. You can correct payment lines in the following ways.  

|Correction|Description|  
|----------------|---------------------------------------|  
|Add a payment journal line|If the payment journal already contains many lines and you want to add an additional line, you can enter the journal line manually. For example, if you want to reimburse a credit memo to a customer. These types of customer payments aren't suggested automatically by the **Suggest Vendor Payments** batch job.|  
|Edit a payment journal line|If you don't assign a bank account to the payment journal or if you don't specify a preferred bank account on the Vendor card, you have to manually enter this information on each journal line before posting the journal. If you specify a bank account for a vendor, the bank account is copied to all payment journal lines for that vendor. Learn more in [Setup](belgian-electronic-banking.md#setup).|  
|Delete a payment journal line|The **Suggest Vendor Payments** batch job creates payment suggestions for all vendors matching the specified criteria. If you want to prevent payment for a specific vendor ledger entry or vendor, you can delete the corresponding journal lines.|  

## Related information

- [Belgium Local Functionality](belgium-local-functionality.md)  
- [Belgian Electronic Banking](belgian-electronic-banking.md)  
- [Set Up Vendors for Automatic Payment Suggestions](how-to-set-up-vendors-for-automatic-payment-suggestions.md)  
- [Suggest Vendor Payments](../../payables-how-suggest-vendor-payments.md)  
- [Create Payment Journal Templates and Batches](how-to-create-payment-journal-templates-and-batches.md)  
- [Test Electronic Payments](how-to-test-electronic-payments.md)  
- [Print Payment Files](how-to-print-payment-files.md)  
