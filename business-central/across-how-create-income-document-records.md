---
title: Create Incoming Document Records
description: Use different functions on the Incoming Documents page to review expense receipts, manage OCR tasks, convert incoming document files and attach external files.
author: jswymer
ms.topic: how-to
ms-service: dynamics-365-business-central
ms.search.keywords: electronic document, e-invoice, incoming document, OCR, ecommerce, document exchange, import invoice
ms.date: 02/27/2024
ms.author: jswymer
ms.custom: bap-template
ms.reviewer: jswymer
ms.service: dynamics-365-business-central
---
# Create incoming document records

On the **Incoming Documents** page, you can use different functions to review expense receipts, manage OCR tasks, and convert incoming document files, manually or automatically, to the relevant documents or journal lines. The external files can be attached at any process stage, including to posted documents and to the resulting vendor, customer, and general ledger entries.

To record an external document in [!INCLUDE[prod_short](includes/prod_short.md)], first create or complete an incoming document record. You can do those tasks manually, or you can take a photo of the external document to create the incoming document record with the image file attached.

Before you can use the **Incoming Documents** feature, you must perform the required setup. For more information, see [Set Up Incoming Documents](across-how-setup-income-documents.md).

## Approve or reject an incoming document

If you have set up the **Incoming Documents** feature to require approval to create documents, users with the appropriate rights must approve the records before they're processed. For more information, see [Set up approvers of incoming document records](across-how-setup-income-documents.md#to-set-up-approvers-of-incoming-document-records).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Incoming Documents**, and then choose the related link.
2. Select the line with the document that you want to approve or reject, and then choose the **Approve** or **Reject** actions.

If you approve the incoming document record, the **Released** check box on the incoming document line is selected. The user in charge of creating, for example, purchase invoices can proceed to process the record.

## Create an incoming document record by taking a photo

> [!NOTE]  
> The following procedure only applies to the [!INCLUDE[prod_short](includes/prod_short.md)] tablet and phone clients.

1. On the role center, choose the **Create Incoming Document from Camera** tile, and then go to step 4.
2. Alternatively, choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Incoming Documents**, and then choose the related link.
3. On the **Incoming Documents** page, choose **New**, and then choose **Create from Camera**. The camera on the tablet or phone is activated.
4. Take a photo of a document, such as a purchase receipt, that you want to process as an incoming document, and then choose the **Use** button.

    A new incoming document record is created with the image attached.

## Attach an image to an incoming document record by taking a photo

> [!NOTE]  
> The following procedure only applies to the [!INCLUDE[prod_short](includes/prod_short.md)] tablet and phone clients.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Incoming Documents**, and then choose the related link.
2. Open the card for an existing incoming document record.
3. On the document record page, choose **Process**, and then choose **Attach Image from Camera**. The camera on the tablet or phone is activated.
4. Take a photo of a document, such as a purchase receipt, that you want to process as an incoming document, and then choose the **Use** button.

    The image is attached to the incoming document record.

## Create an incoming document record manually

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Incoming Documents**, and then choose the related link.
2. Choose **New**, and then the **Create from File** action.  
3. On the **Insert File** page, do one the following steps attach a file that represents the incoming document:

   [!INCLUDE[file-upload](includes/file-upload.md)]

4. Alternatively, choose the **New** action, then do the following steps:

    1. To attach a file, choose **Process** > **Attach File**.
    2. On the **Insert File** page, drag a selected the file that represents the incoming document in question or select **click here to browse** to find and open the file.
    3. On the **Incoming Document** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## Related information

[Use OCR to Turn PDF and Image Files into Electronic Documents](across-how-use-ocr-pdf-images-files.md)
[Create Incoming Document Records Directly from Documents and Entries](across-how-connect-disconnect-income-document-records.md)
[Find Posted Documents without Incoming Document Records](across-how-find-posted-documents-without-income-document-records.md)
[Incoming Documents](across-income-documents.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
