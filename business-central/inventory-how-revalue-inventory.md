---
title: Create new value entries for items in the inventory| Microsoft Docs
description: Describes how to appreciate or depreciate the value entries of one or more items in inventory by posting their current, calculated value.
documentationcenter: ''
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: costing, inventory cost, value entries
ms.search.forms: 5803,
ms.date: 07/29/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Revalue inventory
If you want to appreciate or depreciate an item or a specific item ledger entry, you must use the revaluation journal.

## To revalue inventory
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Revaluation Journal**, and then choose the related link.
2. Choose the **Calculate Inventory Value** action.
3. On the **Calculate Inventory Value** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Choose the **OK** button.
5. On each line on the **Item Revaluation Journals** page, in the **Unit Cost (Revalued)** field, enter the new unit cost. Alternatively, enter the new total amount in the **Inventory Value (Revalued)** field.

    The relevant fields are automatically updated. The **Amount** field shows the actual change in inventory value for the selected item ledger entry. It calculates the difference between the **Inventory Value (Calculated)** field and the **Inventory Value (Revalued)** field.
6. When you have completed all lines in the revaluation journal, choose the **Post** action.

New value entries are now created to reflect the revaluations that you have posted. You can see the new values on the respective item cards.

## Related information
[Design Details: Revaluation](design-details-revaluation.md)    
[Inventory](inventory-manage-inventory.md)    
[Sales](sales-manage-sales.md)    
[Purchasing](purchasing-manage-purchasing.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
