---
title: Create and Manage Catalog Items| Microsoft Docs
description: Describes how to trade in items that are in your vendors list of items but not in your own list of items.
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: non-inventoriable
ms.date: 04/01/2020
ms.author: sgroespe

---
# Work with Catalog Items
You can offer certain items to your customers for their convenience, which you do not want to manage in your system until you start selling them. When you want to start managing such items in your system, you can convert them to normal item cards in two ways.

* From a catalog item card, create a new item card based on a template.
* From a sales order line of type **Item** with an empty **No** field, select a catalog item. An item card is then automatically created for the catalog item.

> [!NOTE]  
> You cannot select a catalog item from the **Sales Invoice** page.<br /><br />
> You can select a catalog item from the **Sales Quote** page, but the catalog item will not be converted to a normal item when you use the **Make Order** function.

A catalog item typically has the item number of the vendor who supplies it. To enable conversion of a catalog item card to a normal item card, you must first set up how vendor item numbering is converted to your own item numbering.   

> [!Important]
> Catalog items are not to be mistaken with non-inventory items, which are regular items that are given the type **Non-Inventory** to keep them out of availability and costing calculations, for example, because they are only used internally and have a low cost. For more information, see [About Item Types](inventory-about-item-types.md).

## To create a catalog item
Catalog item cards have much less information than normal item cards because you only use them to offer on quotes and in other ways. For that reason, they must be converted to normal item cards before you can post sales transactions for them.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Catalog Items**, and then choose the related link.
2. Choose the **New** action.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To set up how catalog item numbers are converted to your own numbering
To enable conversion of a catalog item card to a normal item card, you must first set up how the vendor's item numbering is converted to your own item number format.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Catalog Item Setup**, and then choose the related link.
2. Fill in the fields as necessary.

## To convert a catalog item to a normal item
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Catalog Items**, and then choose the related link.
2. Open the card for a catalog item that you want to convert to a normal item.
3. On the **Catalog Item Card** page, choose the **Create Item** action.

A new item card prefilled with information from the catalog item and a relevant item template is created. You can then fill or edit fields on the new item card as necessary. For more information, see [Register New Items](inventory-how-register-new-items.md).

## To sell a catalog item, and convert it to a normal item
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.
2. Choose the **New** action. Fill in the fields on the **General** FastTab as for any sales order. For more information, see [Sell Products](sales-how-sell-products.md).
3. On a new sales line, in the **Type** field, select **Item**, but leave the **No.** field empty.
4. Choose the **Line** action, and then choose the **Select Catalog Items** action.

    The catalog item is converted to a normal item. A new item card prefilled with information from the catalog item and a relevant item template is created.
5. On the **Catalog Items** page, select the catalog item that you want to sell, and then choose the **OK** button.
6. When the sales order is complete, choose the **Post** action.

You can then fill or edit fields on the new item card as necessary. For more information, see [Register New Items](inventory-how-register-new-items.md).

> [!NOTE]  
>   An Item cross reference record is automatically created for the vendor of the item between the vendor's item number and your new item number. For more information, see [Use Item Cross References](inventory-how-use-item-cross-refs.md).

## See Also
[Register New Items](inventory-how-register-new-items.md)  
[Create Special Orders](sales-how-to-create-special-orders.md)|  
[Inventory](inventory-manage-inventory.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
