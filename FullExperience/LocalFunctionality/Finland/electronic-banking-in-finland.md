---
title: "Electronic Banking in Finland"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "electronic banking, in Finland"
ms.assetid: aa34324d-c6e1-4db3-95c2-47bdcbc8001f
caps.latest.revision: 3
ms.author: "edupont"
translation.priority.ht: 
  - "fi-fi"
---
# Electronic Banking in Finland
The [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] electronic banking feature allows you to process electronic customer and vendor payments. This feature supports domestic payments \(LM03\) and foreign payments \(LUM2\) for transferring electronic bank payments. To export or import electronic payments, you must first set up bank reference files to determine how payment files are processed.  
  
## Customer Payments  
 Domestic customer payments can be imported from the bank and linked to the associated accounts receivable entry with a reference number. This type of automation enables incoming payments to be linked directly to open receivables without a delay in manual processing. The following steps explain how to import customer payments into a file from the bank and how to link these payments to invoices through their reference numbers.  
  
-   Create a sales invoice and assign a unique reference number to the invoice. This reference number will be used by the customer when paying the invoice.  
  
-   Import the payment files that contain customer payments into the cash receipt journal. These files contain the reference numbers received from the bank. The payments are linked to the accounts receivable entry through their reference numbers.  
  
-   Post the cash receipt journal and close the open accounts receivable entries with the applied payments from the file.  
  
### Reference Number  
 A reference number is automatically created when an invoice is posted or when an order is posted for invoicing. However, you can enter a reference number manually on a sales journal transaction. This reference number is not based on the reference number options in the **Sales & Receivables Setup** window. If you enter a reference number for the **Sales** journal, only the validity of the reference number is checked.  
  
## Vendor Payments  
 To send electronic bank payments to vendors, you can export domestic or foreign vendor payments into a transfer file that can be sent to the bank. The following steps show how to export vendor payments.  
  
-   Use the **Bank Payments to send** form to select the vendors for which you want to create payment files.  
  
-   Enter payment information for each transaction in the payment journal or use **Suggest Vendor Payments** to create suggested payments.  
  
-   Generate and preview the payment report.  
  
-   Create a transfer file for domestic or foreign vendor payments.  
  
-   Send the payment transfer file to the bank.  
  
## See Also  
 [Finland Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Finland/finland-local-functionality.md)   
 [How to: Set Up Bank Reference Files](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Finland/how-to-set-up-bank-reference-files.md)   
 [How to: Generate Payment Files](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Finland/how-to-generate-payment-files.md)   
 [How to: Disregard Payment Discounts](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Finland/how-to-disregard-payment-discounts.md)   
 [Suggest Bank Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Finland/-$-b_32000003-suggest-bank-payments-$-.md)   
 [Import Ref. Payment](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Finland/-$-b_32000000-import-ref.-payment-$-.md)   
 [Ref. Payment \- Imported](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Finland/-$-t_32000001-ref.-payment-imported-$-.md)   
 [Ref. Payment \- Exported Buffer](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Finland/-$-t_32000004-ref.-payment-exported-buffer-$-.md)   
 [Bank Payments to send](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Finland/-$-n_32000006-bank-payments-to-send-$-.md)