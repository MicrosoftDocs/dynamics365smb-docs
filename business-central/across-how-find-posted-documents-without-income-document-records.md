---
title: Find Posted Documents without Incoming Document Records
description: Search for general ledger entries of posted purchase and sales documents that lack associated incoming electronic documents, such as imported invoices.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: electronic document, e-invoice, incoming document, OCR, ecommerce, document exchange, import invoice
ms.date: 11/10/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Find posted documents without incoming document records

From the **Chart of Accounts** and **General Ledger Entries** pages, you can use a search function to find general ledger entries for posted purchase and sales documents that don't have incoming document records and then centrally link to existing records or create new ones with attached document files.

## Find posted documents without incoming document records

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Chart of Accounts**, and then choose the related link.
1. Select a G/L account whose posted documents you want to check, and then choose **Posted Documents without Incoming Document**.

Alternatively, open **General Ledger Entries** and choose **Posted Documents without Incoming Document**.

The **Posted Documents without Incoming Document** page shows documents represented by general ledger entries on the selected G/L account. By default, the **Date Filter** limits the posting dates from the start of the fiscal year to the work date. Use the date, document number, G/L account, and external document number filters to narrow the results. If a message indicates that the result limit was reached, narrow the filters to find the documents you need.

## Connect found documents to existing incoming document records

Select an incoming document record that has an attachment and isn't already linked to another document or journal line.

1. On the **Posted Documents without Incoming Document** page, select the line for a posted document that you want to connect to an existing incoming document record, and then choose the **Select Incoming Document** action.
1. On the **Incoming Documents** page, select the incoming document record that you want to connect to the posted document, and then choose **OK**.

The selected incoming document record is connected to the posted document. You can view its files in the **Incoming Document Files** FactBox.

If a relevant incoming document record doesn't exist on the **Incoming Documents** page, then you can create it. For more information, see [Create Incoming Document Records](across-how-create-income-document-records.md).

## Related information

[Create Incoming Document Records](across-how-create-income-document-records.md)  
[Use OCR to Turn PDF and Image Files into Electronic Documents](across-how-use-ocr-pdf-images-files.md)  
[Create Incoming Document Records Directly from Documents and Entries](across-how-connect-disconnect-income-document-records.md)  
[Incoming Documents](across-income-documents.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
