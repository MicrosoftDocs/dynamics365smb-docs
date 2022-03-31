---
title: Use Item References
description: Set up references between the descriptions, unit of measures, and variants that you and your vendor or customer use for an item.
author: brentholtorf

ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: item reference, cross reference, inventory
ms.search.forms: 5737, 5735, 5736
ms.date: 10/27/2021
ms.author: edupont

---
# Use Item References

If you buy or sell items that you and your vendor or customer use different terms for, then you can set up a reference between your terms for the items and the terms that the customer or vendor of that item uses. This way, the vendor's or customer's item description, unit of measure, or variant code is automatically inserted on the relevant documents when you fill in the **Item Reference No.** field.  

> [!NOTE]
> [!INCLUDE [2021_releasewave2](includes/2021_releasewave2.md)]
>
> Not all companies use item references. To minimize clutter on pages, we've hidden the related fields and actions by default. If you decide to use them, select the **Use Item References** field on the **Inventory Setup** page. After you turn on item references, the fields and actions are available on the Item Card, Vendor Card, and Customer Card pages, and from sales and purchase documents.
>
> In versions earlier than 2021 release wave 2, your administrator can turn on the *Write longer item references* feature in the [Feature Management](https://businesscentral.dynamics.com/?page=2610) page (link requires that you have a [!INCLUDE [prod_short](includes/prod_short.md)] tenant). How you use references doesn't change, but the names of things like pages and buttons will. For example, the **Item Cross-Reference Entries** page will become the **Item Reference Entries** page.

## To start using item references

[!INCLUDE [2021_releasewave2](includes/2021_releasewave2.md)]

1. Choose the :::image type="icon" source="media/ui-search/search_small.png" border="false"::: icon, enter **Inventory Setup**, and then choose the related link.
2. Select the **Use Item References** field.

## To set up an item reference

1. Choose the :::image type="icon" source="media/ui-search/search_small.png" border="false"::: icon, enter **Items**, and then choose the related link.
2. Open the card for an item for which you want to create a reference.
3. Choose the **Item References** action.

     If you cannot find the **Item References** action, choose to view more options, and then find it under **Related** > **Item**.
  
4. On a new line on the **Item Reference Entries** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].

The following procedure describes how you specify the item reference on a purchase order. Similar steps apply to sales documents and other purchase documents.  

## To enter a vendor's item description on a document

1. Choose the :::image type="icon" source="media/ui-search/search_small.png" border="false"::: icon, enter **Purchase Orders**, and then choose the related link.
2. Create a purchase order for the vendor that you set up an item reference for in the previous procedure.
3. Create a purchase line for the item that you set up an item reference for in the previous procedure.
4. In the **Item Reference No.** field, select the relevant item reference, and then choose the **OK** button.

The **Description** field on the line is overwritten with the vendor's item description, as set up on the item reference entry. If the item reference includes a variant code or a unit of measure, these values are also copied to the document.  

## See Also

[Register New Items](inventory-how-register-new-items.md)  
[Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]