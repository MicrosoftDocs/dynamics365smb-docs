---
title: Create Item Cards for Goods or Services| Microsoft Docs
description: You create item cards for services that you sell as hours and for physical products, such as assembly items, finished goods, components, or raw material, that you sell from your inventory.
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: item, finished good, component, raw material, assembly item
ms.date: 06/02/2017
ms.author: sgroespe

---
# How to: Register New Items
Items, among other products, are the basis of your business, the goods or services that you trade in. Each item must be registered as an item card.

Item cards hold the information that is required to buy, store, sell, deliver, and account for items.

The item card can be of type **Inventory** or **Service** to specify if the item is a physical unit or a labor time unit. Apart from some fields that relate to the physical aspects of an item, all fields on an item card function in the same way for inventory items and services. For more information about selling an item, see [How to: Sell Products](sales-how-sell-products.md) or [How to: Invoice Sales](sales-how-invoice-sales.md).

An item can be structured as a parent item with underlying child items in a bill of materials (BOM). In [!INCLUDE[d365fin](includes/d365fin_md.md)], a bill of materials is referred to as an assembly BOM. You use assembly BOMs to structure parent items that you sell as kits consisting of the parent's components or that you assemble to order or to stock. For more information, see [How to: Work with Bills of Materials](inventory-how-work-BOMs.md).

**Note**: If item templates exist for different item types, then a window appears when you create a new item card from where you can select an appropriate template. If only one item template exists, then new item cards always use that template.

## To create a new item card
1. On the Home page, choose the **Items** action to open the list of existing items.  
2. In the **Items** window, choose the **New** action.

    If only one item template exists, then a new item card opens with some fields filled with information from the template.
3. In the **Select a template for a new item** window, choose the template that you want to use for the new item card.
4. Choose the **OK** button. A new item card opens with some fields filled with information from the template.
5. Proceed to fill or change fields on the item card as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

On the **Price and Posting** FastTab, you can view special prices or discounts that you grant for the item if certain criteria are met, such as customer, minimum order quantity, or ending date. Each row represents a special price or line discount. Each column represents a criterion that must apply to warrant the special price that you enter in the **Unit Price** field, or the line discount that you enter in the **Line Discount %** field. For more information, see [Record Sales Price, Discount, and Payment Agreements](sales-how-record-sales-price-discount-payment-agreements.md).

The item is now registered, and the item card is ready to be used on purchase and sales documents.

If you want to use this item card as a template when you create new item cards, you can save it as a template. For more information, see the following section.

## To save the item card as a template
1. In the **Item Card** window, choose the **Save as Template** action. The **Item Template** window opens showing the item card as a template.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. To reuse dimensions in templates, choose the **Dimensions** action. The **Dimension Templates** window opens showing any dimension codes that are set up for the item.
4. Edit or enter dimension codes that will apply to new item cards created by using the template.
5. When you have completed the new item template, choose the **OK** button.

The item template is added to the list of item templates, so that you can use it to create new item cards.

## See Also
  [Inventory](inventory-manage-inventory.md)  
  [Purchasing](purchasing-manage-purchasing.md)  
  [Sales](sales-manage-sales.md)  
  [Working With [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](ui-work-product.md)
