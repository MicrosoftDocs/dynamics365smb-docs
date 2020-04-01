---
title: Organize Items in Categories| Microsoft Docs
description: To help you search for and find items, you can assign item attributes and organize items in categories.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: category, search, attribute, facet
ms.date: 04/01/2020
ms.author: sgroespe

---
# Categorize Items
To maintain an overview of your items and to help you sort and find items, it is useful to organize your items in item categories.

To find items by characteristics, you can assign item attributes to items and also to item categories. For more information, see [Work with Item Attributes](inventory-how-work-item-attributes.md).
<br><br>  

> [!Video https://www.microsoft.com/en-us/videoplayer/embed/RE4j4mo?rel=0]

## To create an item category
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Categories**, and then choose the related link.
2. On the **Item Categories** page, choose the **New** action.
3. On the **Item Category Card** page, on the **General** FastTab, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. On the **Attributes** FastTab, specify any item attributes for the item category. For more information, see [To assign item attributes to item categories](inventory-how-work-item-attributes.md#to-assign-item-attributes-to-item-categories).

> [!NOTE]  
>   If the item category has a parent item category, as indicated by the **Parent Category** field, then any item attributes that are assigned to that parent item category are prefilled on the **Attributes** FastTab.

> [!NOTE]  
>   Item attributes that you assign to an item category will automatically apply to the item that the item category is assigned to.

## To assign an item category to an item
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
2. Open the card for the item that you want to assign to an item category.
3. Choose the lookup button in the **Item Category Code** field and select an existing item category. Alternatively, choose the **New** action to first create a new item category as explained in [To create an item category](inventory-how-categorize-items.md#to-create-an-item-category).

## See Also
[Work with Item Attributes](inventory-how-work-item-attributes.md)  
[Register New Items](inventory-how-register-new-items.md)  
[Inventory](inventory-manage-inventory.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
