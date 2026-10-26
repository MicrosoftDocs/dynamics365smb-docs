---
title: Create Multiple Fixed Asset Cards in the Italian Version [IT]
description: Learn how to create multiple fixed asset cards during purchase invoice posting in Business Central and split the acquisition amount among the assets.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: multiple fixed asset cards, fixed asset card, fixed asset card creation, invoice posting, Italian version
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Create multiple fixed asset cards in the Italian version

> [!NOTE]
> This feature has been delocalized and is now part of standard Business Central worldwide.  

You can create multiple fixed asset cards automatically during purchase invoice posting. For example, if your company purchases 200 computers of the same kind from the same vendor, you don't have to manually create a fixed asset card for each computer; the fixed asset cards can be created automatically.  

## Create multiple fixed asset cards  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Fixed Assets**, and then choose the related link.  
1. On the **Fixed Asset List** page, choose the **New** action.  
1. On the **Fixed Asset Card** page, fill in the relevant fields.  

   Use the value of the **No.** field when you generate the remaining fixed assets later.  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Purchase Orders**, and then choose the related link.  
1. Create a new purchase order, or open the existing purchase order.  
1. Expand the **Lines** FastTab.  
1. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Type**|Select **Fixed Asset**.|  
    |**No.**|Specify the fixed asset number.<br><br/> **NOTE:** This should be the same fixed asset number that you entered in the **Fixed Asset** list.|  
    |**Quantity**|Enter the quantity purchased, and enter the cost information for the purchase line.|
    |**No. of Fixed Asset Cards**|Enter the total number of fixed assets, including the card selected in **No.** For example, enter **200** to use that card and create 199 additional cards.|

1. Post the purchase invoice, or receive and invoice the purchase order when it's ready.

During invoice posting, [!INCLUDE[prod_short](../../includes/prod_short.md)] copies the original fixed asset card, depreciation books, and default dimensions to the additional cards. The acquisition amount is divided among the specified number of fixed assets. **Fixed Asset Nos.** must be configured on **Fixed Asset Setup** so that the additional cards can receive numbers.

## Related information

- [Fixed Assets](../../fa-manage.md)  
- [Italian Fixed Assets](italian-fixed-assets.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
