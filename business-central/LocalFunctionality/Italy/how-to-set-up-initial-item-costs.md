---
title: Set Up Initial Item Costs in the Italian Version [IT]
description: Learn how to set up initial item costs using the Before Start Item Cost page in the Italian version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: configure initial item costs, set up item costs, initial item cost, before start item cost, Italian version
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up initial item costs in the Italian version

Use **Before Start Item Cost** when fiscal valuation needs quantities and costs from before you started using [!INCLUDE[prod_short](../../includes/prod_short.md)].

On the **Before Start Item Cost** page, you can enter information about inventory items, such as component costs, routing costs, and overhead costs.  

## Set up initial item costs  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Before Start Item Cost**, and then choose the related link.  
1. Choose the **New** action.  
1. Select **Item No.**, and enter **Starting Date**. Enter the historical **Purchase Quantity**, **Purchase Amount**, and **Production Quantity** that apply to the item.
1. Enter the production cost components in **Direct Components Amount**, **Direct Routing Amount**, **Overhead Routing Amount**, and **Subcontracted Amount**. The read-only **Production Amount** is calculated from those fields.
1. Choose the **OK** button.  

The fiscal cost calculation uses these records as historical input. They don't post inventory quantities or general ledger entries. Run **Calculate End Year Costs**, and review the results on **Item Cost History List**.

## Related information

- [Fiscal Inventory Valuation](fiscal-inventory-valuation.md)
- [Set Up Fiscal Inventory Valuation](how-to-set-up-fiscal-inventory-valuation.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
