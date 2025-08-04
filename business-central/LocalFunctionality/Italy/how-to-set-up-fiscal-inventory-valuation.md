---
title: How to Set Up Fiscal Inventory Valuation [IT]
description: Learn how to set up fiscal inventory valuation for item costing in the Italian version of Business Central using the Item Costing Setup feature.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: set up fiscal inventory valuation, fiscal inventory valuation, item costing, item costing setup, Italian version
ms.date: 05/21/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up fiscal inventory valuation in the Italian version

To use fiscal inventory valuation, you must set up inventory valuation methods.  

## Set up fiscal inventory valuation for item costing  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Costing Setup**, and then choose the related link.  
1. On the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Components Valuation**|Specify the fiscal inventory valuation method.|  
    |**Estimated WIP Consumption**|Select to include the finished production orders or the released production orders for the cost calculation.<br><br/> If this field is cleared, then consumption and capacity ledger entries are filtered by posting date.|  

1. Choose the **OK** button.  

## Steps to set up fiscal inventory valuation for an item  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
1. On the **Item List** page, select each item, and then, on the **General** FastTab, in the **Inventory Valuation** field, specify the inventory valuation type.  
1. Choose the **OK** button.  

## Related information

[Fiscal Inventory Valuation](fiscal-inventory-valuation.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
