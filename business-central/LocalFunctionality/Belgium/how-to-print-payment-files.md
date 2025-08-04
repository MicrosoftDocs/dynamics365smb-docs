---
title: Export Payment Files in the Belgian Version
description: In the Belgian Version of Business Central, you can print the payment journal lines to a payment file after printing a test report and correcting errors.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: payment journal lines, payment file, payment journal, print payment lines, Belgian version
ms.search.form: 2000001
ms.date: 04/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Export payment files in the Belgian version

After printing a test report and correcting errors, you can export the payment journal lines to a payment file.  

A payment file contains either domestic, international, SEPA, or non-Euro SEPA payments. The file can be sent to a bank electronically. You can create only one file for each posting date and each currency code. When you export the payments to a file, an accompanying note is printed, which can also be sent to the bank.  

In the payment journal, the **Status** field on the exported lines is set to **Posted**.  

## Print a payment file  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter *Payment Journal*, and then choose the link to open the **EB Payment Journal** page.  
1. In the **Batch Name** field, select the required journal batch.  
1. In the **Export Protocol** field, select the export protocol.  

   Export protocols control which payment file is generated in the payment journal. You can have a mixture of export formats in a single batch, such as domestic, international, SEPA, or a combination of these. However, when exporting the payment lines to a file, you can use only one export format, or export protocol.  

   > [!NOTE]
   > By defining the export protocol, you also define the type of validation that is performed in the payment journal.
1. Enter the payment journal line information.

    1. Choose the **Suggest Vendor Payments** action.
    1. In the **Suggest Vendor Payments EB** page, set the relevant filters and options.

        This batch job processes open vendor ledger entries and creates a payment suggestion as lines in a payment journal. Open vendor ledger entries result from posting invoices and finance charge memos.

        Only the ledger entries of vendors where the **Suggest Payments** field is selected on their **Vendor** card are included in the batch job. The suggestions are registered in a payment journal. You must specify a last payment date that is used in the batch job.

        In addition, only vendor entries that aren't marked as **On Hold** in the **Vendor Ledger Entries** page are included in the batch job. You can also run the batch job so that it also includes payments for which you can obtain a discount.

        When you enter an available amount, the vendors are ordered by **Priority**.

        You can define what is included in the report by setting filters. To set additional fields on the tab, choose the field. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]
    1. Delete or modify the lines as appropriate.
    1. If no bank account is indicated on the payment journal template, indicate a bank account to pay with on each line.
1. Choose the **Check Payment Lines** action.

    The **Export Check Error Logs** page displays any errors that exist. If there are errors, you must fix them before you can continue.

1. If there are no errors, choose the **Export Payment Lines** action.  

   The report that you specified in the relevant export protocol processes the payment lines and generates the file.  

## Related information

- [Belgian Electronic Banking](belgian-electronic-banking.md)  
- [Belgian Electronic Payments](belgian-electronic-payments.md)  
- [Set Up Vendors for Automatic Payment Suggestions](how-to-set-up-vendors-for-automatic-payment-suggestions.md)  
- [Suggest Vendor Payments](../../payables-how-suggest-vendor-payments.md)  
- [Create Payment Journal Templates and Batches](how-to-create-payment-journal-templates-and-batches.md)  
- [Test Electronic Payments](how-to-test-electronic-payments.md)  
