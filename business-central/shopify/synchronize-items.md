---
title: Synchronize items and inventory
description: Set up and execute synchronizations of items between Shopify and Business Central
ms.date: 03/21/2022
ms.topic: article
ms.service: dynamics365-business-central
author: AndreiPanko
ms.author: andreipa
manager: 
---

# Synchronize items and inventory

Term **Items** in [!INCLUDE[prod_short](../includes/prod_short.md)] corresponds to products in Shopify, which includes physical goods, digital downloads, services, and gift cards that you sell.
There are two main reasons to synchronize the items:

1. Master-data management is performed in [!INCLUDE[prod_short](../includes/prod_short.md)], you need to export all or some data to Shopify and make it visible. You can export item name, description, image, prices, availability, variants, vendor details, and barcodes. Once imported, the items can become immediately visible or they can be reviewed and enhanced by a responsible person first.
2. When order from Shopify is imported, the information about items is essential for further processing of document in [!INCLUDE[prod_short](../includes/prod_short.md)].

These two scenarios are always enabled.

Another scenario is when master-data management is performed in Shopify and you want to import those items in bulk to [!INCLUDE[prod_short](../includes/prod_short.md)]. This scenario can be useful for data-migration scenarios, when an existing online shop needs to be connected to new [!INCLUDE[prod_short](../includes/prod_short.md)].

## To define item synchronizations

1. Choose the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**. Open a shop for which you want to configure item synchronization.
2. Fill in the **Sync item** field. <br>The following table outlines the difference among the options.

|Option|Description|
|------|-----------|
|**Blank**|Products are imported together with import of orders. Products are exported to Shopify if user runs **Add Item** action from the **Shopify Products** window. This is the default behavior. |
|**To Shopify**| Select this option if, after initial sync triggered by **Add Item** action, you plan to update products manually using **Sync Product** action or via job queue for recurring updates. Remember to enable **Can Update Shopify Product** field. If not enabled, it's equal to **Blank** option. |
|**From Shopify**|Select this option, if you plan to import products from Shopify in bulk; either manually using **Sync Product** action or via job queue for recurring updates. If no option is selected, it equals to **Blank** option.|

## Import items from Shopify

Either you import items from Shopify in bulk or together with import of orders, these items are added to the **Shopify Product** and **Shopify Variant** tables first. Following settings let you manage the process:

|Field|Description|
|------|-----------|
|**Auto create unknown items**|When shopify products and variants are imported to [!INCLUDE[prod_short](../includes/prod_short.md)], system always tries to find matching record in the item list first. **SKU Mapping** impacts how system performs matching and creates new item and/or item variant. For more information, see [Product Mapping](synchronize-items.md#). Enable this option if you want to create a new item or when the system couldn't find a matching record. New item will be created using imported data and **Item Template Code**. If this option isn't enabled, you'll need to create an item manually and use **Map Product** action from **Shopify Products** page.|
|**Item Template Code**|Used together with **Auto create unknown items**. <br> Choose template to be used for automatically created items.|
|**SKU Mapping**|Choose how you want to use **SKU** value imported from Shopify during item/variant mapping and creation. For more information, see [How SKU and Barcode defined in Shopify product affects mapping and creation of items and variants](synchronize-items.md#how-sku-and-barcode-defined-in-shopify-product-affects-mapping-and-creation-of-items-and-variants-in-business-central)|
|**SKU Field Separator**|Used together with **SKU Mapping** set to **Item. No + Variant Code** option.<br> Define a separator that system should use to split SKU. <br>For example: if in Shopify you create the variant with SKU '1000/001', fill '/' in the **SKU Field Separator** field to get the item number in [!INCLUDE[prod_short](../includes/prod_short.md)] as '1000' and the item variant code as '001'.
|**Variant Prefix**|Used together with **SKU Mapping** set to **Variant Code** or **Item. No + Variant Code** options as fallback strategy when SKU coming from Shopify is empty.<br>If you want system to create item variant in [!INCLUDE[prod_short](../includes/prod_short.md)], you'll need to fill in **Code**. By default, the system uses value defined in the SKU field imported from Shopify. However if SKU is empty, it will generate code starting with defined variant prefix and "001".|
|**Shopify Can Update Item**|Select if you want system automatically update items and/or variants.|

### How SKU and Barcode defined in Shopify product affects mapping and creation of items and variants in [!INCLUDE[prod_short](../includes/prod_short.md)]

When products are imported from Shopify to **Shopify Products** and **Shopify Variants** tables, system tries to find existing records. The following table outlines the difference among the options in the **SKU Mapping** field.

|Option|Effect on mapping|Effect on creation|
|------|-----------------|------------------|
|**Blank**|SKU field isn't used in item mapping routine.|No effect on creation of item. <br>Prevents creation of variants. It's useful when in sales order, only main item is used. A variant can still be mapped manually from **Shopify Product** window.|
|**Item No.**|Select if SKU field contains item no.|No effect on creation of item without variants. For item with variants, each variant is created as a separate item.<br> For example: if Shopify has a product with two variants and their SKUs are '1000' and '2000', in [!INCLUDE[prod_short](../includes/prod_short.md)] system will create two items with numbers '1000' and '2000'.|
|**Variant Code**|SKU field isn't used in item mapping routine.|No effect on creation of item. When an item variant is created, system uses value of SKU field as Code. If SKU is empty, the system generates code using **Variant Prefix** field.|
|**Item No. + Variant Code**| Select if SKU field contains item no. and item variant code separated by value defined in the **SKU Field Separator** field.|When an item is created, system uses first part of value of SKU field as **No.**. If SKU is empty, the system generates item no using number series defined in the **Item Template Code** or **Item Nos.** from the **Inventory Setup** window.<br>When an item is created, variant system uses the second part of value of SKU field as **Code**. If SKU is empty, the system generates code using **Variant Prefix** field.|
|**Vendor Item No.**| Select if SKU field contains vendor item no. Note that system won't use **Item Vendor No.** in the **Item card** window, but **Vendor Item No.** from the **Item Vendor Catalog**. If founded *Item Vendor Catalog* record contains variant code, the system will use this variant code to map Shopify variant.|If corresponding vendor exists in [!INCLUDE[prod_short](../includes/prod_short.md)], the SKU value will be used as **Vendor Item No.** in the **Item Card** and as **Item Reference** of type Vendor. <br>Prevents creation of variants. It's useful when in sales order, you want to use main item only. You still will be able to map variant manually from **Shopify Product** window.|
|**Barcode**| Select if SKU field contains barcode. System will perform search among **Item References** of type Vendor. If founded Item Reference record contains variant code, this variant code will be used by system to map Shopify variant.|No effect on creation of item. <br>Prevents creation of variants. It can be useful if in sales order, only main item is used. A variant can still be mapped manually from **Shopify Product** window.|

The following table outlines the effect of **Barcode** field.

|Effect on mapping|Effect on creation|
|-----------------|------------------|
|System performs search among **Item References** of type Barcode for value defined in the Barcode field in Shopify. If founded item reference record contains variant code, this variant code will be used by system to map Shopify variant.|Barcode is saved as **Item Reference** for item and item variant.|

> [!NOTE]
> You can trigger mapping for selected product/variants or all imported unmapped products by choosing **Try Find Product Mapping** (for selected) or **Try Find Mappings** (for all).

## Export items to Shopify

Choose the elements from your item list, which will be exported to Shopify. Use **Add Item** action from the **Shopify Products** window to add items to the Shopify products list.

Following settings let you manage the process of exporting items:

|Field|Description|
|------|-----------|
|**Customer Price Group**|Determine the price for an item in Shopify. The sales price of this customer price group is taken. If no group is entered, the price of the item card is used.|
|**Customer Discount Group**|Determine the discount to be used for  calculating price of an item in Shopify. Discounted prices are stored in the **Price** field and full price is stored in the **Compare at Price** field.|
|**Sync Item Extended Text**|Select to sync the extended text of the item. As it will be added to *Description*, it can contain HTML code. |
|**Sync Item Attributes**|Select to sync the item attributes. Attributes are formatted as table and included into *Description* field on Shopify.|
|**Language Code**|If selected, system will use translated versions for title, attributes, and extended text.|
|**SKU Mapping**|Choose how you like to populate SKU field in Shopify. Supported options are:<br> - **Item No.** to use item no for both products and variants.<br> - **Item No.+ Variant Code**  to create SKU by concatenating values of two fields. For items without variants, system uses item no only.<br>- **Item Vendor No.** to use item vendor no defined in the *Item Card* for both products and variants.<br> - **Barcode** - uses **Item Reference** of barcode type. This option respects variants. |
|**SKU Field Separator**|Define a separator for **Item. No + Variant Code** option.|
|**Inventory Tracked**|Select how system should populate *Track Inventory* field for products exported to Shopify. You can update availability information from [!INCLUDE[prod_short](../includes/prod_short.md)] for products in Shopify whose track inventory is enabled. For more information, see [Inventory](synchronize-items.md#sync-inventory-to-shopify)|
|**Default Inventory Policy**|Select *Deny* to prevent negative stock of Shopify side. |
|**Can Update Shopify Products**|Define if Business Central can only create items or can update items as well. Select this option, if after initial sync triggered by **Add Item** action, you plan to update products manually using **Sync Product** action or via job queue for recurring updates. Remember to select **To Shopify** in the **Item Sync** field.|

### Fields mapping overview

|Shopify|Source when exported from [!INCLUDE[prod_short](../includes/prod_short.md)]|Target when imported to [!INCLUDE[prod_short](../includes/prod_short.md)]|
|------|-----------------|-----------------|
|Status|According to the **Status for Created Products** in the **Shopify Shop Card**. For more information, see [Ad-hock updates of Shopify Products](synchronize-items.md#ad-hock-updates-of-shopify-products).|Not used.|
|Title|**Description**. If the language code is defined and corresponding item translation exists, item translation will be used instead of description.|**Description**|
|Description|Combines extended texts and attributes if corresponding toggles in the Shopify shop card are enabled. Respects language code.|Not used.|
|SEO page title|Fix value: empty, see [Ad-hock updates of Shopify Products](synchronize-items.md#ad-hock-updates-of-shopify-products). |Not used.|
|SEO meta description|Fix value: empty, see [Ad-hock updates of Shopify Products](synchronize-items.md#ad-hock-updates-of-shopify-products). |Not used.|
|Media|**Image**, for more information, see [Sync Item Images](synchronize-items.md#sync-item-images)|**Image**|
|Price|End-customer price is calculated with respect to item price group, item discount group, currency code, customer template code. |Not used.|
|Compare at price|Price without discount is calculated with respect to item price group, item discount group, currency code, customer template code. |Not used.|
|Cost per item|**Unit Cost**|**Unit Cost**|
|SKU|See **SKU Mapping** in the [Export items to Shopify](synchronize-items.md#export-items-to-shopify)| See [How SKU and Barcode defined in Shopify product affect mapping and creation of items and variants](synchronize-items.md#how-sku-and-barcode-defined-in-shopify-product-impact-mapping-and-creation-of-items-and-variants-in-business-central)|
|Barcode|**Item References** of barcode type|**Item References** of barcode type|
|Track quantity|According to the **Inventory Tracked** in the **Shopify Shop Card**. For more information, see [Inventory](synchronize-items.md#sync-inventory-to-shopify).|Not used.|
|Continue selling when out of stock|According to the **Default Inventory Policy** in the **Shopify Shop Card**. Not imported.|Not used.|
|Type|**Description** of **Item Category Code**. If type isn't specified on Shopify, it will be added as a custom type.|**Item Category Code**. Mapping by description.|
|Vendor|**Name** of vendor from **Vendor No.** |**Vendor No.** Mapping by name.|
|Weight|**Gross Weight**.|Not used.|
|Taxable|Fixed value: Enabled.|Not used.|
|Tax Codes|**Tax Group Code**. Only relevant for sales taxes. For more information, see [taxes](synchronize-orders.md#tax-remarks). |Not used.|

### Tags

Imported tags can be reviewed in the **Tags** factbox in the **Shopify Product**. To edit tags, choose **Tags** action in the **Shopify Product** page.
If **To Shopify** option is selected in the **Sync Item** field, assigned tags are exported to Shopify at next synchronization.

## Execute Item Synchronization

Full or partial synchronization of items can be performed in many different ways.

### Initial sync of items from [!INCLUDE[prod_short](../includes/prod_short.md)] to Shopify

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products** and choose the related link.
2. Choose the **Add Items** action.
3. Fill in the **Shop Code** field. If you open the **Shopify Product** window from the **Shop Card** window, the Shop Code will be populated automatically.
4. Define filters on items as required. For example, you can filter by item no. or item category code.
5. Select ok.

The resulting items are automatically created in Shopify with prices but images and inventory levels aren't included. The operation might take some time if a large number of items is added.

### Sync products from Shopify to [!INCLUDE[prod_short](../includes/prod_short.md)]

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop** and choose the related link.
2. Select the Shop for which you want to synchronize items to open **Shopify Shop Card** page.
3. Choose the **Sync Products** action.

Alternatively, use the **Sync Products** action on the **Shopify Products** window or search for **Sync Products** batch job.

### Ad-hock updates of Shopify Products

When the records are updated in the **Shopify Product** table, following changes are synchronized with Shopify.

Update:

* **Status** - you can choose between active, archived, or draft.
* **SEO Title**
* **SEO Description**

Deletion:
Based on the value in **Action for Removed Products** in **Shopify Shop Card**, system may update product in Shopify when record is deleted from the **Shopify Products** page.

* **Blank** - nothing will happen. If necessary, user needs to perform required action from Shopify Admin.
* **Status to Draft** - status of product in Shopify is set to Draft.
* **Status to Archived** - product is archived in Shopify.

## Sync item images

Synchronization of images can be configured for synchronized items.

**Sync Item Images**

* **Blank** - image synchronization is deactivated.
* **To Shopify** - pictures of items are exported to Shopify
* **From Shopify** - images from Shopify are imported to [!INCLUDE[prod_short](../includes/prod_short.md)]

Image synchronization can be initialized in two ways.

### Sync product images from the Shopify shop window

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops** and choose the related link.
2. Select the Shop for which you want to synchronize images to open **Shopify Shop Card** page.
3. Choose the **Sync Product Images** action.

### Sync product images from the Shopify products window

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products** and choose the related link.
2. Choose the **Sync Product Images** action.

### Image synchronization remarks

* When exporting images from [!INCLUDE[prod_short](../includes/prod_short.md)] to Shopify, the new images are added to Shopify, keeping old images intact. If an image is updated in [!INCLUDE[prod_short](../includes/prod_short.md)], you'll need to delete old images in Shopify Admin.
* Images that are exported to Shopify and don't comply with requirements defined by Shopify, won't be imported. For more information, see [Product Media Types on help.shopify.com](https://help.shopify.com/en/manual/products/product-media/product-media-types#images)

## Sync prices with Shopify

Prices can be exported for synchronized items in following ways:

### Sync prices from the Shopify products window

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products** and choose the related link.
2. Choose the **Sync Prices to Shopify** action.

### Price calculation remarks

* For price calculation, it's important to have the **Default Customer Template** field filled in.
* Remember to fill in **Currency Code** if your online shop uses different currency than LCY.
* When determining price, system uses "Lowest price" logic. It means if unit price defined in the item card is lower than what is defined in the price group, unit price from item card is used.

## Sync Inventory to Shopify

Inventory synchronization can be configured for already synchronized items. There are two conditions that must be met:

1. Inventory tracking must be enabled for product in Shopify. If items are exported to Shopify, consider enabling **Inventory Tracked** toggle in the **Shopify Shop** card. For more information, see [Export items to Shopify](synchronize-items.md#export-items-to-shopify).
2. Inventory synch must be enabled for **Shopify Locations**

### To enable inventory sync

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop** and choose the related link.
2. Select the Shop for which you want to synchronize inventory to open **Shopify Shop Card** page.
3. Choose the **Locations** action to open **Shopify Shop Locations**
4. Choose the **Get Shopify Locations** action to import all locations defined in the Shopify. You can find them in the [**Locations**](https://www.shopify.com/admin/settings/locations) settings in your **Shopify admin**.
5. Fill in the **Location Filter** if you want to include inventory from specific locations only. For example, you can enter *EAST|WEST*, so that inventory from these two locations only is available for sales via online shop.
6. Remove toggle from the **Disabled** field to enable inventory sync for selected Shopify locations

You can initialize inventory synchronization in two ways.

### Sync inventory from the Shopify shop window

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops** and choose the related link.
2. Select the Shop for which you want to synchronize inventory to open **Shopify Shop Card** page.
3. Choose the **Sync inventory** action.

### Sync inventory from the Shopify products window

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products** and choose the related link.
2. Choose the **Sync inventory** action.

### Inventory remarks

* System calculates the **Projected Available Balance** and export it to Shopify.
* You can inspect the stock information received from Shopify in the **Shopify Inventory Factbox** page. In this factbox, you get an overview of the Shopify Stock and the last calculated inventory in Business Central. There's a record per location.
* If Stock information in Shopify is different from **Projected Available Balance** in [!INCLUDE[prod_short](../includes/prod_short.md)], then Stock will be updated in Shopify.
