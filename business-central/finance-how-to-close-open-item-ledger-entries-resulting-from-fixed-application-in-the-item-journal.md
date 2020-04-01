---
    title: How to Close Open Item Ledger Entries Resulting from Fixed Application in the Item Journal | Microsoft Docs
    description: You can use the **Applies-from Entry** field on the **Item Journal** page to create a fixed application between an inbound transaction and the original outbound transaction. For example, to correct the outbound transaction or to process its return.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Close Open Item Ledger Entries Resulting from Fixed Application in the Item Journal
You can use the **Applies-from Entry** field on the **Item Journal** page to create a fixed application between an inbound transaction and the original outbound transaction. For example, to correct the outbound transaction or to process its return. For more information, see Applies-from Entry.  

> [!IMPORTANT]  
>  Fixed applications made in this manner only apply the cost, not the quantity. Accordingly, the posted positive item ledger entry will not close the applied outbound entry and will itself remain open. This also applies when you post a fixed application for a positive entry to a negative entry that has not been closed by a regular positive entry, then both the negative and the positive entries will remain open.  
>   
>  This also means that you cannot close an inventory period if such an entry exists.  

The following procedure shows how to close such entries by performing two corrective postings in the item journal.  

## To close open item ledger entries that result from a fixed application in the item journal  

1.  Use the **Applies-from Entry** field to post a positive adjustment with the corresponding quantity. This closes the original negative entry with a fixed application.  
2.  Use the **Applies-to Entry** field to post a negative adjustment. This closes the original corrective positive entry with a fixed application.  

## See Also  
[ Remove and Reapply Item Ledger Entries](finance-how-to-remove-and-reapply-item-entries.md)  
 [Process Sales Returns and Cancellations](sales-how-process-sales-returns-cancellations.md)   
 [Setting Up Inventory Valuation and Costing](finance-set-up-inventory-valuation-and-costing.md)   
 [Managing Inventory Costs](finance-manage-inventory-costs.md)   
 [Design Details: Costing Methods](design-details-costing-methods.md)
