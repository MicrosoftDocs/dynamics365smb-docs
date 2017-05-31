---
title: "How to: Print Payment Files"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "payment journals, printing payment files"
  - "payment files, printing"
ms.assetid: d390b5ea-f939-4bd7-a74a-957590b17de3
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "fr-be"
  - "nl-be"
---
# How to: Print Payment Files
After you have printed a test report and corrected all errors, you can print the payment journal lines to a payment file.  
  
 A payment file contains either domestic, international, SEPA, or non\-euro SEPA payments. The file can be sent to a bank either on disk, by modem, or via Interbanks Standards Association Belgium \(Isabel\). You can only create one file for each posting date and each currency code. When you export the payments to a file, an accompanying note is printed, which can also be sent to the bank.  
  
 In the payment journal, the **\($ T\_2000001\_53 Status $\)** field on the exported lines will be set to **Posted**.  
  
### To print a payment file  
  
1.  In the **Search** box, enter **Payment Journal**, and then choose the related link.  
  
2.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Batch Name**|Specify the batch name of the payment journal.|  
    |**\($ N\_2000001\_1010024 Bank Account $\)**|Specify the bank account of the payment journal.|  
    |**\($ N\_2000001\_1010028 Export Protocol $\)**|Specify the export protocol code of the payment journal line. Export protocols control which payment file will be generated in the payment journal.<br /><br /> You can have a mixture of export formats in a single batch, such as domestic, international, SEPA, or a combination of these. However, when exporting the payment lines to a file, you can only use one export format, or export protocol. **Note:**  By defining the export protocol, you also define the type of validation that will be performed in the payment journal.|  
  
3.  On the **Home** tab, in the **Process** group, choose **Check Payment Lines**. The **\($ N\_2000006 Export Check Error Logs $\)** window will open. This window will display any errors that may exist. If there are errors, you must fix the errors before you can continue. If there are no errors, on the **Home** tab, in the **Process** group, choose **Export Payment Lines**.  
  
     The report that you specified in the **\($ T\_2000000\_5 Test Report ID $\)** field in the **\($ N\_2000000 EB Payment Journal Templates $\)** will open.  
  
4.  Choose the **Print** button.  
  
## See Also  
 [Belgian Electronic Banking](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/belgian-electronic-banking.md)   
 [Belgian Electronic Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/belgian-electronic-payments.md)   
 [How to: Set Up Electronic Banking](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-electronic-banking.md)   
 [How to: Set Up IBLC\-BLWI Transaction Codes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-iblc-blwi-transaction-codes.md)   
 [How to: Set Up Vendors for Automatic Payment Suggestions](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-vendors-for-automatic-payment-suggestions.md)   
 [How to: Generate Payment Suggestions](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-generate-payment-suggestions.md)   
 [How to: Create Payment Journal Templates and Batches](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-create-payment-journal-templates-and-batches.md)   
 [How to: Test Electronic Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-test-electronic-payments.md)   
 [How to: Manage Electronic Payment Lines](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-manage-electronic-payment-lines.md)