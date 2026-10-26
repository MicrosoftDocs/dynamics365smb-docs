---
title: Set Up Tax Accounting in Russia
description: Learn how to set up and activate tax accounting in Business Central for Russia.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: tax accounting, activate tax accounting, Russia
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Set up tax accounting

Tax accounting lets you apply rules for recognizing income and expenses that follow your local tax laws. You can activate tax accounting features in [!INCLUDE[prod_short](../../includes/prod_short.md)] by setting up tax registers.

## Activate tax accounting

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Tax Register Setup**, and then choose the related link.

1. On the **General** FastTab, select codes for the following dimensions.

   | Field | Description |
   |:-|:-|
   | **Condition Dimension Code** | Select a dimension code that describes the condition of the tax register. |
   | **Kind Dimension Code** | Select a dimension code that describes the type of tax register. |

1. Select the following fields to activate entries in the tax register.

   | Field | Description |
   |:-|:-|
   | **Create Acquis. FA Tax Ledger** | Select to create fixed asset acquisition entries. |
   | **Create Reclass. FA Tax Ledger** | Select to create fixed asset reclassification entries. |
   | **Create Acquis. FE Tax Ledger** | Select to create future expense acquisition entries. |

1. Select the appropriate depreciation books in the **Tax Depreciation Book** and **Future Exp. Depreciation Book** fields. The depreciation books that you select shouldn't be integrated with the [!INCLUDE[prod_short](../../includes/prod_short.md)] finance module.

1. Select the **Create Data for Printing Forms** check box to enable detailed tax register entry information to be printed on reports and forms.

1. Choose the **Close** button to close the window and save your entries.

Learn more in [Create Tax Registers](how-to-create-tax-registers.md) for more information about how to set up and customize tax registers.

## Related information

- [Tax Accounting](tax-accounting.md)  
- [Tax Registers](tax-registers.md)  
- [Create Tax Registers](how-to-create-tax-registers.md)  
- [Tax Differences](tax-differences.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
