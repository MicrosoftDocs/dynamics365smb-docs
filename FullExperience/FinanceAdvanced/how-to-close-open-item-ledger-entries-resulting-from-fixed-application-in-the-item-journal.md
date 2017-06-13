---
title: "How to: Close Open Item Ledger Entries Resulting from Fixed Application in the Item Journal"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "fixed application"
  - "item entries, close"
ms.assetid: 70a2bfb2-0ab8-4209-90b2-dcc001fccc59
caps.latest.revision: 6
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
---
# How to: Close Open Item Ledger Entries Resulting from Fixed Application in the Item Journal
You can use the **Applies\-from Entry** field in the **Item Journal** window to create a fixed application between an inbound transaction and the original outbound transaction. For example, to correct the outbound transaction or to process its return. For more information, see [Applies\-from Entry](../Topic/\($%20T_83_5807%20Applies-from%20Entry%20$\).md).  
  
> [!IMPORTANT]  
>  Fixed applications made in this manner only apply the cost, not the quantity. Accordingly, the posted positive item ledger entry will not close the applied outbound entry and will itself remain open. This also applies when you post a fixed application for a positive entry to a negative entry that has not been closed by a regular positive entry, then both the negative and the positive entries will remain open.  
>   
>  This also means that you cannot close an inventory period if such an entry exists.  
  
 The following procedure shows how to close such entries by performing two corrective postings in the item journal.  
  
### To close open item ledger entries that result from a fixed application in the item journal  
  
1.  Use the **Applies\-from Entry** field to post a positive adjustment with the corresponding quantity. This closes the original negative entry with a fixed application.  
  
2.  Use the **Applies\-to Entry** field to post a negative adjustment. This closes the original corrective positive entry with a fixed application.  
  
## See Also  
 [Applies\-from Entry](../Topic/\($%20T_83_5807%20Applies-from%20Entry%20$\).md)   
 [Applies\-to Entry](../Topic/\($%20T_83_29%20Applies-to%20Entry%20$\).md)   
 [Item Journal](assetId:///dfc0499a-34a8-42f6-9538-cf9c8e42fd31)   
 [How to: Create Sales Return Orders](../Sales/how-to-create-sales-return-orders.md)   
 [How to: Assign Exact Cost Reversing in Sales](../Finance/how-to-assign-exact-cost-reversing-in-sales.md)   
 [Manage Inventory Costs](../Finance/manage-inventory-costs.md)   
 [Design Details: Costing Methods](../ApplicationDesign/design-details-costing-methods.md)