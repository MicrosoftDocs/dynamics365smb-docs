---
title: How to Create Multiple Fixed Asset Cards [IT]
description: Learn how to automatically create multiple fixed asset cards during purchase invoice posting in Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: multiple fixed asset cards, fixed asset card, fixed asset card creation, invoice posting, Italian version
ms.date: 05/20/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

> [!NOTE]
> This feature has been delocalized and now it is part of standard Business Central worldwide.  

# Create multiple fixed asset cards in the Italian version

You can create multiple fixed asset cards automatically during purchase invoice posting. For example, if your company purchases 200 computers of the same kind from the same vendor, you don't have to manually create a fixed asset card for each computer; the fixed asset cards can be created automatically.  

## Create multiple fixed asset cards  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Assets**, and then choose the related link.  
1. Choose the **Lists** action, and then choose the **Fixed Assets** action.  
1. On the **Fixed Asset List** page, choose the **New** action.  
1. On the **Fixed Asset Card** page, fill in the relevant fields.  

   Use the value of the **No.** field when you generate the remaining fixed assets later.  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.  
1. Create a new purchase order, or open the existing purchase order.  
1. Expand the **Lines** FastTab.  
1. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Type**|Select **Fixed Asset**.|  
    |**No.**|Specify the fixed asset number.<br><br/> **NOTE:** This should be the same fixed asset number that you entered in the **Fixed Asset** list.|  
    |**No. of Fixed Asset Cards**|Specify the relevant number of duplicates for your fixed asset.<br><br/> **NOTE:** During invoice posting, duplicate fixed asset cards are automatically generated and added to the fixed asset list. The only difference between the duplicate fixed asset cards is the number assigned to each fixed asset.|  

1. Choose the **OK** button.  

## Related information

- [Fixed Assets](../../fa-manage.md)  
- [Italian Fixed Assets](italian-fixed-assets.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
