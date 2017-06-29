---
title: "Set Up Data Exchange"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 4c8d82d8-6124-4b0d-abee-a4597f735f1d
caps.latest.revision: 9
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
# Set Up Data Exchange
Before you can send and receive electronic documents or import and export bank files, you must set up the Data Exchange Framework to process the involved files. In addition, you must set up related areas, such as master data for customers that you send electronic invoices to or the bank data conversion service in case you use the external service provider to convert your bank files. For more information, see [Data Exchange](../../BusinessFunctionality/DataExchange/data-exchange.md).  
  
 When FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)] --> --> --> --> --> is set up to exchange data with external files, users can use the setup in common business tasks, such as sending and receiving electronic documents and importing and exporting bank files. For more information, see [Exchange Data](../../BusinessFunctionality/DataExchange/exchange-data.md).  
  
 The following table describes a sequence of tasks, with links to the topics that describe them.  
  
|**To**|**See**|  
|------------|-------------|  
|Set up the preconfigured document exchange service to enable sending and receiving electronic documents from and to [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)].|[How to: Set Up a Document Exchange Service](../../BusinessFunctionality/DataExchange/how-to-set-up-a-document-exchange-service.md)|  
|Set up the preconfigured OCR service to turn PDF or image files into electronic documents that can be converted to document records in [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)].|[How to: Set Up an OCR Service](../../BusinessFunctionality/DataExchange/how-to-set-up-an-ocr-service.md)|  
|Set up one of two preconfigured services for updated exchange rates to get the latest currency exchange rates into the **Currencies** window.|[How to: Set Up a Currency Exchange Rate Service](../../BusinessFunctionality/DataExchange/how-to-set-up-a-currency-exchange-rate-service.md)|  
|Set up various master data, such as company information, customers, vendors, items, and units of measure, related to mapping data in [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)] to and from elements in a standardized electronic document file.|[How to: Set Up Electronic Document Sending and Receiving](../../BusinessFunctionality/DataExchange/how-to-set-up-electronic-document-sending-and-receiving.md)|  
|Set up a bank account, a vendor, and a payment journal for SEPA credit transfer.|[How to: Set Up SEPA Credit Transfer](../../BusinessFunctionality/DataExchange/how-to-set-up-sepa-credit-transfer.md)|  
|Prepare bank account formats, payment methods, and customer agreements for SEPA direct debit.|[How to: Set Up SEPA Direct Debit](../../BusinessFunctionality/DataExchange/how-to-set-up-sepa-direct-debit.md)|  
|Set up user authentication and the URL of the bank data conversion service provider that is required to have bank files converted to your bank’s format.|[How to: Set Up the Bank Data Conversion Service](../../BusinessFunctionality/DataExchange/how-to-set-up-the-bank-data-conversion-service.md)|  
|Set up and enable an external service that enables you to import bank statements directly as bank feeds.|[How to: Set Up the Bank Statement Service](../../Finance/how-to-set-up-the-bank-statement-service.md)|  
|After the Bank Statement service is enabled, link bank accounts in [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)] to one or more online bank accounts by accessing the service provider’s **Account Linking** page.|[How to: Link Bank Accounts to Online Bank Accounts](../../Finance/how-to-link-bank-accounts-to-online-bank-accounts.md)|  
|Prepare to set up a new data exchange definition for a data file or stream by using the file’s XML schema to prefill the **Column Definitions** FastTab in the **Posting Exchange Definition** window.|[How to: Use XML Schemas to Prepare Data Exchange Definitions](../../BusinessFunctionality/DataExchange/how-to-use-xml-schemas-to-prepare-data-exchange-definitions.md)|  
|Set up the Data Exchange Framework to enable users to receive a new purchase document format, send a new sales document format, import a new bank file, or other data exchange.|[How to: Set Up Data Exchange Definitions](../../BusinessFunctionality/DataExchange/how-to-set-up-data-exchange-definitions.md)|  
  
## See Also  
 [Exchange Data](../../BusinessFunctionality/DataExchange/exchange-data.md)   
 [Data Exchange](../../BusinessFunctionality/DataExchange/data-exchange.md)   
 [Incoming Documents](../../BusinessFunctionality/IncomingDocuments/incoming-documents.md)   
 [Business Functionality](../Topic/Business%20Functionality.md)