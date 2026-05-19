---
title: Manage product variants
description: Learn how you can record products that are almost identical but vary in color, size, or material as item variants.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: item, variant, finished good, component, raw material, assembly item, item substitution
ms.search.form: 30, 5717, 31, 32, 346, 9091, 5718, 5716, 5720, 1384, 1383, 35, 5404, 1378, 5719, 5401_Primary
ms.date: 03/04/2026
ms.service: dynamics-365-business-central
---

# Manage product variants

Item variants are a great way to keep your list of products under control. For example, you have a large number of items that are almost identical and vary only in color. You can define each variant as a separate item. But you can also choose to set up one item and specify the various colors as variants of the item.  

> [!TIP]
> For a practical introduction to using variants in production, see [Walkthrough: Variants](contoso-coffee/manufacturing/variants.md) for the Contoso Coffee demo data.  

## Add variants to an item

It's easy enough to define variants for an item.  

### To add variants

1. Open [the **Items List** page](https://businesscentral.dynamics.com/?page=31), open the relevant item.  
2. On the **Item** card, choose the **Related** action, then choose **Item**, and then choose the **Variants** action.  
3. On the **Item Variants** page, list the variants.  

Then, when you create a sales document and add the item, you can specify the variant of the item in the Variant **Code** field. The same applies to purchasing documents.  

## Add attributes to variants

You can assign attributes that are specific to a variant. Item variants inherit attributes from the item, and you can adjust or remove those inherited values when the variant requires different information.
  
You can open the **Item Variant Attribute Values** page from the **Item Variants List** or the **Item Variant Card** pages to review or edit variant-specific attributes. When you add a new variant of an item, the attributes defined for the item transfer to the variant. You can then update or delete the inherited values to ensure the variant shows the correct details. 

There's also the **Update Variant Attributes** action on the **Item Card** page that lets you to force sync attributes from the item to its variants.

## Add a picture to a variant

Adding pictures of item variants can reduce confusion when working with large assortments of similar variants. Tiles and tall tiles modes on the list can help you quickly identify each variant, which improves accuracy in the variant selection, manufacturing, fulfillment, and sales processes.

1. Open the **Item Card** and choose the **Variants** action.
1. Select the variant that you want to update.
1. On the **Item Variant Card**, in the **Picture** FactBox, choose one of the following actions: 

   - **Import** to upload a file.
   - **Take** to use your device camera to capture an image.
   - **Export** if you want to save the current image.
   - **Delete** if you don't want the picture.
   
## Item availability by variant

[!INCLUDE [inventory_variant-availability](includes/inventory_variant-availability.md)]

## Require use of variants

Administrators can require that users specify the variant in documents and journals for items that have variants. To activate the capability, on the **Inventory Setup** page, and select the **Variant Mandatory if Exists** field. You can override this global setting for specific items.  

On item cards, the **Variant Mandatory if Exists** field has the following options:

|Field value |Description|
|---------|----|
|Default (No)| The setting from **Inventory Setup** applies to this item.|
|No| Users aren't required to specify a variant for this item.|
|Yes| If the item has one or more variants, users must specify the relevant variant. If they don't, they're blocked from posting the transaction.|

> [!NOTE]
> These settings don't affect items that don't have variants.

If the capability is switched on, you can't post an entry if the variant isn't specified.

## Categories, attributes, and variants

[!INCLUDE[inventory_variant](includes/inventory_variant.md)]

## Related information

[Register New Items](inventory-how-register-new-items.md)    
[Set Up General Inventory Information](inventory-how-setup-general.md)    
[Walkthrough: Variants](contoso-coffee/manufacturing/variants.md)    
