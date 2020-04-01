---
    title: How to Print Payment Files
    description: After you have printed a test report and corrected all errors, you can print the payment journal lines to a payment file.

    services: project-madeira 
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Print Payment Files
After you have printed a test report and corrected all errors, you can print the payment journal lines to a payment file.  

A payment file contains either domestic, international, SEPA, or non-euro SEPA payments. The file can be sent to a bank either on disk, by modem, or via Interbanks Standards Association Belgium (Isabel). You can create only one file for each posting date and each currency code. When you export the payments to a file, an accompanying note is printed, which can also be sent to the bank.  

In the payment journal, the **Status** field on the exported lines will be set to **Posted**.  

## To print a payment file  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Journal**, and then choose the related link.  
2.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Batch Name**|Specify the batch name of the payment journal.|  
    |**Bank Account**|Specify the bank account of the payment journal.|  
    |**Export Protocol**|Specify the export protocol code of the payment journal line. Export protocols control which payment file will be generated in the payment journal.<br /><br /> You can have a mixture of export formats in a single batch, such as domestic, international, SEPA, or a combination of these. However, when exporting the payment lines to a file, you can use only one export format, or export protocol. **Note:**  By defining the export protocol, you also define the type of validation that will be performed in the payment journal.|  

3.  Choose the **Check Payment Lines** action.

    The **Export Check Error Logs** page displays any errors that exist. If there are errors, you must fix them before you can continue.

4. If there are no errors, choose the **Export Payment Lines** action.  

    The report that you specified in the **Test Report ID** field in the **EB Payment Journal Templates** will open.  

5.  Choose the **Print** button.  

## See Also  
 [Belgian Electronic Banking](belgian-electronic-banking.md)   
 [Belgian Electronic Payments](belgian-electronic-payments.md)   
 [Set Up Electronic Banking](how-to-set-up-electronic-banking.md)   
 [Set Up IBLC-BLWI Transaction Codes](how-to-set-up-iblc-blwi-transaction-codes.md)   
 [Set Up Vendors for Automatic Payment Suggestions](how-to-set-up-vendors-for-automatic-payment-suggestions.md)   
 [Generate Payment Suggestions](how-to-generate-payment-suggestions.md)   
 [Create Payment Journal Templates and Batches](how-to-create-payment-journal-templates-and-batches.md)   
 [Test Electronic Payments](how-to-test-electronic-payments.md)   
 [Manage Electronic Payment Lines](how-to-manage-electronic-payment-lines.md)
