---
title: Reverse and correct production order transactions
description: Learn how to reverse consumption, output, or capacity transactions on production orders, finish orders without output, and reopen finished orders.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.form: 99000768, 99000779, 99000780, 99000866
ms.date: 06/17/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Reverse and correct production order transactions

Even when production doesn't go as planned, it's important to keep your inventory, cost, and financial records accurate. You can revert consumption or output transactions, return unused raw materials, and correct mistakes in your reported operations. For actual scrap occurrences, [!INCLUDE [prod_short](includes/prod_short.md)] provides a process that lets you close orders and write off accumulated WIP.

## Reverse production order transactions

When you post production transactions by mistake, you probably want to cancel (undo) the transactions, and in some cases close the order. To do that, from the **Released Production Order** page, open the **Item Ledger entries** or **Capacity Ledger entries** pages and use the **Reverse Production Order Transaction** action.

- For item ledger entries of the type **Consumption**, the action creates item journal lines of the type **Consumption**. For the lines, it copies values from the original transaction, uses the opposite sign in the **Quantity** field, applies to the original entry, and posts the item journal.
- For item ledger entries of the types **Output** or **Capacity**, the action creates item journal lines of the type **Output**. For the lines, it copies values from original transaction, uses the opposite sign in the **Quantity**, **Scrap Quantity**, **Setup Time**, and **Run time** fields, applies to the original entry (only for item ledger entries), and posts the item journal. It also removes the **Finished** status from the related production routing line.

The **Reverse Production Order Transaction** action is only enabled for entries that are related to the production order. It uses the original posting date.

The action isn't supported under the following conditions:

- If the output entry was already applied to an outbound transaction.
- If consumption/output involve warehouse handling. Bins are supported.
- Entries were created through subcontracting purchase orders. You can undo receipt in the Posted Purchase Receipt page.

## Undo subcontracting receipts

You can undo subcontracting receipts before you post them as invoiced. To do so, go to the posted purchase receipt, select the line, and choose the **Undo** action. As a result, an identical line with an opposite sign in the **Quantity** field is created along with the capacity ledger entry. And, if the canceled receipt line is linked to the last routing operation, an item ledger entry of the type **Output**. You can't reverse a receipt if it's invoiced or if the production order is finished.

> [!NOTE]
> If posting a subcontracting receipt caused consumption of components due to the flushing method, the consumption transactions aren't reverted. You must reverse them separately by using an output journal or the **Reverse Production Order Transaction** action.

## Finish a production order without output

After you revert and correct the records, you can change the status of the production order to **Finished**. This also applies to scenarios where actual scrap occurred and there's no output to allocate the accumulated work in process (WIP).

To set up this capability, turn on the **Finish Order Without Output** toggle on the **Manufacturing Setup** page.

> [!NOTE]
> After you turn on the toggle, you can't turn it off again. However, you can decide whether to write off WIP for each order individually.

When you change the status of a released production order that has consumption or capacity ledger entries but no output, turn on the **Allow Finishing Prod. Order with no output** toggle on the **Change production order status** page.

The system posts the accumulated WIP amounts to your inventory adjustment account. Fill in the **Inventory Adjustment Account** on the **General Posting Setup** page for the entry defined by:

- The **Gen. Bus. Posting Group** field on the production order.
- The **Gen. Prod. Posting Group** field on the produced item.

## Reopen a finished production order to make corrections

After you complete a production order and set its status to **Finished**, you might discover a mistake. For example, you might find that consumption is missing or the item tracking information is incorrect. To make sure that your inventory and cost transactions are correct, use the **Reopen** action on the **Finished Production Orders** page to make adjustments. However, to protect your data there are a few restrictions:

- You can only reopen an order one time.
- You can't reopen an order that has no output and cost was written off to an adjustment account.

## Related information

[Register Consumption and Output for One Released Production order line](production-how-to-register-consumption-and-output.md)  
[Batch Post Production Consumption](production-how-to-post-consumption.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
