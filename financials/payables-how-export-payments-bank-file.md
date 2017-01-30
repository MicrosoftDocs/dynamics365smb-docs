---
title: 'How to: Export Payments to a Bank File| Microsoft Docs'
description: 'How to: Export Payments to a Bank File'
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: project-madeira
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/12/2016
ms.author: sgroespe

---
# How to: Export Payments to a Bank File
When you are ready to make payments to your vendors using the **Payment Journal** window, you can export a file with the payment information on the journal lines. You can then upload the file to your electronic bank to process the related money transfers.

In the generic version of Financials, a global provider of services to convert bank data to any file format that your bank requires is set up and connected.

**Note**: Before you can export from a payment journal, you must enable export on the related journal batch. In addition, your bank account and the vendor’s bank account must be set up for electronic payment. For more information, see [How to: Set Up the Bank Data Conversion Service](bank-how-setup-bank-data-conversion-service.md).

You use the **Credit Transfer Registers** window to view the payment files that have been exported from the payment journal. From this window, you can also re-export payment files in case of technical errors or file changes.

## To export payments to a bank file
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Payment Journals**, and then choose the related link.
2. Fill payment journal lines, for example, by using the **Suggest Vendor Payments** function. For more information, see [How to: Suggest Vendor Payments](payables-how-suggest-vendor-payments.md).  
3. When you have completed all payment journal lines, choose **Export Payment to File**.
   
    Any error messages will be shown in the **Payment File Errors** FactBox where you can also choose an error message to see detailed information. You must resolve all errors before the payment file can be exported.
   
    **Tip**: When you use the bank data conversion service, a common error message states that the bank account number does not have the length that your bank requires. To avoid or resolve the error, you must remove the value in the **IBAN** field in the **Bank Account Card** window and then, in the **Bank Account No.** field, enter a bank account number in the format that your bank requires.
4. In the **Save As** window, specify the location that the file is exported to, and then choose **Save**.

The bank payment file is exported to the location that you specify, and you can proceed to upload it to your electronic bank account and make the actual payments.

When you receive confirmation that the payments are successfully processed in the bank, you can post the exported payment journal lines.

## To plan when to post exported payments
If you do not want to post a payment journal line for an exported payment, for example because you are waiting for confirmation that the transaction has been processed by the bank, you can just delete the journal line. When you later create a payment journal line to pay the remaining amount on the invoice, the **Total Exported Amount** field shows how much of the payment amount has already been exported. Also, you can find detailed information about the exported total by choosing the **Credit Transfer Reg. Entries** button to see details about exported payment files.

If you follow a process where you do not post payments until you have confirmation that they have been processed in the bank, you can control this in two ways.

* In a payment journal with suggested payment lines, you can sort on either the **Exported to Payment File** column or the **Total Exported Amount** and then delete payment suggestions for open invoices for which payments have already been made and you do not want to make payments for.
* In the **Suggest Vendor Payments** window, where you specify which payments to insert in the payment journal, you can select the **Skip Exported Payments** check box if you do not want to insert journal lines for payments that have already been exported.

To see information about exported payments, choose the **Payment Export History** action.

## To re-export payments to a bank file
You can re-export payment files from the **Credit Transfer Registers** window. Before you delete or post payment journal lines, you can also re-export the payment file from the **Payment Journal** window by simply exporting it again.

If you have deleted or posted the payment journal lines after exporting them, you can re-export the same payment file from the **Credit Transfer Registers** window. Select the line for the batch of credit transfers that you want to re-export, and then use the **Reexport Payments to File** action.

## See Also
[Payables](payables-manage-payables.md)  
[Purchasing](purchasing-manage-purchasing.md)
[Setting Up Purchasing](purchasing-setup-purchasing.md)  
[Working With Financials](ui-work-product.md)

