---
title: Set Up incoming documents
description: Set up the Incoming Documents feature to create electronic documents, manage OCR tasks, import invoices, and convert image files.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: electronic document, e-invoice, incoming document, OCR, ecommerce, document exchange, import invoice
ms.date: 10/15/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up incoming documents

If you create general journal lines from incoming document records, you must specify on the **Incoming Documents Setup** page which journal template and batch to use.

When the **Incoming Documents** feature is set up, you can use different functions to review expense receipts, manage OCR tasks, and convert incoming document files, manually or automatically, to the relevant documents or journal lines. The external files can be attached at any process stage, including to posted documents and to the resulting vendor, customer, and general ledger entries. Learn more in [Create Incoming Documents Records](across-how-create-income-document-records.md).

## To set up the Incoming Documents feature

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Incoming Document Setup**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

As part of the setup, you must decide if you want to require approval of incoming documents. To require approval, you must [set up approvers and approval workflows](#to-set-up-approvers-of-incoming-document-records). If your organization doesn't intend to require approval, you can skip the next section.

Finally, if you use an OCR service to convert PDF or image files representing incoming documents, [you must it set up](#to-set-up-an-ocr-service). Otherwise, you can also skip that section.

## To set up approvers of incoming document records

If you don't want users to create invoices or general journal lines from incoming document records unless the documents are first approved, set up an approval process for the incoming documents. Approvers of incoming documents must be set up as approval workflow users.

Before you can create workflows that involve approval steps, you must set up the workflow users who are involved in approval processes. On the **Approval User Setup** page, you also set amount limits for specific types of requests and define substitute approvers to whom approval requests are delegated when the original approver is absent. Learn more in [Set Up Approval Users](across-how-to-set-up-approval-users.md).

## To set up an OCR service

To turn PDF and image files into electronic documents that you can convert to invoices, credit memos, or journal lines, set up the OCR feature. Alternatively, you can create entries manually to represent the external documents.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **OCR Service Setup**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]  
> Your login data is automatically encrypted.

Learn more in [Use OCR to Turn PDF and Image Files into Electronic Documents](across-how-use-ocr-pdf-images-files.md).  

## Related information

[Incoming Documents](across-income-documents.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
