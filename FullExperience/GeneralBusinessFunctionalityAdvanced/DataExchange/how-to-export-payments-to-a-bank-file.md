---
title: "How to: Export Payments to a Bank File"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "exporting, to a bank file"
  - "payments, exporting to a bank file"
  - "exporting, payments"
ms.assetid: 8948133e-52e9-4a72-9e2b-ba461359a4e5
caps.latest.revision: 22
ms.author: "sgroespe"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Export Payments to a Bank File
When you are ready to make payments to your vendors using the **\($ N\_256 Payment Journal $\)** window, you can export a file with the payment information on the journal lines. You can then upload the file to your electronic bank to process the related money transfers.  
  
 In the generic version of [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)], a global provider of services to convert bank data to any file format that your bank requires is set up and connected.  
  
> [!NOTE]  
>  The bank data conversion service may impose a limit on the number of lines that can be exported in one file. You will receive an error message if the limit is exceeded.  
  
 In addition, the generic version of [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)] supports the SEPA Credit Transfer format. In your country\/region, other formats for electronic payments may be available. For more information, see [Make Payments with Bank Data Conversion Service or SEPA Credit Transfer](../../Finance/make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md).  
  
 To enable export of a bank file formats that are not supported by the generic or local versions of [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)], you can use the Date Exchange Framework. For more information, see [How to: Set Up Data Exchange Definitions](../../BusinessFunctionality/DataExchange/how-to-set-up-data-exchange-definitions.md).  
  
 Before you can export from a payment journal, you must enable export on the related journal batch. In addition, you bank account and the vendor’s bank account must be set up for electronic payment. For more information, see [How to: Set Up SEPA Credit Transfer](../../BusinessFunctionality/DataExchange/how-to-set-up-sepa-credit-transfer.md) or [How to: Set Up the Bank Data Conversion Service](../../BusinessFunctionality/DataExchange/how-to-set-up-the-bank-data-conversion-service.md).  
  
### To export payments to a bank file  
  
1.  In the **Search** box, enter **Payment Journals**, and then choose the related link.  
  
2.  Fill payment journal lines, for example, by using the **\($ B\_393 Suggest Vendor Payments $\)** function. For more information, see [How to: Suggest Vendor Payments](../../Finance/how-to-suggest-vendor-payments.md).  
  
    > [!NOTE]  
    >  You can select how posting dates are inserted on the journal lines. For more information, see [How to: Insert Due Date as Posting Date on Payment Journal Lines](../../Finance/how-to-insert-due-date-as-posting-date-on-payment-journal-lines.md).  
  
3.  When you have completed all payment journal lines, on the **Home** tab, in the **Bank** group, choose **Export Payments to File**.  
  
     Any error messages will be shown in the **Payment File Errors** FactBox where you can also choose an error message to see detailed information. You must resolve all errors before the payment file can be exported.  
  
    > [!TIP]  
    >  When you use the Bank Data Conversion Service feature, a common error message states that the bank account number does not have the length that your bank requires.  
    >   
    >  To avoid or resolve the error, you must remove the value in the **\($ T\_270\_110 IBAN $\)** field in the **\($ N\_370 Bank Account Card $\)** window and then, in the **\($ T\_270\_13 Bank Account No. $\)** field, enter a bank account number in the format that your bank requires.  
  
4.  In the **Save As** window, specify the location that the file is exported to, and then choose **Save**.  
  
     The bank payment file is exported to the location that you specify, and you can proceed to upload it to your electronic bank account and make the actual payments.  
  
 When you receive confirmation that the payments are successfully processed in the bank, you can post the exported payment journal lines.  
  
> [!TIP]  
>  If you do not want to post a payment journal line for an exported payment, for example because you are waiting for confirmation that the transaction has been processed by the bank, you can just delete the journal line. When you later create a payment journal line to pay the remaining amount on the invoice, the **\($ N\_256\_28 Total Exported Amount $\)** field shows how much of the payment amount has already been exported. Also, you can find detailed information about the exported total choosing the **Credit Transfer Reg. Entries** button to see details about exported payment files.  
>   
>  If you follow a process where you do not post payments until you have confirmation that they have been processed in the bank, you may want to control the risk of not accidently exporting payments again for open documents for which payment exports already have been made and are in process at the bank. You can control this in two ways.  
>   
>  1.  In a payment journal with suggested payment lines, you can sort on either the **\($ T\_81\_290 Exported to Payment File $\)** column or the **\($ N\_256\_28 Total Exported Amount $\)** and then delete payment suggestions for open invoices for which payments have already been made and you do not want to make payments for.  
> 2.  Alternatively, on the **Suggest Vendor Payments** batch job, where you specify which payments to insert in the payment journal, you can select the **Skip Exported Payments** check box if you do not want to insert journal lines for payments that have already been exported.  
>   
>  To see information about exported payments, on the **Home** tab, in the **Bank** group, choose **Payment Export History**. For more information, see [How to: Re\-export Payments to a Bank File](../../Finance/how-to-re-export-payments-to-a-bank-file.md).  
  
## See Also  
 [\($ T\_270\_1210 Payment Export Format $\)](assetId:///0bd91b95-8ee0-4c8f-90b6-c78248849896)   
 [\($ T\_81\_290 Exported to Payment File $\)](assetId:///2066fa1e-7ead-4c75-a3d1-aafc8bc49bfb)   
 [\($ T\_23\_288 Preferred Bank Account $\)](../Topic/\($%20T_23_288%20Preferred%20Bank%20Account%20$\).md)   
 [\($ N\_256\_28 Total Exported Amount $\)](assetId:///a00ace00-a103-477b-8600-db2860af5ff0)   
 [\($ T\_81\_288 Recipient Bank Account $\)](assetId:///1902718c-e916-4992-8ffc-a4bfb748bae2)   
 [\($ T\_232\_11 Allow Payment Export $\)](assetId:///194b6110-910b-4cf9-9023-10f2ecdb2c41)   
 [\($ B\_393 Suggest Vendor Payments $\)](../Topic/\($%20B_393%20Suggest%20Vendor%20Payments%20$\).md)   
 [Field Mapping When Exporting Payment Files Using Bank Data Conversion Service](../../BusinessFunctionality/DataExchange/field-mapping-when-exporting-payment-files-using-bank-data-conversion-service.md)   
 [Field Mapping When Importing SEPA CAMT Files](../../BusinessFunctionality/DataExchange/field-mapping-when-importing-sepa-camt-files.md)   
 [How to: Import Bank Statements](../../BusinessFunctionality/DataExchange/how-to-import-bank-statements.md)   
 [\($ T\_312\_8 Ext. Doc. No. Mandatory $\)](../Topic/\($%20T_312_8%20Ext.%20Doc.%20No.%20Mandatory%20$\).md)   
 [How to: Set Up Data Exchange Definitions](../../BusinessFunctionality/DataExchange/how-to-set-up-data-exchange-definitions.md)   
 [How to: Set Up SEPA Credit Transfer](../../BusinessFunctionality/DataExchange/how-to-set-up-sepa-credit-transfer.md)   
 [How to: Suggest Vendor Payments](../../Finance/how-to-suggest-vendor-payments.md)   
 [How to: Insert Due Date as Posting Date on Payment Journal Lines](../../Finance/how-to-insert-due-date-as-posting-date-on-payment-journal-lines.md)