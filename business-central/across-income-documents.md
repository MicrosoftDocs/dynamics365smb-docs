---
title: Work with Incoming Documents| Microsoft Docs
description: You can manage incoming external business documents, such as payment receipts or PDFs, manage OCR tasks, and convert files to electronic documents and records.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: electronic document, e-invoice, incoming document, OCR, ecommerce, document exchange, import invoice
ms.date: 04/01/2020
ms.author: sgroespe

---
# Incoming Documents
Some business transactions are not recorded in [!INCLUDE[d365fin](includes/d365fin_md.md)] from the outset. Instead, an external business document comes into your company as an email attachment or a paper copy that you scan to file. This is typical of purchases, where such incoming document files represent payment receipts for expenses or small purchases.

From PDF or image files representing incoming documents, you can have an external OCR service (Optical Character Recognition) generate electronic documents that can then be converted to document records inside [!INCLUDE[d365fin](includes/d365fin_md.md)].

On the **Incoming Documents** page, you can use different functions to review expense receipts, manage OCR tasks, and convert incoming document files, manually or automatically, to the relevant documents or journal lines. The external files can be attached at any process stage, including to posted documents and to the resulting vendor, customer, and general ledger entries.

The incoming document process can consist of the following main activities:

* Record the external documents inside [!INCLUDE[d365fin](includes/d365fin_md.md)] by creating lines on the **Incoming Documents** page in either of the following ways:
  * Manually, by using simple functions, either from a PC or from a mobile device, in one of the following ways:
    * Use the **Create from File** button, and then fill relevant fields on the **Incoming Document** page. The file is automatically attached.  
    * Use the **New** button, and then fill relevant fields on the **Incoming Document** page and manually attach the related file.
    * From a tablet or phone, use the **Create from Camera** button to create a new incoming document record, and then send the image to the OCR service, for example.
  * Automatically, by receiving the document from the OCR service as an electronic document after you have emailed the related PDF or image file to the OCR service. The **Financial Information** FastTab is automatically filled on the **Incoming Document** page.
* Use the OCR service to have PDF or image files turned into electronic documents that can be converted to document records in [!INCLUDE[d365fin](includes/d365fin_md.md)].
* Create new documents or general journal lines for incoming document records by entering the information as you read it from incoming document files.
* Attach incoming document files to purchase and sales documents of any status, including to the vendor, customer, and general ledger entries that result from posting.
* View incoming document records and their attachments from any purchase and sales document or entry, or find all general ledger entries without incoming document records from the **Chart of Accounts** page.

| To | See |
| --- | --- |
| Set up the Incoming Documents feature and set up the OCR service. |[Set Up Incoming Documents](across-how-setup-income-documents.md) |
| Create incoming document records, attach files, use OCR to turn PDF files into electronic documents, convert electronic documents to document records, audit incoming document records from posted sales and purchase documents. |[Processing Incoming Documents](across-process-income-documents.md) |

## See Related Training at [Microsoft Learn](/learn/modules/incoming-documents-dynamics-365-business-central/index)

## See Also
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
