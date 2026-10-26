---
title: Set Up Fiscal Inventory Valuation in the Italian Version [IT]
description: Learn how to set up fiscal inventory valuation for item costing in the Italian version of Business Central using the Item Costing Setup feature.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: set up fiscal inventory valuation, fiscal inventory valuation, item costing, item costing setup, Italian version
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up fiscal inventory valuation in the Italian version

To use fiscal inventory valuation, you must set up inventory valuation methods.  

## Set up fiscal inventory valuation for item costing  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Item Costing Setup**, and then choose the related link.  
1. On the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Components Valuation**|Specify the fiscal inventory valuation method.|  
    |**Estimated WIP Consumption**|Select to calculate estimated production costs from production order components and routing lines. If cleared, the calculation uses consumption and capacity ledger entries.|

1. Choose the **OK** button.  

## Steps to set up fiscal inventory valuation for an item  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Items**, and then choose the related link.  
1. Open the item card, and set **Inventory Valuation** to the required fiscal valuation method. For **Discrete LIFO**, also specify **Lifo Category**.
1. Choose the **OK** button.  

## Related information

[Fiscal Inventory Valuation](fiscal-inventory-valuation.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
