---
title: Close item ledger entries that came from using fixed application
description: Learn how you can create a fixed application between an inbound transaction and the original outbound transaction in the item journal.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form: 40
ms.date: 07/30/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Close open item ledger entries resulting from fixed application in the item journal

You can use the **Applies-from Entry** field on the **Item Journal** page to create a fixed application between an inbound transaction and the original outbound transaction. For example, to correct the outbound transaction or to process its return.  

> [!IMPORTANT]  
> Fixed applications made in this manner only apply the cost, not the quantity. Accordingly, the posted positive item ledger entry will not close the applied outbound entry and will itself remain open. This also applies when you post a fixed application for a positive entry to a negative entry that has not been closed by a regular positive entry, then both the negative and the positive entries will remain open.  
>
> This also means that you cannot close an inventory period if such an entry exists.  

You can change and reapply application entries under certain conditions by using the **Application Worksheet** page.  

The following procedure shows how to close such entries by performing two corrective postings in the item journal.  

## To close open item ledger entries that result from a fixed application in the item journal  

1. Use the **Applies-from Entry** field to post a positive adjustment with the corresponding quantity. This closes the original negative entry with a fixed application.  

    The **Applies-from Entry** field specifies the number of the outbound item ledger entry whose cost is forwarded to the inbound item ledger entry when you post an inbound transaction of type **Positive Adjmt.** or **Purchase** with the item journal.  
2. Use the **Applies-to Entry** field to post a negative adjustment. This closes the original corrective positive entry with a fixed application.  

    The **Applies-to Entry** field specifies if the quantity in the item journal line should be applied to an already-posted document. If so, enter the entry number of the item ledger entry to which the item journal line should be applied.

## Related information

[Remove and Reapply Item Ledger Entries](finance-how-to-remove-and-reapply-item-entries.md)    
[Process Sales Returns and Cancellations](sales-how-process-sales-returns-cancellations.md)    
[Setting Up Inventory Valuation and Costing](finance-set-up-inventory-valuation-and-costing.md)    
[Managing Inventory Costs](finance-manage-inventory-costs.md)    
[Design Details: Costing Methods](design-details-costing-methods.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
