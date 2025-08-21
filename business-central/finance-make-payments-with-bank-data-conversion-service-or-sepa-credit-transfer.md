---
title: Make payments with AMC banking (US) or SEPA credit transfer (EU)
description: Process payments to your vendors by exporting a file (EFT) together with the payment information from the journal lines.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.search.form: 256, 1205, 1206, 1209, 10810, 10811
ms.date: 08/26/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Make payments with the AMC banking 365 fundamentals extension or SEPA credit transfer

On the **Payment Journals** page, you can process payments to your vendors by exporting a file together with the payment information from the journal lines. You can then upload the file to your electronic bank where the related money transfers are processed. [!INCLUDE[prod_short](includes/prod_short.md)] supports the SEPA Credit Transfer format, but in your country/region, other formats for electronic payments might be available.

> [!NOTE]
> In the generic version of [!INCLUDE[prod_short](includes/prod_short.md)], a global provider of services to convert bank data to any file format that your bank requires is set up and connected. In North American versions, the same service can be used to send payment files as electronic funds transfer (EFT), for example the commonly used Automated Clearing House (ACH) network, however with a slightly different process. See step 6 in [To export payments to a bank file](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#to-export-payments-to-a-bank-file).  

 To enable SEPA credit transfers, you must first set up a bank account, a vendor, and the general journal batch that the payment journal is based on. You then prepare payments to vendors by automatically filling the **Payment Journals** page with due payments with specified posting dates.  

After you verify that the bank processed the payments, you can post the payment journal lines.  

## Setting up the AMC Banking 365 Fundamentals extension

Activate the AMC Banking 365 Fundamentals extension to:

* Convert bank statement files to a format that you can import.
* Convert your exported payment files to the format that your bank requires.

For more information, see [Use the AMC Banking 365 Fundamentals extension](ui-extensions-amc-banking.md).

## Setting up SEPA credit transfer

From the **Payment Journals** page, you can export payments to a file for upload to your electronic bank for processing of the related money transfers. [!INCLUDE[prod_short](includes/prod_short.md)] supports the SEPA Credit Transfer format, but in your country/region, other formats for electronic payments might be available.  

To be able export of a bank file format that isn't supported out of the box in [!INCLUDE[prod_short](includes/prod_short.md)], you can set up a data exchange definition. For more information, see [Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md).  

Before you can process payment electronically by exporting payment files in the SEPA Credit Transfer format, you must perform the following setup steps:  

* Set up the bank account in question to handle the SEPA Credit Transfer format  
* Set up vendor cards to process payments by exporting files in the SEPA Credit Transfer format  
* Set up the related general journal batch to enable payment export from the **Payment Journals** page  
* Connect the data exchange definition for one or more payment types with the relevant payment method or methods  

> [!NOTE]
> Business Central supports both SEPA format CT pain.001.001.03 and CT pain.001.001.09. You can choose any format on the **Bank Account Card** page.  

> [!TIP]
> This article applies to the generic version of [!INCLUDE [prod_short](includes/prod_short.md)]. In your country or region, additional required fields may have been added to the various pages. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

### To set up a bank account for SEPA Credit Transfer

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Bank Accounts**, and then choose the related link.  
2. Choose the bank account from which you export payment files in the SEPA Credit Transfer format.
3. On the **General** FastTab, in the **Credit Transfer Msg. Nos.** field, choose a number series from which numbers are assigned to SEPA credit transfer entries.
4. On the **Communication** FastTab, enter address and contact information for the bank. 

   > [!NOTE]
   > You must fill in the **Country/Region Code** field. If the field is blank, you can't export payments for the account. Also, the country/region must have a valid ISO Code.

5. On the **Posting** FastTab, in the **Currency Code** field, specify the currency for the bank account.  

   > [!NOTE]  
   > The **Currency Code** field must be set to **EUR**, because SEPA credit transfers can only be made in the EURO currency.  

6. On the **Transfer** FastTab, in the **Payment Export Format** field, choose the SEPA format you want to use.  
7. In the **IBAN** field, specify the international bank account number for the account.  

### To set up a vendor card for SEPA Credit Transfer

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Vendors**, and then choose the related link.  
2. Open the card of the vendor you pay electronically using export payment files in the SEPA Credit Transfer format.  
3. On the **Payments** FastTab, in the **Payment Method Code** field, choose **BANK**.  
4. In the **Preferred Bank Account** field, choose the bank to which the money transfers when it's processed by your electronic bank.  

    If you don't have a bank account set up for this vendor, you can do so now. For more information, see [To set up vendor bank accounts for export of bank files](bank-how-setup-bank-accounts.md#to-set-up-vendor-bank-accounts-for-export-of-bank-files). The value in the **Preferred Bank Account** field is copied to the **Recipient Bank Account** field on the **Payment Journal** page.  

### To set the payment journal up to export payment files

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Payment Journals**, and then choose the related link.  
2. In the **Batch Name** field, choose the drop\-down button.  
3. On the **General Journal Batches** page, choose the **Edit List** action.  
4. On the line for the payment journal that you use to export payments, select the **Allow Payment Export** checkbox.  

### To connect the data exchange definition for one or more payment types with the relevant payment method or methods

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Payment Methods**, and then choose the related link.  
2. On the **Payment Methods** page, select the payment method that is used to export payments from, and then choose the **Pmt. Export Line Definition** field.  
3. On the **Pmt. Export Line Definitions** page, select the code that you specified in the **Code** field on the **Line Definitions** FastTab in step 4 in the "To describe the formatting of lines and columns in the file" section in the [Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md) procedure.  

## Preparing the payment journal

Fill the payment journal with lines for due payments to vendors, with the option to insert posting dates based on the due date of the related purchase documents. For more information, see [Managing Payables](payables-manage-payables.md).

## Exporting payments to a bank file

When you're ready to make payments to your vendors, or reimbursements to your employees, you can export a file with the payment information on the lines on the **Payment Journals** page. You can then upload the file to your bank to process the related money transfers.

In the generic version of [!INCLUDE[prod_short](includes/prod_short.md)], the AMC Banking 365 Fundamentals extension is available. In North American versions, the same extension can be used to send payment files as electronic funds transfer (EFT), however with a slightly different process. See step 6 in [To export payments to a bank file](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#to-export-payments-to-a-bank-file).

> [!NOTE]  
> Before you can export payment files from the payment journal, you must specify the electronic format for the involved bank account, and you must enable the AMC Banking 365 Fundamentals extension. For more information, see [Set Up Bank Accounts](bank-how-setup-bank-accounts.md) and [Use the AMC Banking 365 Fundamentals extension](ui-extensions-amc-banking.md). In addition, you must select the **Allow Payment Export** check box on the **General Journal Batches** page. For more information, see [Work with General Journals](ui-work-general-journals.md).  

Use the **Credit Transfer Registers** page to view the payment files that exported from the payment journal. From this page, you can also re-export payment files if there were technical errors or file changes. Note, however, that exported EFT files aren't shown in this page and can't be re-exported.  

### To export payments to a bank file

The following steps describe how to pay a vendor by check. The steps are similar to refund a customer by check.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Payment Journals**, and then choose the related link.
2. Fill in the payment journal lines. For more information, see [Record Payments and Refunds](payables-how-post-payments-refunds.md).

    > [!NOTE]
    > If you are using EFT, you must select either **Electronic Payment** or **Electronic Payment–IAT** in the **Bank Payment Type** field. Different file export services and their formats require different setup values on the **Bank Account Card** and **Vendor Bank Account Card** pages. You will be informed about wrong or missing setup values as you try to export the file.
    >
    > The EFT feature can only be used for bank accounts in the local currency. It cannot be used with a foreign currency, indicated by a value in the **Currency Code** field. (Blank field value means local currency.)

3. After you fill in all payment journal lines, choose the **Export** action.
4. On the **Export Electronic Payments** page, fill in the fields as necessary.

    Error messages show in the **Payment File Errors** FactBox, where you can also choose an error message to access more details. You must resolve all errors before you can export the payment file.

    > [!TIP]  
    > When you use the AMC Banking 365 Fundamentals extension, a common error message states that the bank account number does not have the length that your bank requires. To avoid or resolve the error, you must remove the value in the **IBAN** field on the **Bank Account Card** page and then, in the **Bank Account No.** field, enter a bank account number in the format that your bank requires.

5. On the **Save As** page, specify the location that the file is exported to, and then choose **Save**.

    > [!NOTE]  
    > If you are using EFT, save the resulting vendor remittance form as a Word document or select to have it emailed directly to the vendor. The payments are now added to the **Generate EFT File** page from where you can generate multiple payment orders together to save transmission cost. For more information, see the following steps.
6. On the **Payment Journals** page, choose the **Generate EFT File** action.

    On the **Generate EFT File** page, the **Lines** FastTab shows all EFT payments that you exported from the payment journal for a bank account but aren't yet generated.
7. Choose the **Generate EFT File** action to export one file for all the EFT payments.
8. On the **Save As** page, specify the location that the file is exported to, and then choose **Save**.

The bank payment file is exported to the location you specified. You can upload it to your electronic bank account and make the actual payments. Then you can post the exported payment journal lines.

### To plan when to post exported payments

If you don't want to post a payment journal line for an exported payment, you can just delete the journal line. For example, because you're waiting for confirmation that the bank processed the transaction. Later, when you create a payment journal line to pay the remaining amount, the **Total Exported Amount** field shows how much of the payment amount was already exported. Also, you can find detailed information about the exported total by choosing the **Credit Transfer Reg. Entries** button to see details about exported payment files.

If you don't want to post payments until the bank confirms they're processed, you can:

* In a payment journal with suggested payment lines, you can sort on either the **Exported to Payment File** column or the **Total Exported Amount** and then delete payment suggestions for open invoices for which payments were already made.
* On the **Suggest Vendor Payments** page, where you specify which payments to insert in the payment journal, you can select the **Skip Exported Payments** checkbox if you don't want to insert journal lines for payments that were already exported.

To see information about exported payments, choose the **Payment Export History** action.

### To re-export payments to a bank file

You can re-export payment files from the **Credit Transfer Registers** page. Before you delete or post payment journal lines, you can also re-export the payment file from the **Payment Journals** page by exporting it again. If you delete or post the payment journal lines after your export, you can re-export the same payment file from the **Credit Transfer Registers** page. Select the line for the batch of credit transfers that you want to re-export, and then use the **Reexport Payments to File** action.

> [!NOTE]  
> Exported EFT files are not shown on the **Credit Transfer Registers** page and cannot be re-exported.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Credit Transfer Registers**, and then choose the related link.
2. Select a payment export that you want to re-export, and then choose the **Reexport Payment to File** action.

## Posting the payments

After your bank processes the electronic payment, post the payments. For more information, see [Making Payments](payables-make-payments.md).

## Related information

[Use the AMC Banking 365 Fundamentals extension](ui-extensions-amc-banking.md)  
[Managing Payables](payables-manage-payables.md)  
[Work with General Journals](ui-work-general-journals.md)  
[Collect Payments with SEPA Direct Debit](finance-collect-payments-with-sepa-direct-debit.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
