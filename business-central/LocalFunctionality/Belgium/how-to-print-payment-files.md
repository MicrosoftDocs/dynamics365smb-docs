---
    title: Print Payment Files in the Belgian Version
    description: After you have printed a test report and corrected all errors, you can print the payment journal lines to a payment file in the Belgian Version of Business Central.
    author: edupont04

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.search.keywords:
    ms.date: 04/01/2021
    ms.author: edupont

---
# Print Payment Files

After you have printed a test report and corrected all errors, you can print the payment journal lines to a payment file.  

A payment file contains either domestic, international, SEPA, or non-euro SEPA payments. The file can be sent to a bank either on disk, by modem, or via Interbanks Standards Association Belgium (Isabel). You can create only one file for each posting date and each currency code. When you export the payments to a file, an accompanying note is printed, which can also be sent to the bank.  

In the payment journal, the **Status** field on the exported lines will be set to **Posted**.  

## To print a payment file  

1. Choose the ![Lightbulb that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journal**, and then choose the link to open the **EB Payment Journal** page.  
2. In the **Batch Name** field, select the required journal batch.  
3. In the **Export Protocol** field, select the export protocol.  

    Export protocols control which payment file will be generated in the payment journal. You can have a mixture of export formats in a single batch, such as domestic, international, SEPA, or a combination of these. However, when exporting the payment lines to a file, you can use only one export format, or export protocol.  

    > [!NOTE]
    > By defining the export protocol, you also define the type of validation that will be performed in the payment journal.
4. Enter the payment journal line information, and then choose the **Check Payment Lines** action.

    The **Export Check Error Logs** page displays any errors that exist. If there are errors, you must fix them before you can continue.

5. If there are no errors, choose the **Export Payment Lines** action.  

    The report that you specified in the **Test Report ID** field in the **EB Payment Journal Templates** will open.  

6. Choose the **Print** button.  

## See Also

[Belgian Electronic Banking](belgian-electronic-banking.md)  
[Belgian Electronic Payments](belgian-electronic-payments.md)  
[Set Up Vendors for Automatic Payment Suggestions](how-to-set-up-vendors-for-automatic-payment-suggestions.md)  
[Suggest Vendor Payments](../../payables-how-suggest-vendor-payments.md)  
[Create Payment Journal Templates and Batches](how-to-create-payment-journal-templates-and-batches.md)  
[Test Electronic Payments](how-to-test-electronic-payments.md)  
