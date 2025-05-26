---
title: Find Posted Documents without Incoming Documents
description: You can search for general ledger entries for posted purchase and sales documents that don't have incoming electronic documents, such as imported invoices.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: electronic document, e-invoice, incoming document, OCR, ecommerce, document exchange, import invoice
ms.date: 06/14/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Find Posted Documents without Incoming Document Records

From the **Chart of Accounts** and **General Ledger Entries** pages, you can use a search function to find general ledger entries for posted purchase and sales documents that don't have incoming document records and then centrally link to existing records or create new ones with attached document files.

## To find posted documents without incoming document records

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.
2. Select a line for a G/L account for whose general ledger entries you want to see posted purchase and sales documents without incoming document records, and then choose the **Posted Documents without Incoming Document** action.
3. Alternatively, choose the **Ledger Entries** action.
4. On the **General Ledger Entries** page, choose the **Posted Documents without Incoming Documents** action.

The **Posted Documents without Incoming Document** page opens showing posted purchase and sales documents without incoming document records represented by general ledger entries on the G/L account that you opened the page for. The page can show a maximum of 1000 lines. By default, the **Date Filter** field therefore contains a filter that limits the lines to entries with posting dates from the beginning of the accounting period to the work date.

## To connect found documents to existing incoming document records

1. On the **Posted Documents without Incoming Document** page, select the line for a posted document that you want to connect to an existing incoming document record, and then choose the **Select Incoming Document** action.
2. On the **Incoming Documents** page, select the incoming document record that you want to connect to posted document found, and then choose the **OK** button.
3. On the **Posted Documents without Incoming Document** page, the selected incoming document record is now connected to the posted document, as you can see in the **Incoming Document Files** FactBox.

If a relevant incoming document record doesn't exist on the **Incoming Documents** page, then you can create it. For more information, see [Create Incoming Document Records](across-how-create-income-document-records.md).

## Related information

[Create Incoming Document Records](across-how-create-income-document-records.md)
[Use OCR to Turn PDF and Image Files into Electronic Documents](across-how-use-ocr-pdf-images-files.md)
[Create Incoming Document Records Directly from Documents and Entries](across-how-connect-disconnect-income-document-records.md)
[Incoming Documents](across-income-documents.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
