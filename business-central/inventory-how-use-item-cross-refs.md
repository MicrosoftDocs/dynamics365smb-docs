---
title: Use item references
description: Set up references between the descriptions, unit of measures, and variants that you and your vendor or customer use for an item.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: item reference, cross reference, inventory
ms.search.forms: 5737, 5735, 5736
ms.date: 05/16/2024
ms.custom: bap-template
ms.service: dynamics-365-business-central
---
# Use item references

If you buy or sell items that you and your vendor or customer use different terms for, then you can set up a reference between your terms for the items and the terms that the customer or vendor of that item uses. This way, the vendor's or customer's item description, unit of measure, or variant code is automatically inserted on the relevant documents when you fill in the **Item Reference No.** field.  

## To set up an item reference

1. Choose the :::image type="icon" source="media/ui-search/search_small.png" border="false"::: icon, enter **Items**, and then choose the related link.
2. Open the card for an item for which you want to create a reference.
3. Choose the **Item References** action.

     If you can't find the **Item References** action, choose to view more options, and then find it under **Related** > **Item**.
  
4. On a new line on the **Item Reference Entries** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].

The following procedure describes how you specify the item reference on a purchase order. Similar steps apply to sales documents and other purchase documents.  

## To enter a vendor's item description on a document

1. Choose the :::image type="icon" source="media/ui-search/search_small.png" border="false"::: icon, enter **Purchase Orders**, and then choose the related link.
2. Create a purchase order for the vendor that you set up an item reference for in the previous procedure.
3. Create a purchase line for the item that you set up an item reference for in the previous procedure.
4. In the item reference **No.** field, select the relevant item reference, and then choose the **OK** button.

The **Description** field on the line is overwritten with the vendor's item description, as set up on the item reference entry. If the item reference includes a variant code or a unit of measure, these values are also copied to the document.  

## Scan barcodes with the Business Central mobile app

[!INCLUDE [barcode-mobile-app](includes/barcode-mobile-app.md)]

The following table lists the pages that support barcode scanning of item references from the [!INCLUDE [prod_short](includes/prod_short.md)] mobile app.

|Page  |Field value you can scan  |
|---------|---------|
|Item Reference     | Reference No.        |
|Item Journal Line     | Item Reference No.        |
|Phys. Invt. Order Line     |Item Reference No.         |
|Purchase Line     |   Item Reference No.      |
|Sales Line     | Item Reference No.        |

## Related information

[Register New Items](inventory-how-register-new-items.md)  
[Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
