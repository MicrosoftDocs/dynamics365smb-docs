---
title: Using the Payments and Reconciliations (DK) Extension | Microsoft Docs
description: This extension makes it easy to export files that are pre-formatted to meet bank requirements for electronic submissions.
services: project-madeira
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: extension, bank, formats
ms.date: 04/01/2020
ms.author: bholtorf

---

# The Payments and Reconciliations (DK) Extension
Make fast, error-free payments by exporting files that are formatted specifically for exchanges with your vendor or bank. These files speed up the payment and reconciliation processes, and eliminate errors that can happen when you manually enter the information on a bank website.  

This extension supports file formats for several Danish banks. When you export payment information to a file, the extension packages the data into the format that your bank requires. For example, the formats include Bankdata-V3, BEC, SDC, and FIK, which many different banks use, and some that are more specialized for certain banks, for example, Danske Bank and Nordea. The extension also includes some formats for importing and reconciling bank statements.  

> [!Note]
> To use the extension, you must know the format that your bank or vendor requires. Some banks or vendors provide this information on their websites; however, you might need to contact their customer service to get the information.  

## Supported Bank Formats
This extension can apply the following file formats for payment files:  

* BANKDATA-V3  
* BEC-INDLAND  
* BEC-CSV  
* DANSKEBANK-CMKV  
* DANSKEBANK-CMKXKSX  
* DANSKEBANK  
* FIK71  
* NORDEA-ERHVERV-CSV  
* NORDEA  
* NORDEA-UNITEL-V3  
* SDC  
* SDC-CSV  

## To set up the extension
There are a few steps to get started.  

* Allow payment data exports. To help protect your data, this is not readily available.  
* Set up purchase and payables so that you do not require external document numbers on invoices. If needed, you can use the reference number to refer to a specific invoice.  
* Specify the payment method for each vendor. Payment methods define how you pay invoices from the vendor. For example, Bank, Cash, Check, or Account.  
* Specify the type of format to use for each of your bank accounts. For example, NORDEA, DANSKEBANK, SDC, and so on.  

Additionally, you must assign vendors to a domestic **Gen. Bus. Posting Group** and a **Vendor Posting Group**. The Country/Region setting for the vendor must be Denmark (DK). For more information, see [Setting Up Posting Groups](finance-posting-groups.md).  

### To allow [!INCLUDE[d365fin](includes/d365fin_md.md)] to export payment data
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journal**, and then choose the related link.  
2. On the **Edit Payment Journal** page, choose the **Bank** batch.  
3. Choose the **Allow Payment Export** check box.  

### To specify a payment method for a vendor
The following table shows the combinations of FIK and GIRO payment methods that [!INCLUDE[d365fin](includes/d365fin_md.md)] supports.

||Type 01 | Type 04 | Type 71 | Type 73 |
|----|---|---|---|---|
|Giro Account No. or FIK Creditor No.? | Giro Account No. | Giro Account No. | FIK Creditor No. | FIK Creditor No.|
|Allows Message to Recipient? | Yes |No |No | Yes |
|Contains Payment Reference number? | No | Yes, 16 digits. | Yes, 15 digits. | No|

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.  
2. Open the card, expand the **Payments** tab, in the **Payment Method** field choose the payment method.  
3. Depending on your selection, you must complete other fields. See the table above for a description of the combinations.  

### To specify the format to use for a bank account
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.  
2. Open the card for the bank account.  
3. In the **Payment Export Format** field, choose the format for your export file.  

## Choosing the FIK or Giro payment information for vendor invoices
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and then choose the related link.
2. Choose the vendor. Remember, this must be a Danish vendor with an address in Denmark.
3. Create an invoice. The **Payment Method** and **Vendor Number** fields are filled in based on settings on the Vendor card. You can change them if you want.
4. In the **Payment Reference** field, enter the 15-digit number from the vendor invoice.  

    > [!Tip]
    > You only have to add the last 11 digits of the number. [!INCLUDE[d365fin](includes/d365fin_md.md)] will add four zeros to the beginning of the number.  

5. Post the invoice.

## To use the extension to export payment data
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journals**, and then choose the related link.  
2. Choose the **Suggest Vendor Payment Journals** action.  

    > [!Tip]
    > If you want to export only specific payments, use the options for filtering the data.  

3. If needed, you can add filters to export only specific payments.  
4. In the **Bank Payment Type** field, choose **Electronic Payment**.  
5. Choose the **Export** action.  

## See also
[Customizing Business Central for [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md)  
[Collect Payments with SEPA Direct Debit](finance-collect-payments-with-sepa-direct-debit.md)  
[Working with General Journals](ui-work-general-journals.md)  
