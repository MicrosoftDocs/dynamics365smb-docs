---
title: Release and Reopen Sales and Purchase Documents
description: Release sales and purchase documents to make them ready for further processing. Reopen documents when you need to change them before posting.
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to
ms.date: 11/10/2026
ai-usage: ai-assisted
ms.custom: bap-template
author: jswymer
---

# Release and reopen sales and purchase documents

In this article, you learn how to release or reopen sales and purchase documents like an order, invoice, and quote. You release sales and purchase documents to move them to the next stage of processing before they're posted. For orders that require warehouse handling, releasing the order makes it available for warehouse processing.

## Release a sales or purchase document

1. Open the document that you want to release as follows:

   1. [!INCLUDE[open-search](includes/open-search.md)], enter the document type you're looking for, such as **Sales Orders** or **Purchase Orders**, and then choose the related link.
   1. In the list, select the document to open it.
1. In the action bar at the top, select **Release**.

   The **Status** field changes to **Released**.

> [!NOTE]
> Approval workflows or prepayment requirements can prevent a document from being released. An order can have the **Pending Prepayment** status if a required prepayment hasn't been fully invoiced or if a posted prepayment invoice is unpaid and **Check Prepmt. when Posting** is turned on. Learn more in [Document statuses](ui-document-status.md).

## Reopen a sales or purchase document

You can make changes to a released sales and purchase document by reopening it.

1. Open the document that you want to reopen as follows:

   1. [!INCLUDE[open-search](includes/open-search.md)], enter the document type you're looking for, such as **Sales Orders** or **Purchase Orders**, and then choose the related link.
   1. In the list, select the document to open it.
1. In the action bar at the top, select **Reopen**.

   The **Status** field changes to **Open**.

You can now make changes to the document before you release it again.

> [!NOTE]
> Reopening a document doesn't remove warehouse restrictions. For example, you can't change the item, location, or unit of measure on a line while related warehouse lines exist. Coordinate changes with the warehouse before you release the document again.

## Related information
  
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]