---
    title: Exchange Data | Microsoft Docs
    description: You can exchange data between ADD INCLUDE<!--[!INCLUDE[dyn_nav](includes/data-exchange.md).
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
# Exchange Data
You can exchange data between ADD INCLUDE<!--[!INCLUDE[dyn_nav](includes/data-exchange.md).  
  
 Before you can send and receive electronic documents or import and export bank files, you must set up the Data Exchange Framework to process the involved data files or streams. In addition, you must set up related areas. These include master data for customers that you send electronic invoices to and the bank data conversion service in case you distribute bank file conversions to an external service provider. For more information, see [Set Up Data Exchange](../set-up-data-exchange.md).  
  
 The following table describes a sequence of tasks, with links to the topics that describe them.  
  
|**To**|**See**|  
|------------|-------------|  
|Convert sales document records in ADD INCLUDE<!--[!INCLUDE[dyn_nav](includes/how-to-send-electronic-documents.md)|  
|Send PDF or image files to a provider of OCR services, and receive them back as electronic documents that can be converted to document records in ADD INCLUDE<!--[!INCLUDE[dyn_nav](includes/how-to-use-ocr-to-turn-pdf-and-image-files-into-electronic-documents.md)|  
|Receive electronic documents, either from the OCR service or the document exchange service, in a standardized format that you convert to the relevant document records in ADD INCLUDE<!--[!INCLUDE[dyn_nav](includes/how-to-receive-and-convert-electronic-documents.md)|  
|Import a bank statement file into the **Payment Reconciliation Journal** window as the first step in reconciling payments or into the **Bank Acc. Reconciliation** window as the first step in reconciling bank accounts.|[How to: Import Bank Statements](../how-to-import-bank-statements.md)|  
|Export payments from the **Payment Journal** window to a bank file that you upload to your electronic bank account for processing.|[How to: Export Payments to a Bank File](../how-to-export-payments-to-a-bank-file.md)|  
|Instruct your bank to transfer payment amounts from your customers’ bank accounts to your company’s account according to your setup of SEPA direct debit.|[How to: Create SEPA Direct Debit Collection Entries and Export to a Bank File](../how-to-create-sepa-direct-debit-collection-entries-and-export-to-a-bank-file.md)|  
|Use a service provider of currency exchange rates to update the **Currencies**.|[How to: Update Currency Exchange Rates from a Service](../how-to-update-currency-exchange-rates-from-a-service.md)|  
|View which file elements are mapped to fields in Microsoft Dynamics NAV when importing SEPA CAMT statement files.|[Field Mapping When Importing SEPA CAMT Files](../field-mapping-when-importing-sepa-camt-files.md)|  
|View which fields in ADD INCLUDE<!--[!INCLUDE[dyn_nav](includes/field-mapping-when-exporting-payment-files-using-bank-data-conversion-service.md)|  
  
## See Also  
 [Set Up Data Exchange](../set-up-data-exchange.md)   
 [Data Exchange](../data-exchange.md)   
 [Invoice Sales Activities](../invoice-sales-activities.md)   
 [How to: Record Purchases](../how-to-record-purchases.md)   
 [Incoming Documents](../incoming-documents.md)   
 [Business Functionality](../Business%20Functionality.md)