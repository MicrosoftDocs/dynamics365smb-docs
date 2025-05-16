---
title: Creating fixed asset charges in Russia
description: Russian enhancements include fixed asset charges.
author: DianaMalina


ms.topic: how-to
ms.search.keywords:
ms.date: 04/01/2021
ms.reviewer: bholtorf
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Create a Fixed Asset Charge

The following procedure shows how to create a new fixed asset charge. 

## To create a fixed asset charge

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Charge Card**, and then choose the related link.

2. On the **General** FastTab, fill in the fields as described in the following table.

   | Field                        | Description                                                  |
   | :--------------------------- | :----------------------------------------------------------- |
   | **No.**                      | Specify the fixed asset charge code.                         |
   | **Description**              | Specify the description of the fixed asset charge.           |
   | **Gen. Prod. Posting Group** | Specify the default general product posting group that will be used for the fixed asset charge code. |
   | **VAT Prod. Posting Group**  | Specify the default VAT product posting group that will be used for the fixed asset charge code. |
   | **Global Dimension 1 Code**  | Specify the global dimension code that is associated with the fixed asset charge. |
   | **Global Dimension 2 Code**  | Specify the global dimension code that is associated with the fixed asset charge. |
   | **Exclude Cost for TA**      | Select if you want to exclude the fixed asset charge from tax accounting. |
   | **G/L Acc. For Released FA** | Specify the general ledger account to post the fixed asset charge amount to when the fixed asset is released. |
   | **Tax Difference Code FA**   | Specify the tax difference code that is associated with the fixed asset charge. |

## Related information

[Setting Up Fixed Assets](../../fa-setup.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
