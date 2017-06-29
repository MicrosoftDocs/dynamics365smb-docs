---
title: "How to: Use OCR to Turn PDF and Image Files into Electronic Documents"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: a1b8ed5b-7be1-4193-91af-31d63f14bf98
caps.latest.revision: 15
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
# How to: Use OCR to Turn PDF and Image Files into Electronic Documents
From PDF or image files that you receive from your trading partners, you can have an external OCR service \(Optical Character Recognition\) generate electronic documents that can be converted to document records in [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)]. For example, when you receive an invoice in PDF format from your vendor, you can send it to the OCR service from the **Incoming Documents** window. This is described in the first procedure.  
  
 As an alternative to sending the file from the **Incoming Documents** window, you can send the file to the OCR service by email. Then, when you receive the electronic document back, a related incoming document record is created automatically. This is described in the second procedure.  
  
 After some seconds, you receive the file back from the OCR service as an electronic invoice that can be converted to a purchase invoice for the vendor. This is described in the third procedure.  
  
 You can either send incoming document files to the OCR service manually, as described in this procedure, or you can enable a workflow to send them automatically when an incoming document with a PDF or image attachment is created. The generic version of [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)] includes a workflow template, **Incoming Document OCR Workflow**, which is ready to create a workflow from. For more information, see [Workflow](../../BusinessFunctionality/Workflow/workflow.md).  
  
 Because OCR is based on optical recognition, it is likely that the OCR service will interpret characters in your PDF or image files wrongly when it first processes a certain vendor’s documents, for example. It may not interpret the company logo as the vendor’s name or it may misinterpret the total amount on a receipt because of its layout. To avoid these errors going forward, you can correct the errors in a separate version of the **Incoming Document Card** window. Then you send the corrections back to the OCR service to train it to interpret the specific characters correctly next time it processes a PDF or image document for the same vendor. For more information, see [How to: Train the OCR Service to Avoid Errors](../../BusinessFunctionality/IncomingDocuments/how-to-train-the-ocr-service-to-avoid-errors.md).  
  
 The electronic document generated from OCR is processed by the Data Exchange Framework like for electronic PEPPOL documents. For more information, [How to: Receive and Convert Electronic Documents](../../BusinessFunctionality/DataExchange/how-to-receive-and-convert-electronic-documents.md).  
  
> [!NOTE]  
>  The traffic of files to and from the OCR service is processed by a dedicated job queue entry, which are created automatically when you enable the related service connection. For more information, see [How to: Set Up an OCR Service](../../BusinessFunctionality/DataExchange/how-to-set-up-an-ocr-service.md).  
  
### To send a PDF or image file to the OCR service from the Incoming Documents window  
  
1.  In the **Search** box, enter **Incoming Documents**, and then choose the related link.  
  
2.  Create a new incoming document record and attach the file. For more information, see [How to: Create Incoming Document Records](../../BusinessFunctionality/IncomingDocuments/how-to-create-incoming-document-records.md).  
  
3.  In the **Incoming Documents** window, select one or more lines, and then, on the **Actions** tab, in the **OCR** group, choose **Send to Job Queue**.  
  
     The value in the **OCR Status** field changes to **Ready**. The attached PDF or image file is sent to the OCR service by the job queue according to the schedule, provided that no errors exist. For more information, see [Use Job Queues to Schedule Tasks](../../SetupAndAdministration/use-job-queues-to-schedule-tasks.md).  
  
4.  Alternatively, in the **Incoming Documents** window, select one or more lines, and then, on the **Actions** tab, in the **OCR** group, choose **Send to OCR Service**.  
  
     The value in the **OCR Status** field changes to **Sent**, provided that no errors exist.  
  
### To send a PDF or image file to the OCR service by email  
  
-   From your email application, send an email to the OCR service provider with the PDF or image file attached. For information about the email address to send to, see the service provider’s web site.  
  
     Because no incoming document record exists for the file, a new record will be created automatically in the **Incoming Documents** window when you receive the resulting electronic document from the OCR service. For more information, see [How to: Create Incoming Document Records](../../BusinessFunctionality/IncomingDocuments/how-to-create-incoming-document-records.md).  
  
    > [!NOTE]  
    >  If you work on a tablet or phone, you can send the file to the OCR service as soon as you have taken a photo of the document, or you can create an incoming document directly. For more information, see [How to: Create Incoming Document Records by Taking a Photo](../../BusinessFunctionality/IncomingDocuments/how-to-create-incoming-document-records-by-taking-a-photo.md).  
  
### To receive an electronic document from the OCR service  
  
1.  In the **Search** box, enter **Incoming Documents**, and then choose the related link.  
  
2.  To actively pull electronic document from the OCR service, on the **Actions** tab, in the **OCR** group, choose **Receive from OCR Service**.  
  
3.  Alternatively, wait until a new electronic document is coming in from the OCR service through the job queue.  
  
     When the electronic document arrives, various fields in the **Incoming Document Card** window will be filled with information from the source document file. For more information, see [How to: Receive and Convert Electronic Documents](../../BusinessFunctionality/DataExchange/how-to-receive-and-convert-electronic-documents.md).  
  
 Now you can proceed to create document records in [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)], manually or automatically. You can also connect the new incoming document record to existing posted or non\-posted document so that the source file is easy to access from [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)]. For more information, see [Use Incoming Documents](../../BusinessFunctionality/IncomingDocuments/use-incoming-documents.md).  
  
> [!NOTE]  
>  When you create, for example, a purchase invoice from an electronic document that was created with OCR, the invoice will contain one line of type G\/L Account with an empty **Description** field, and the value in the **Amount** field will equal the total amount excluding VAT. To make sure that the **Description** field is filled, you can open the **Text\-to\-Account Mapping** window from the **Incoming Documents** window to define that a certain invoice text is always mapped to a certain debit account. Going forward, the **Description** field on document lines created from an electronic document for that vendor will then be filled with the text in question, so that the invoice is ready to post. For more information, see [How to: Receive and Convert Electronic Documents](../../BusinessFunctionality/DataExchange/how-to-receive-and-convert-electronic-documents.md).  
  
## See Also  
 Incoming Document   
 OCR Status   
 Status   
 [How to: Train the OCR Service to Avoid Errors](../../BusinessFunctionality/IncomingDocuments/how-to-train-the-ocr-service-to-avoid-errors.md)   
 [How to: Set Up the Incoming Documents Feature](../../BusinessFunctionality/IncomingDocuments/how-to-set-up-the-incoming-documents-feature.md)   
 [How to: Receive and Convert Electronic Documents](../../BusinessFunctionality/DataExchange/how-to-receive-and-convert-electronic-documents.md)   
 [How to: Create Incoming Document Records](../../BusinessFunctionality/IncomingDocuments/how-to-create-incoming-document-records.md)   
 [How to: View Incoming Document Records from Documents and Entries](../../BusinessFunctionality/IncomingDocuments/how-to-view-incoming-document-records-from-documents-and-entries.md)   
 [Incoming Documents](../../BusinessFunctionality/IncomingDocuments/incoming-documents.md)   
 [Data Exchange](../../BusinessFunctionality/DataExchange/data-exchange.md)   
 [Data Exchange](../../BusinessFunctionality/DataExchange/data-exchange.md)   
 [Workflow](../../BusinessFunctionality/Workflow/workflow.md)