---
title: 'Advanced: Inventory Reconciliation| Microsoft Docs'
description: 'Describes how your inventory value in reconciled with the general ledger.'
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2017
ms.author: sgroespe

---
## Advanced: Inventory Reconciliation
When you post inventory transactions, such as sales shipments, purchase invoices, or inventory adjustments, the changed item costs are recorded in item value entries. To reflect this change of inventory value in your financial books, the inventory costs are automatically posted to the related inventory accounts in the general ledger. For each inventory transaction that you post, the appropriate values are posted to the inventory account, adjustment account, and COGS account in the general ledger.

Even though inventory costs are automatically posted to the general ledger, it is still necessary to ensure that the costs of goods are forwarded to the related outbound sales transaction, especially in situations where you sell goods before you invoice the purchase of those goods. This is referred to as cost adjustment, which you can perform manually or set up to happen automatically when you post an item transaction. For more information, see [How to: Adjust Item Costs](inventory-how-adjust-item-costs.md).

## See Also
[Inventory](inventory-manage-inventory.md)  
[Advanced: Best Price Calculation](advanced-best-price-calculation.md)
