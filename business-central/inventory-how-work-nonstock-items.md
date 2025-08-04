---
title: Create and manage catalog items
description: Learn how to sell items that you don't keep in your list of items.
author: brentholtorf 
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 11/21/2024
ms.custom: bap-template
ms.search.keywords: non-inventoriable
ms.search.forms: 5725, 5726, 5732
ms.service: dynamics-365-business-central
---

# Work with catalog items

Catalog items are items that you don't manage in [!INCLUDE[prod_short](includes/prod_short.md)] until you sell them. When you use the **Select Catalog Item** action to add a catalog item to a line on a sales order, quote, or blanket sales order, the catalog item is converted to a regular item.

> [!NOTE]  
> You can't select a catalog item from the **Sales Invoice** page.

A catalog item typically has the item number of the vendor who supplies it. Before you can convert a catalog item to a normal item, you must specify how to convert vendor item numbers to your item numbering. To learn more about item numbering, go to [Specify how catalog item numbers are converted to your own numbering](#specify-how-catalog-item-numbers-are-converted-to-your-own-numbering).  

> [!IMPORTANT]
> Catalog items are not to be mistaken with non-inventory items, which are regular items that are given the type **Non-Inventory** to keep them out of availability and costing calculations, for example, because they are only used internally and have a low cost. To learn move about non-inventory items, go to [About Item Types](inventory-about-item-types.md).

## Create a catalog item

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Catalog Items**, and then choose the related link.
2. On the **Catalog Items** page, choose the **New** action.
3. On the **Catalog Item Card** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## Specify how catalog item numbers are converted to your own numbering

Before you can convert a catalog item to a regular item, you must specify how to convert vendor item numbers to the structure you use for item numbers.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Catalog Item Setup**, and then choose the related link.
2. In the **No. Format** field, choose the option you prefer.

## Convert a catalog item to a normal item

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Catalog Items**, and then choose the related link.
2. Open the card for a catalog item that you want to convert to a normal item.
3. On the **Catalog Item Card** page, choose the **Create Item** action.

A new item card prefilled with information from the catalog item and an item template is created. You can edit the information about the new item if needed. To learn more about creating items, go to [Register New Items](inventory-how-register-new-items.md).

> [!NOTE]  
> An item reference is automatically created between the vendor's item number and your new item number. To learn more about item references, go to [Use Item References](inventory-how-use-item-cross-refs.md).

## To sell a catalog item and convert it to a normal item

The following process uses a sales order, but the steps are the same for blanket sales orders and quotes.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.
2. Choose the **New** action. Fill in the fields on the **General** FastTab as for any sales order. For more information, see [Sell Products](sales-how-sell-products.md).
3. On a new sales line, in the **Type** field, select **Item**, but leave the **No.** field empty.
4. Choose the **Line** action, and then choose the **Select Catalog Items** action.
5. On the **Catalog Items** page, select the catalog item that you want to sell, and then choose the **OK** button.
   The catalog item automatically converts to a normal item, and the new normal item is selected on the sales line.
6. When the sales order is complete, choose the **Post** action.

> [!IMPORTANT]
> If you change you mind and delete the sales line, the automatically created item is also deleted. Deleting the item helps reduce clutter in you list of items.
>
> The item is also deleted if you convert the item manually, or make changes such as adding new units of measure or updating prices or cost. However, the item won't be deleted if it's already used in sales or purchase lines, assembly BOMs, or has ledger entries.

## Related information

[Register New Items](inventory-how-register-new-items.md)  
[Create Special Orders](sales-how-to-create-special-orders.md)  
[Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
