---
title: Manage Many Incoming Document Records
description: Adjust the default view of incoming documents, such as e-invoices, to improve your overview of processed and unprocessed records.
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

# Manage many incoming document records

As you create or process incoming document records, the number of lines on the **Incoming Documents** page may grow to an extent where you lose overview. Therefore, you can set incoming document records to *Processed* to remove them from the default view. When you choose the **Show All** action, you can view both processed and unprocessed records.

> [!NOTE]  
> The **Incoming Document** page is read-only when the record is set to **Processed**. To edit its fields, first choose **Set To Unprocessed**.

The **Processed** check box is automatically selected when you post the related document or journal line, or when you link the incoming document to a posted document. Attaching a file or creating an unposted document doesn't, by itself, mark the incoming document as processed. You can also use **Set To Processed** and **Set To Unprocessed** to change the value manually.

> [!NOTE]  
> Unless you specify a **Processed** filter, the **Incoming Documents** page shows only unprocessed records when you open it. This article refers to that view as the default view. Choose **Show Unprocessed** to return to it after using **Show All**.

## Remove incoming document records from the default view

1. On the **Incoming Documents** page, select one or more lines for incoming document records that you want to remove from the default view.
1. Choose the **Set To Processed** action.

    The incoming document records are removed from the default view, and the **Processed** check box is selected on the lines.

> [!NOTE]  
> You can also perform this action for the individual record on the **Incoming Document** page.

## View all incoming document records

1. On the **Incoming Documents** page, choose the **Show All** action.

Both processed and unprocessed incoming document records are displayed. Any other filters on the page still apply.

## Add incoming document records to the default view

1. On the **Incoming Documents** page, choose the **Show All** action.
1. Select one or more lines for incoming document records that you want to appear in the default view.
1. Select the **Set To Unprocessed** action.
1. Select **Show Unprocessed** to return to the default view.

> [!NOTE]  
> You can also perform this action for the individual record on the **Incoming Document** page.

## Related information
  
[Create Incoming Document Records](across-how-create-income-document-records.md)  
[Create Incoming Document Records Directly from Documents and Entries](across-how-connect-disconnect-income-document-records.md)  
[Incoming Documents](across-income-documents.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
