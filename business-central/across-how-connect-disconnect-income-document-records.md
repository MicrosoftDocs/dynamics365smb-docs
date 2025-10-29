---
title: Create incoming document records from docs
description: Attach external business documents to related incoming document records for easy storage and management.
author: jswymer
ms.topic: how-to
ms.search.keywords: electronic document, e-invoice, incoming document, OCR, ecommerce, document exchange, import invoice
ms.date: 10/14/2025
ms.author: jswymer
ms.reviewer: v-soumramani
ms-service: dynamics-365-business-central
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Create incoming document records directly from documents and entries

You can store external business documents in [!INCLUDE[prod_short](includes/prod_short.md)] by attaching the document files to the related incoming document records. If the document, such as a purchase invoice, didn't start its existence as an incoming document record, you can still create and connect an incoming document record to it later. You can also attach incoming document files to posted purchase and sales documents and to vendor, customer, and general ledger entries by using the **Incoming Document Files** FactBox in, for example, the **Posted Purchase Invoices** and **Vendor Ledger Entries** pages.

From the **Chart of Accounts** and **General Ledger Entries** pages, you can use a search function to find general ledger entries for posted purchase and sales documents that don't have incoming document records and then centrally link to existing records or create new ones with attached document files. For more information, see [Find Posted Documents without Incoming Document Records](across-how-find-posted-documents-without-income-document-records.md).

The following procedures show how to attach a file to a vendor ledger entry or an existing purchase invoice that wasn't created from an incoming document record. Attaching a file to posted purchase or sales documents works in a similar way.

[!INCLUDE [incoming-doc-archived-doc](includes/incoming-doc-archived-doc.md)]

## Create and connect an incoming document record from a purchase invoice

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Purchase Invoices**, and then choose the related link.
2. Select the line for a purchase invoice that you want to attach a file to, and then choose the **Create Incoming Document from File** action.
3. Alternatively, select the line for a purchase invoice that you want to attach a file to, and then choose the **Attach File** action.
4. On the **Insert File** page, do one of the following steps to attach a file that represents the incoming document in question:

   [!INCLUDE[file-upload](includes/file-upload.md)]

## Create and connect an incoming document record from a vendor ledger entry

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Vendor Ledger Entries**, and then choose the related link.
2. Select a line for a vendor ledger entry that you want to attach a file to, and then choose the **Create Incoming Document from File** action.
3. Alternatively, select a line for a vendor ledger entry that you want to attach a file to, and then choose the **Attach File** action.
4. On the **Insert File** page, do one of the following steps to attach a file that represents the incoming document in question:

   [!INCLUDE[file-upload](includes/file-upload.md)]

## Remove a connection from an incoming document record to a posted document

You can remove file attachments from non-posted documents at any time by deleting the related incoming document record. If the document is posted, then you must first remove the connection from the incoming document record.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Incoming Documents**, and then choose the related link.
2. Select the line for an incoming document record connected to a posted document that you want to remove, and then choose the **Remove Reference to Record** action.

The connection to the posted document is removed. You can now proceed to connect another incoming document record to the posted document as described in this article.

## Related information

[Create Incoming Document Records](across-how-create-income-document-records.md)  
[Use OCR to Turn PDF and Image Files into Electronic Documents](across-how-use-ocr-pdf-images-files.md)  
[Find Posted Documents without Incoming Document Records](across-how-find-posted-documents-without-income-document-records.md)  
[Incoming Documents](across-income-documents.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
