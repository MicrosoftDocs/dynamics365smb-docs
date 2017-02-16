---
title: 'How to: Adjust Item Costs| Microsoft Docs'
description: 'How to: Adjust Item Costs'
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: project-madeira
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/08/2017
ms.author: sgroespe

---
# How to: Adjust Item Costs
The cost of an item (inventory value) that you purchase and later sell may change during its lifetime, for example because a freight cost is added to its purchase cost after you have sold the item. To always know the correct inventory value, item costs must therefore regularly be adjusted.
This ensures that sales and profit statistics are up to date and that financial KPIs are correct.

**Note**: Item costs are adjusted by the FIFO costing method only. This means that an item’s unit cost is the actual value of any receipt of the item, and that inventory is valuated with the assumption that the first items placed in inventory are sold first.

The cost adjustment function processes only value entries that have not yet been adjusted. If the function encounters a situation where changed inbound costs need to be forwarded to associated outbound entries, then new adjustment value entries are created, which are based on the information in the original value entries but contain the adjustment amount. The cost adjustment function uses the posting date of the original value entry in the adjustment entry, unless that date is in a closed inventory period. In that case, the program uses the starting date of the next open inventory period. If inventory periods are not used, then the date in the **Allow Posting From** field in the **General Ledger Setup** window will define when the adjustment entry is posted.

You can adjust item costs in two ways:  

* Automatically, by having the system adjusted any cost changes every time that inventory transactions occur.  
* Manually, by running the **Adjust Cost - Item Entries** batch job for one or more items when you know that their costs have changed.

Changes in inventory value from trade are automatically reconciled with your financial books when you post item transactions. For more information, see [Advanced: Inventory Reconciliation](advanced-inventory-reconciliation.md).

## To adjust item costs automatically
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Inventory Setup**, and then  choose the related link.
2. In the **Inventory Setup** window, in the **Automatic Cost Adjustment** field, select one of the following values.

| Option | Behavior |
| --- | --- |
| Never |Costs are not adjusted when posting |
| Day |Costs are adjusted if posting occurs within one day from the work date |
| Week |Costs are adjusted if posting occurs within one week from the work date |
| Month |Costs are adjusted if posting occurs within one month from the work date |
| Quarter |Costs are adjusted if posting occurs within one quarter from the work date |
| Year |Costs are adjusted if posting occurs within one year from the work date |
| Always |Costs are always adjusted when posting, irrespective of the posting date |

## To adjust item costs manually
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Adjust Cost - Item Entries**, and then choose the related link.
2. In the **Adjust Cost - Item Entries** window, specify which items to adjust costs for and whether the adjusted costs will be posted to the general ledger at the same time.

## See Also
[Advanced: Inventory Reconciliation](advanced-inventory-reconciliation.md)  
[Inventory](inventory-manage-inventory.md)  
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working With [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
