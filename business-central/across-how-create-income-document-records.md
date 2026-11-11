---
title: Create Incoming Document Records
description: Use different functions on the Incoming Documents page to review expense receipts, manage OCR tasks, convert incoming document files and attach external files.
author: jswymer
ms.topic: how-to
ms.search.keywords: electronic document, e-invoice, incoming document, OCR, ecommerce, document exchange, import invoice
ms.date: 11/10/2026
ms.author: jswymer
ms.custom: bap-template
ms.reviewer: jswymer
ai-usage: ai-assisted
ms.service: dynamics-365-business-central
---

# Create incoming document records

On the **Incoming Documents** page, you can use different functions to review expense receipts, manage OCR tasks, and convert incoming document files, manually or automatically, to the relevant documents or journal lines. The external files can be attached at any process stage, including to posted documents and to the resulting vendor, customer, and general ledger entries.

To record an external document in [!INCLUDE[prod_short](includes/prod_short.md)], first create or complete an incoming document record. You can do those tasks manually, or you can take a photo of the external document to create the incoming document record with the image file attached.

Before you can use the **Incoming Documents** feature, you must perform the required setup. Learn more in [Set Up Incoming Documents](across-how-setup-income-documents.md).

## Approve or reject an incoming document

If an approval workflow is enabled for incoming documents, send the record for approval with **Send Approval Request**. The assigned approver can then approve or reject it. Learn more in [Set up approvers of incoming document records](across-how-setup-income-documents.md#set-up-approvers-of-incoming-document-records).

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Incoming Documents**, and then choose the related link.
1. Open the incoming document that has an approval request assigned to you.
1. In the **Approval** group, choose **Approve** or **Reject**.

When all required approvals are complete and the workflow releases the incoming document, the **Released** check box is selected. The user in charge of creating, for example, purchase invoices can proceed to process the record.

## Create an incoming document record by taking a photo

> [!NOTE]  
> The following procedure only applies to the [!INCLUDE[prod_short](includes/prod_short.md)] tablet and phone clients.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Incoming Documents**, and then choose the related link.
1. On the **Incoming Documents** page, choose **New** > **Create from Camera**. The camera on the tablet or phone is activated.
1. Take a photo of a document, such as a purchase receipt, that you want to process as an incoming document, and then choose the **Use** button.

   A new incoming document record is created with the image attached.

## Attach an image to an incoming document record by taking a photo

> [!NOTE]  
> The following procedure only applies to the [!INCLUDE[prod_short](includes/prod_short.md)] tablet and phone clients.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Incoming Documents**, and then choose the related link.
1. Open the card for an existing incoming document record.
1. On the document record page, choose **Process** > **Attach Image from Camera**. The camera on the tablet or phone is activated.
1. Take a photo of a document, such as a purchase receipt, that you want to process as an incoming document, and then choose the **Use** button.

    The image is attached to the incoming document record.

## Create an incoming document record manually

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Incoming Documents**, and then choose the related link.
1. Choose **New** > **Create from File**.
1. In the **Insert File** dialog box, attach the file that represents the incoming document:

   [!INCLUDE[file-upload](includes/file-upload.md)]

1. On the **Incoming Document** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

Alternatively, choose **New** to create an incoming document record without a file. Fill in the fields, and then choose **Process** > **Attach File** when you're ready to attach the file.

## Related information

[Use OCR to Turn PDF and Image Files into Electronic Documents](across-how-use-ocr-pdf-images-files.md)  
[Create Incoming Document Records Directly from Documents and Entries](across-how-connect-disconnect-income-document-records.md)  
[Find Posted Documents without Incoming Document Records](across-how-find-posted-documents-without-income-document-records.md)  
[Incoming Documents](across-income-documents.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
