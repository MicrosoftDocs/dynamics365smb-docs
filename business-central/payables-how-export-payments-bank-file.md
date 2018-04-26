---
title: Export Payments to an Electronic Payment File| Microsoft Docs
description: To make vendor payments, you enable a bank data conversion service, export a bank file, and upload the file to your electronic bank to transfer the funds.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: bank file export, re-export, bank transfer, AMC, bank data conversion service, funds transfer
ms.date: 04/26/2018
ms.author: sgroespe

---
# Export Payments to a Bank File
When you are ready to make payments to your vendors, or reimbursements to your employees, you can export a file with the payment information on the lines in the **Payment Journal** window. You can then upload the file to your bank to process the related money transfers.

In the generic version of [!INCLUDE[d365fin](includes/d365fin_md.md)], a global provider of services to convert bank data to any file format that your bank requires is set up and connected. In North American versions, the same service can be used to send payment files as electronic funds transfer (EFT), however with a slightly different process. See step 6 in the "To export payments to a bank file" section.    

> [!NOTE]  
>   Before you can export payment files from the payment journal, you must specify the electronic format for the involved bank account, and you must enable the bank data conversion service. For more information, see [Set Up Bank Accounts](bank-how-setup-bank-accounts.md) and [Set Up the Bank Data Conversion Service](bank-how-setup-bank-data-conversion-service.md). In addition, you must select the **Allow Payment Export** check box in the **General Journal Batches** window. For more information, see [Working with General Journals](ui-work-general-journals.md).  

You use the **Credit Transfer Registers** window to view the payment files that have been exported from the payment journal. From this window, you can also re-export payment files in case of technical errors or file changes. Note, however, that exported EFT files are not shown in this window and cannot be re-exported.  

## To export payments to a bank file
The following describes how to pay a vendor by check. The steps are similar to refund a customer by check.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Journals**, and then choose the related link.
2. Fill in the payment journal lines. For more information, see [Record Payments and Refunds](payables-how-post-payments-refunds.md).

> [!NOTE]  
>   If you are using EFT, you must select either **Electronic Payment** or **Electronic Payment–IAT** in the **Bank Payment Type** field. Different file export services and their formats require different setup values in the **Bank Account Card** and **Vendor Bank Account Card** windows. You will be informed about wrong or missing setup values as you try to export the file.

3. When you have completed all payment journal lines, choose the **Export** action.
4. In the **Export Electronic Payments** window, fill in the fields as necessary.

    Any error messages will be shown in the **Payment File Errors** FactBox where you can also choose an error message to see detailed information. You must resolve all errors before the payment file can be exported.

    > [!TIP]  
    >   When you use the bank data conversion service, a common error message states that the bank account number does not have the length that your bank requires. To avoid or resolve the error, you must remove the value in the **IBAN** field in the **Bank Account Card** window and then, in the **Bank Account No.** field, enter a bank account number in the format that your bank requires.

5. In the **Save As** window, specify the location that the file is exported to, and then choose **Save**.

    > [!NOTE]  
    >   If you are using EFT, save the resulting vendor remittance form as a Word document or select to have it emailed directly to the vendor. The payments are now added to the **Generate EFT File** window from where you can generate multiple payment orders together to save transmission cost. For more information, see the following steps.
6. In the **Payment Journal** window, choose the **Generate EFT File** action.

    In the **Generate EFT File** window, all payments set up for EFT that you have exported from the payment journal for a specified bank account but not yet generated are listed on the **Lines** FastTab.
7. Choose the **Generate EFT File** action to export one file for all the EFT payments.
8. In the **Save As** window, specify the location that the file is exported to, and then choose **Save**.

The bank payment file is exported to the location that you specify, and you can proceed to upload it to your electronic bank account and make the actual payments. Then you can post the exported payment journal lines.

## To plan when to post exported payments
If you do not want to post a payment journal line for an exported payment, for example because you are waiting for confirmation that the transaction has been processed by the bank, you can just delete the journal line. When you later create a payment journal line to pay the remaining amount on the invoice, the **Total Exported Amount** field shows how much of the payment amount has already been exported. Also, you can find detailed information about the exported total by choosing the **Credit Transfer Reg. Entries** button to see details about exported payment files.

If you follow a process where you do not post payments until you have confirmation that they have been processed in the bank, you can control this in two ways.

* In a payment journal with suggested payment lines, you can sort on either the **Exported to Payment File** column or the **Total Exported Amount** and then delete payment suggestions for open invoices for which payments have already been made and you do not want to make payments for.
* In the **Suggest Vendor Payments** window, where you specify which payments to insert in the payment journal, you can select the **Skip Exported Payments** check box if you do not want to insert journal lines for payments that have already been exported.

To see information about exported payments, choose the **Payment Export History** action.

## To re-export payments to a bank file
You can re-export payment files from the **Credit Transfer Registers** window. Before you delete or post payment journal lines, you can also re-export the payment file from the **Payment Journal** window by simply exporting it again. If you have deleted or posted the payment journal lines after exporting them, you can re-export the same payment file from the **Credit Transfer Registers** window. Select the line for the batch of credit transfers that you want to re-export, and then use the **Reexport Payments to File** action.

> [!NOTE]  
>   Exported EFT files are not shown in the **Credit Transfer Registers** window and cannot be re-exported.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Credit Transfer Registers**, and then choose the related link.
2. Select a payment export that you want to re-export, and then choose the **Reexport Payment to File** action.

## See Also
[Making Payments](payables-make-payments.md)  
[Payables](payables-manage-payables.md)  
[Setting Up Purchasing](purchasing-setup-purchasing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
