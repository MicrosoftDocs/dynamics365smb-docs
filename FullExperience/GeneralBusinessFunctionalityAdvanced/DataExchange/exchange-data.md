---
title: "Exchange Data"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: e23c5010-c609-457a-915a-89bfb3648982
caps.latest.revision: 8
ms.author: "sgroespe"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
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
# Exchange Data
You can exchange data between [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)] and external files or streams in connection with common business tasks, such as sending and receiving electronic documents and importing and exporting bank files. For more information, see [Data Exchange](../../BusinessFunctionality/DataExchange/data-exchange.md).  
  
 Before you can send and receive electronic documents or import and export bank files, you must set up the Data Exchange Framework to process the involved data files or streams. In addition, you must set up related areas. These include master data for customers that you send electronic invoices to and the bank data conversion service in case you distribute bank file conversions to an external service provider. For more information, see [Set Up Data Exchange](../../BusinessFunctionality/DataExchange/set-up-data-exchange.md).  
  
 The following table describes a sequence of tasks, with links to the topics that describe them.  
  
|**To**|**See**|  
|------------|-------------|  
|Convert sales document records in [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)] to a standardized format and send them as electronic documents that your customers can receive into their system.|[How to: Send Electronic Documents](../../BusinessFunctionality/DataExchange/how-to-send-electronic-documents.md)|  
|Send PDF or image files to a provider of OCR services, and receive them back as electronic documents that can be converted to document records in [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)].|[How to: Use OCR to Turn PDF and Image Files into Electronic Documents](../../BusinessFunctionality/DataExchange/how-to-use-ocr-to-turn-pdf-and-image-files-into-electronic-documents.md)|  
|Receive electronic documents, either from the OCR service or the document exchange service, in a standardized format that you convert to the relevant document records in [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)].|[How to: Receive and Convert Electronic Documents](../../BusinessFunctionality/DataExchange/how-to-receive-and-convert-electronic-documents.md)|  
|Import a bank statement file into the **\($ N\_1290 Payment Reconciliation Journal $\)** window as the first step in reconciling payments or into the **\($ N\_379 Bank Acc. Reconciliation $\)** window as the first step in reconciling bank accounts.|[How to: Import Bank Statements](../../BusinessFunctionality/DataExchange/how-to-import-bank-statements.md)|  
|Export payments from the **\($ N\_256 Payment Journal $\)** window to a bank file that you upload to your electronic bank account for processing.|[How to: Export Payments to a Bank File](../../BusinessFunctionality/DataExchange/how-to-export-payments-to-a-bank-file.md)|  
|Instruct your bank to transfer payment amounts from your customers’ bank accounts to your company’s account according to your setup of SEPA direct debit.|[How to: Create SEPA Direct Debit Collection Entries and Export to a Bank File](../../BusinessFunctionality/DataExchange/how-to-create-sepa-direct-debit-collection-entries-and-export-to-a-bank-file.md)|  
|Use a service provider of currency exchange rates to update the **\($ N\_5 Currencies $\)**.|[How to: Update Currency Exchange Rates from a Service](../../BusinessFunctionality/DataExchange/how-to-update-currency-exchange-rates-from-a-service.md)|  
|View which file elements are mapped to fields in Microsoft Dynamics NAV when importing SEPA CAMT statement files.|[Field Mapping When Importing SEPA CAMT Files](../../BusinessFunctionality/DataExchange/field-mapping-when-importing-sepa-camt-files.md)|  
|View which fields in [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)] are mapped to file elements when exporting payment files by using the Bank Date Conversion Service feature.|[Field Mapping When Exporting Payment Files Using Bank Data Conversion Service](../../BusinessFunctionality/DataExchange/field-mapping-when-exporting-payment-files-using-bank-data-conversion-service.md)|  
  
## See Also  
 [Set Up Data Exchange](../../BusinessFunctionality/DataExchange/set-up-data-exchange.md)   
 [Data Exchange](../../BusinessFunctionality/DataExchange/data-exchange.md)   
 [Invoice Sales Activities](../../Finance/invoice-sales-activities.md)   
 [How to: Record Purchases](../../Finance/how-to-record-purchases.md)   
 [Incoming Documents](../../BusinessFunctionality/IncomingDocuments/incoming-documents.md)   
 [Business Functionality](../Topic/Business%20Functionality.md)