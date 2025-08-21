---
title: Organize items in categories
description: To help you search for and find items, you can assign item attributes and organize items in categories.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: category, search, attribute, facet
ms.search.form: 5730, 5733, 5401
ms.date: 06/10/2024
ms.service: dynamics-365-business-central
---

# Categorize items

To maintain an overview of your items and to help you sort and find items, it's useful to organize your items in item categories.

To find items by characteristics, you can assign item attributes to items and also to item categories. For more information, see [Work with Item Attributes](inventory-how-work-item-attributes.md).
<br><br>  

> [!Video https://learn-video.azurefd.net/vod/player?id=4c02e1d8-7569-4eb4-94cf-105899787978]

## To create an item category
1. [!INCLUDE[open-search](includes/open-search.md)], enter **Item Categories**, and then choose the related link.
2. On the **Item Categories** page, choose the **New** action.
3. On the **Item Category Card** page, on the **General** FastTab, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. On the **Attributes** FastTab, specify any item attributes for the item category. For more information, see [To assign item attributes to item categories](inventory-how-work-item-attributes.md#assign-item-attributes-to-item-categories).

> [!NOTE]  
> If the item category has a parent item category, as indicated by the **Parent Category** field, then any item attributes that are assigned to that parent item category are prefilled on the **Attributes** FastTab.

> [!NOTE]  
> Item attributes that you assign to an item category will automatically apply to the item that the item category is assigned to.

If you change your mind about an item category, you can delete it. However, if the category is assigned to an item, you must remove that assignment beforehand.

## To assign an item category to an item

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Items**, and then choose the related link.
2. Open the card for the item that you want to assign to an item category.
3. Choose the lookup button in the **Item Category Code** field and select an existing item category. Alternatively, choose the **New** action to first create a new item category as explained in [To create an item category](inventory-how-categorize-items.md#to-create-an-item-category).

## Categories, attributes, and variants

[!INCLUDE[inventory_variant](includes/inventory_variant.md)]

## Related information

[Work with Item Attributes](inventory-how-work-item-attributes.md)    
[Manage Product Variants](inventory-item-variants.md)    
[Register New Items](inventory-how-register-new-items.md)    
[Inventory](inventory-manage-inventory.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
