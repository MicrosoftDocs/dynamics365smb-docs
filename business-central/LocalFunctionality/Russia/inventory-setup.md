---
title: Inventory setup in Russia
description: Russian enhancements include inventory.
author: DianaMalina


ms.topic: install-set-up-deploy
ms.search.keywords:
ms.date: 04/01/2021
ms.reviewer: bholtorf
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Inventory Setup

As part of inventory management, you can set up inventory to: 

- Assign item charges on purchases from foreign countries/regions based on weight or volume
- Use the same column for original and corrective postings

## Item Charge Assignment in Purchase Documents

In Russia, [!INCLUDE[prod_short](../../includes/prod_short.md)] can assign item charges on purchases from foreign countries/regions based on weight or volume. For each item, in the **Item Card** window, on the **Foreign Trade** FastTab, if the **Gross Weight Mandatory** and **Unit Volume Mandatory** check boxes are selected, you must fill in the **Gross Weight** and **Unit Volume** fields. When you suggest an item charge assignment on a purchase order, you must specify that the distribution principle, weight, and volume are added to the options to choose from. For more information, see [Use Item Charges to Account for Additional Trade Costs](../../payables-how-assign-item-charges.md).

## Item Corrections

You can set up inventory to use the same column for original and corrective postings. This is often referred to as *red storno*.

You can use red storno posting to post corrections for the following inventory entries:

- Corrective entries in the item journal
- Reversal of item documents such as item receipts and item shipments
- Posting item revaluation or item reclassification journals
- Periodic adjustments of item costs

For more information, see [Post Red Storno Corrections](How-to-Post-Red-Storno-Corrections.md).

### Adjusting Item Cost

If you select the Enable Red Storno field in the **Inventory Setup** window, then negative deviations are posted according to red storno when you run the **Adjust Cost - Item Entries** batch job.

## Related information

[Item Documents](Item-Documents.md)  
[Item Obligatory Acts](Item-Obligatory-Acts.md)  
[Post Red Storno Corrections](How-to-Post-Red-Storno-Corrections.md)  
[Use Item Charges to Account for Additional Trade Costs](../../payables-how-assign-item-charges.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
