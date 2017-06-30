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
# How to: Print Payment Files
After you have printed a test report and corrected all errors, you can print the payment journal lines to a payment file.  
  
 A payment file contains either domestic, international, SEPA, or non-euro SEPA payments. The file can be sent to a bank either on disk, by modem, or via Interbanks Standards Association Belgium \(Isabel\). You can only create one file for each posting date and each currency code. When you export the payments to a file, an accompanying note is printed, which can also be sent to the bank.  
  
 In the payment journal, the **Status** field on the exported lines will be set to **Posted**.  
  
### To print a payment file  
  
1.  In the **Search** box, enter **Payment Journal**, and then choose the related link.  
  
2.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Batch Name**|Specify the batch name of the payment journal.|  
    |**Bank Account**|Specify the bank account of the payment journal.|  
    |**Export Protocol**|Specify the export protocol code of the payment journal line. Export protocols control which payment file will be generated in the payment journal.<br /><br /> You can have a mixture of export formats in a single batch, such as domestic, international, SEPA, or a combination of these. However, when exporting the payment lines to a file, you can only use one export format, or export protocol. **Note:**  By defining the export protocol, you also define the type of validation that will be performed in the payment journal.|  
  
3.  On the **Home** tab, in the **Process** group, choose **Check Payment Lines**. The **Export Check Error Logs** window will open. This window will display any errors that may exist. If there are errors, you must fix the errors before you can continue. If there are no errors, on the **Home** tab, in the **Process** group, choose **Export Payment Lines**.  
  
     The report that you specified in the **Test Report ID** field in the **EB Payment Journal Templates** will open.  
  
4.  Choose the **Print** button.  
  
## See Also  
 [Belgian Electronic Banking](belgian-electronic-banking.md)   
 [Belgian Electronic Payments](belgian-electronic-payments.md)   
 [How to: Set Up Electronic Banking](how-to-set-up-electronic-banking.md)   
 [How to: Set Up IBLC-BLWI Transaction Codes](how-to-set-up-iblc-blwi-transaction-codes.md)   
 [How to: Set Up Vendors for Automatic Payment Suggestions](how-to-set-up-vendors-for-automatic-payment-suggestions.md)   
 [How to: Generate Payment Suggestions](how-to-generate-payment-suggestions.md)   
 [How to: Create Payment Journal Templates and Batches](how-to-create-payment-journal-templates-and-batches.md)   
 [How to: Test Electronic Payments](how-to-test-electronic-payments.md)   
 [How to: Manage Electronic Payment Lines](how-to-manage-electronic-payment-lines.md)