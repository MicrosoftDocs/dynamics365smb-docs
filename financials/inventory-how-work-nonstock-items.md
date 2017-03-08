---
title: 'How to: Work with Nonstock Items| Microsoft Docs'
description: Describes how to trade items that are not maintained in inventory
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: project-madeira
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/09/2017
ms.author: sgroespe

---
# How to: Work with Nonstock Items
You can offer certain items to your customers for their convenience, which you do not want to maintain in inventory until you start selling them. When you want to start maintaining such items in inventory, you can convert them to normal item cards in two ways.

* From a nonstock item card, create a new item card based on a template.
* From a sales order line of type **Item** with an empty **No* field, select a nonstock item. An item card is automatically created for the nonstock item.

**Note**: You cannot select a nonstock item from the **Sales Invoice** window. You can select a nonstock item from the **Sales Quote** window, but the nonstock item will not be converted to a normal item when you use the **Make Order** function.

A nonstock item typically has the item number of the vendor who supplies it. To enable conversion of a nonstock item card to a normal item card, you must first set up how vendor item numbering is converted to your own item numbering.   

## To create a nonstock item
Nonstock item cards have much less information than normal item cards because you only use them to offer on quotes and in other ways. For that reason, they must be converted to normal item cards before you can post sales transactions for them.

1. In the top right corner, choose the **Search for Page or Report** icon, enter **Nonstock Items**, and then choose the related link.
2. Choose the **New** action.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To set up how nonstock item numbers are converted to your own numbering
To enable conversion of a nonstock item card to a normal item card, you must first set up how the vendor's item numbering is converted to your own item number format.

1. In the top right corner, choose the **Search for Page or Report** icon, enter **Nonstock Item Setup**, and then choose the related link.
2. Fill in the fields as necessary.

## To convert a nonstock item to a normal item
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Nonstock Items**, and then choose the related link.
2. Open the card for a nonstock item that you want to convert to a normal item.
3. In the **Nonstock Item Card** window, choose the **Create Item** action.

A new item card prefilled with information from the nonstock item and a relevant item template is created. You can then fill or edit fields on the new item card as necessary. For more information, see [How to: Register New Items](inventory-how-register-new-items.md).

## To sell a nonstock item, and convert it to a normal item
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Sales Orders**, and then choose the related link.
2. Choose the **New** action. Fill in the fields on the **General** FastTab as for any sales order. For more information, see [How to: Sell Products](sales-how-sell-products.md).
3. On a new sales line, in the **Type** field, select **Item**, but leave the **No** field empty.
4. Choose the **Line** action, and then choose the **Select Nonstock Items** action.

    The nonstock item is converted to a normal item. A new item card prefilled with information from the nonstock item and a relevant item template is created.
5. In the **Nonstock Items** window, select the nonstock item that you want to sell, and then choose the **OK** button.
6. When the sales order is complete, choose the **Post** action.

You can then fill or edit fields on the new item card as necessary. For more information, see [How to: Register New Items](inventory-how-register-new-items.md).

**Note**: An Item cross reference record is automatically created for the vendor of the item between the vendor's item number and your new item number.

## See Also
[How to: Register New Items](inventory-how-register-new-items.md)  
[Inventory](inventory-manage-inventory.md)  
[Working With [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
