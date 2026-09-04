---
title: Manage product variants
description: Learn how you can record products that are almost identical but vary in color, size, or material as item variants.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: item, variant, finished good, component, raw material, assembly item, item substitution, item reference, item translation, stockkeeping unit, SKU
ms.search.form: 30, 5717, 31, 32, 346, 9091, 5718, 5716, 5720, 1384, 1383, 35, 5404, 1378, 5719, 5401_Primary
ms.date: 09/04/2026
ms.service: dynamics-365-business-central
---

# Manage product variants

Many businesses sell products that come in multiple sizes, colors, materials, or configurations. A single product design can quickly expand into dozens or even hundreds of sellable combinations. Without structure, inventory becomes harder to track, purchasing gets fragmented, and reporting loses clarity.

Use item variants to manage all variations of a product under a single item record instead of creating separate items for each combination. You get consolidated reporting while still tracking inventory, pricing, and availability at the variant level - whether you sell three T-shirt sizes or two hundred fabric-color combinations.

> [!TIP]
> To learn more about using variants in production, go to [Walkthrough: Variants](contoso-coffee/manufacturing/variants.md) for the Contoso Coffee demo data.  

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

## Item references per variant

When your vendors or customers use their own item numbers, set up item references that map their codes to yours, including at the variant level. For example, if a customer orders **BLU-LG-POLO** and you track it as item 1200, variant **BLUE-L**, the item reference automatically bridges that gap on sales and purchase documents.

Item references can also carry variant-specific units of measure. If a vendor ships a particular variant in cases of 24 rather than individual pieces, the correct unit populates automatically.

Learn more at [Use Item References](inventory-how-use-item-cross-refs.md).

## Item translations

If you sell or purchase in markets that use different languages, store translated descriptions for each item and variant combination. When you create a document for a customer or vendor with a different language code, [!INCLUDE [prod_short](includes/prod_short.md)] automatically substitutes the translated description on document lines.

To set up translations:

1. Open the **Item Card** and choose the **Translations** action.
1. On the **Item Translations** page, specify the **Language Code** and the translated **Description** and **Description 2** fields.
1. To set a translation for a specific variant, fill in the **Variant Code** field.

When you add the item to a document where the customer or vendor has a different language, the description pulls from the matching translation entry. If a variant-specific translation exists, it takes priority over the item-level translation.

## Stockkeeping units for replenishment and planning

When you manage the same item across multiple locations or need location-specific planning parameters for specific variants, set up stockkeeping units (SKUs). A SKU links an item, a location, and optionally a variant code into a planning identity that the supply planning system treats independently.

This system means you can define different replenishment methods, lead times, reorder points, safety stock levels, and even different vendors or production BOMs depending on where and how you stock a variant. For example:

- Variant BLUE is purchased from a local supplier at the East warehouse with a two-day lead time, but produced in-house at the West plant with a five-day manufacturing lead time.
- The reorder point for size Large is higher than for size Small because Large sells faster at a specific location.

Without SKUs, the planning system uses the same replenishment parameters for an item everywhere. With SKUs, requisition worksheets and planning worksheets generate separate supply proposals per location-variant combination.

Learn more at [Set Up Stockkeeping Units](inventory-how-to-set-up-stockkeeping-units.md).

## Categories, attributes, and variants

[!INCLUDE[inventory_variant](includes/inventory_variant.md)]

## Related information

[Register New Items](inventory-how-register-new-items.md)  
[Use Item References](inventory-how-use-item-cross-refs.md)  
[Set Up Stockkeeping Units](inventory-how-to-set-up-stockkeeping-units.md)  
[Set Up General Inventory Information](inventory-how-setup-general.md)  
[Walkthrough: Variants](contoso-coffee/manufacturing/variants.md)  
