---
title: Status Field on Documents
description: Learn about the 'Open' and 'Released' status on quote, order, or credit memo documents.
author: brentholtorf
ms.service: dynamics-365-business-central
ms.topic: article
ms.search.keywords: document, status, quote, order, credit memo, released, open, pending approval, pending prepayment,
ms.search.form: 
ms.date: 09/19/2022
ms.author: bholtorf
ms.reviewer: bholtorf
---
# Status Field on Documents

When you create a quote, order, or credit memo, the **Status** field on the document header contains the status **Open** by default.

After you've filled in the document, you can release it, and [!INCLUDE[prod_short](includes/prod_short.md)] changes the value in the **Status** field to **Released**. This status indicates that the order is ready for the next stage of processing before it's posted.

| Status | Description |
| ------ | ----------- |
| Open   | You can make changes to the document. |
| Released | The document has been released to the next stage of processing, and you can't make changes to lines of type *Item* and *Fixed Asset*.<br /><br />You can reopen a released document if you want to make changes to its contents. To move the adjusted document to the next stage of processing, you must once again release the document. |
| Pending Approval   | The document is waiting to be approved. |
| Pending Prepayment | A prepayment invoice has been posted for the document. |

## Release process

You can use the release process in different ways to ease your normal workflow, for example, to follow company procedures about approvals or to start warehouse activities.

### Approval procedures

Your company can use the release procedure to indicate that another user has approved the document or that an external contact can meet the specifications of the document, as shown in these examples:

* You can only release a purchase order when your vendor has indicated that they're prepared to fulfill the order.
* You create an order and a second user must approve it, perhaps for security reasons, before you're allowed to release it.
* The manager responsible for approving all refunds must release a credit memo that you've created.

Learn more about approval workflows at [Use Workflows](across-use-workflows.md).

### Warehouse activities

If the order status is **Open**, the warehouse won't begin to prepare the shipment, and doesn't expect to receive the items on a purchase order. When you release the order, you indicate that the order is complete, and that the warehouse can include it in its activities.

## Reopen a released order

You can make changes to a released order by reopening it. However, you can only increase the quantity of the lines already processed by the warehouse.

When you make the changes and release the order again, [!INCLUDE [prod_short](includes/prod_short.md)] recalculates the value-added tax (VAT) and the invoice discount.

If you make changes to a released order, you must notify the warehouse about the changes.

> [!NOTE]
> If you want to post a single open order or credit memo without releasing it first, [!INCLUDE [prod_short](includes/prod_short.md)] will automatically release the document when you post it. If you post your orders or credit memos by using the **Post Batch** function, you can choose to post only the orders or credit memos that you've released.

## Related information

[Sell Products with a Customer Sales Order](sales-how-sell-products.md)  
[Record Purchases with Purchase Invoices](purchasing-how-record-purchases.md)  
[Ship Items](warehouse-how-ship-items.md)  
[Receive Items](warehouse-how-receive-items.md)  
[Use Approval Workflows](across-how-use-approval-workflows.md)  
[Sorting, Searching, and Filtering Lists](ui-enter-criteria-filters.md)  
[Archive Documents](across-how-to-archive-documents.md)  
[General Business Functionality](ui-across-business-areas.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
