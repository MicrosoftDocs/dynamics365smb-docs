---
title: Create Item Cards for Goods or Services| Microsoft Docs
description: You create item cards for services that you sell as hours and for physical products, such as assembly items, finished goods, components, or raw material, that you sell from your inventory.
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: item, finished good, component, raw material, assembly item
ms.date: 08/31/2017
ms.author: sgroespe

---
# Register New Items
Items, among other products, are the basis of your business, the goods or services that you trade in. Each item must be registered as an item card.

Item cards hold the information that is required to buy, store, sell, deliver, and account for items.

The item card can be of type **Inventory** or **Service** to specify if the item is a physical unit or a labor time unit. Apart from some fields that relate to the physical aspects of an item, all fields on an item card function in the same way for inventory items and services. For more information about selling an item, see [Sell Products](sales-how-sell-products.md) or [Invoice Sales](sales-how-invoice-sales.md).

An item can be structured as a parent item with underlying child items in a bill of materials (BOM). In [!INCLUDE[d365fin](includes/d365fin_md.md)], a bill of material can be either an assembly BOM or a production BOM, depending on its use. For more information, see [Work with Bills of Material](inventory-how-work-BOMs.md).

> [!NOTE]  
>   If item templates exist for different item types, then a window appears when you create a new item card from where you can select an appropriate template. If only one item template exists, then new item cards always use that template.

If you purchase the same item from more than one vendor, you can connect those vendors to the item card. The vendors will then appear in the **Item Vendor Catalog** window, so that you can easily select an alternate vendor.

## To create a new item card
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Items**, and then choose the related link.  
2. In the **Items** window, choose the **New** action.

    If only one item template exists, then a new item card opens with some fields filled with information from the template.
3. In the **Select a template for a new item** window, choose the template that you want to use for the new item card.
4. Choose the **OK** button. A new item card opens with some fields filled with information from the template.
5. Proceed to fill or change fields on the item card as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]
> In the **Costing Method** field, you set up how the item's unit cost is calculated by making assumptions about the flow of physical items through your company. Five costing methods are available, depending on the type of item. For more information, see [Design Details: Costing Methods](design-details-costing-methods.md).
>
> If you select **Average**, then the item’s unit cost is calculated as the average unit cost at each point in time after a purchase. Inventory is valuated with the assumption that all inventories are sold simultaneously. With this setting, you can choose the **Unit Cost** field to view, in the **Average Cost Calc. Overview** window, the history of transactions that the average cost is calculated from.

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

## To set up multiple vendors for an item  
If you purchase the same item from more than one vendor, you must enter information about each vendor of the item, such as prices, lead time, discounts, and so on.  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Items**, and then choose the related link.  
2.  Select the relevant item, and then choose the **Edit** action.  
3.  Choose the **Vendors** action.  
4.  Choose the **Vendor No.** field, and then select the vendor that you want to set up for the item.  
5.  Optionally, fill in the remaining fields.  
6.  Repeat steps 2 through 5 for each vendor that you want to buy the item from.

The vendors will now appear in the **Item Vendor Catalog** window, which you open from the item card, so that you can easily select an alternate vendor.

## See Also
[Create Number Series](ui-create-number-series.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
