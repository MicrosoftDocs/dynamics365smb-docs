---
title: Setting up tax accounting in Russia
description: Russian enhancements include tax accounting.
author: DianaMalina
ms.topic: how-to
ms.search.keywords:
ms.date: 11/13/2023
ms.reviewer: bholtorf
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Set up tax accounting

Tax accounting lets you apply rules for recognizing income and expenses that follow your local tax laws. You can activate tax accounting features in [!INCLUDE[prod_short](../../includes/prod_short.md)] by setting up tax registers.

## To activate tax accounting

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Tax Register Setup**, and then choose the related link.

2. On the **General** FastTab, select codes for the following dimensions.

   | Field                        | Description                                                  |
   | :--------------------------- | :----------------------------------------------------------- |
   | **Condition Dimension Code** | Select a dimension code that describes the condition of the tax register. |
   | **Kind Dimension Code**      | Select a dimension code that describes the type of tax register. |

3. Select the following fields to activate entries in the tax register.

   | Field                             | Description                                            |
   | :-------------------------------- | :----------------------------------------------------- |
   | **Create Acquis. FA Tax Ledger**  | Select to create fixed asset acquisition entries.      |
   | **Create Reclass. FA Tax Ledger** | Select to create fixed asset reclassification entries. |
   | **Create Acquis. FE Tax Ledger**  | Select to create future expense acquisition entries.   |

4. Select the appropriate depreciation books in the **Tax Depreciation Book** and **Future Exp. Depreciation Book** fields. The depreciation books that you select shouldn't be integrated with the [!INCLUDE[prod_short](../../includes/prod_short.md)] finance module.

5. Select the **Create Data for Printing Forms** check box to enable detailed tax register entry information to be printed on reports and forms.

6. Choose the **Close** button to close the window and save your entries.

For more information about how to set up and customize tax registers, see [Create Tax Registers](How-to-Create-Tax-Registers.md).

## Related information

[Tax Accounting](Tax-Accounting.md)  
[Tax Registers](Tax-Registers.md)  
[Create Tax Registers](How-to-Create-Tax-Registers.md)  
[Tax Differences](Tax-Differences.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
