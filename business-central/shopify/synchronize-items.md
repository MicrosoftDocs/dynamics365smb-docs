---
title: Synchronize items and inventory
description: Setup and execute synchronizations of items between Shopify and Business Central
ms.date: 03/21/2022
ms.topic: article
ms.service: dynamics365-business-central
author: AndreiPanko
ms.author: andreipa
manager: 
---

# Synchronize items and inventory

Term **Items** in [!INCLUDE[prod_short](../includes/prod_short.md)] corresponds to *Products in Shopify* which includes physical goods, digital downloads, services and gift cards that you sell.
There are two main reasons to synchronize the items:

1. Master-data management is performed in [!INCLUDE[prod_short](../includes/prod_short.md)], you need to export all or some data to Shopify and make it visible. You can export item name, description, image, prices, availability, variants, vendor details, barcodes, which can become immediately visible or first reviewed and enhanced by a responsible person.
2. When importing order from Shopify, the information about items are essential for further processing of document in [!INCLUDE[prod_short](../includes/prod_short.md)].

These two scenarios are always enabled.

3. Additional scenario is when master-data management is performed in Shopify and you want to import those items in bulk to [!INCLUDE[prod_short](../includes/prod_short.md)]. This can be useful for data-migration scenarios, when existing online shop connected to new [!INCLUDE[prod_short](../includes/prod_short.md)].

## To define item synchronizations

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**. Open a shop for which you want to configure item synchronization.
2. Fill in the **Sync item**, the following table outlines the difference between the options.

|Option|Description|
|------|-----------|
|**Blank**|Products will be imported together with import of orders. Products will be exported to Shopify if user runs **Add Item** action from the **Shopify Products** window. This is default behavior. |
|**To Shopify**| Select if after initial sync triggered by **Add Item** action, you plan to update products manually using **Sync Product** action or via job queue for recurring updates. Remember to enable **Can Update Shopify Product** field. Other than that it equals to **Blank** option. |
|**From Shopify**|Select if you plan import products from Shopify in bulk either manually using **Sync Product** action or via job queue for recurring updates. Other than that it equals to **Blank** option.|

## Import items from Shopify

Either you import items from Shopify in bulk or together with import of orders, these items first will be added to the **Shopify Product** and **Shopify Variant** tables. Following settings let you manage the process:

|Field|Description|
|------|-----------|
|**Auto create unknown items**|When shopify products and variants are imported to [!INCLUDE[prod_short](../includes/prod_short.md)], system always tries to find matching record in the item list first. **SKU Mapping** impacts how system performs matching and creates new Item and/or Item Variant. For more information, see [Product Mapping](synchronize-items.md#). Enable this option if you want to create new item and/or for records where system didn't find the matching record. New item will be created using imported data and **Item Template Code**. If this option is disabled, you will need to create Item manually and use **Map Product** action from **Shopify Products** page.|
|**Item Template Code**|Used together with **Auto create unknown items**. <br> Choose template to be used for automatically created items.|
|**SKU Mapping**|Choose how you want to use **SKU** value imported from Shopify during item/variant mapping and creation. For more information, see [How SKU and Barcode defined in Shopify product impact mapping and creation of items and variants](synchronize-items.md#how-sku-and-barcode-defined-in-shopify-product-impact-mapping-and-creation-of-items-and-variants-in-business-central)|
|**SKU Field Separator**|Used together with **SKU Mapping** set to **Item. No + Variant Code** option.<br> Define a separator that system should use to split SKU. <br>For example: if in Shopify you create the variant with SKU '1000/001', fill '/' in the **SKU Field Separator** field to get the item number in [!INCLUDE[prod_short](../includes/prod_short.md)] as '1000' and the item variant code as '001'.
|**Variant Prefix**|Used together with **SKU Mapping** set to **Variant Code** or **Item. No + Variant Code** options as fallback strategy when SKU coming from Shopify is empty.<br>If you want system to create Item Variant in [!INCLUDE[prod_short](../includes/prod_short.md)], you will need to fill in **Code**. By default system will use value defined in the SKU field imported from Shopify. However if SKU is empty, it will generate code starting with defined variant prefix and "001".|
|**Shopify Can Update Item**|Select if you want system automatically update items and/or variants.|

### How SKU and Barcode defined in Shopify product impact mapping and creation of items and variants in [!INCLUDE[prod_short](../includes/prod_short.md)]

When products are imported from Shopify to **Shopify Products** and **Shopify Variants** tables, system tries to find existing records. The following table outlines the difference between the options in the **SKU Mapping** field.

|Option|Impact on mapping|Impact on creation|
|------|-----------------|------------------|
|**Blank**|SKU field is not used in item mapping routine.|No impact on creation of item. <br>Prevents creation of variants. This can be useful if you want to use in sales order only main item. You still will be able to map variant manually from **Shopify Product** window.|
|**Item No.**|Select if SKU field contains item no.|No impact on creation of item without variants. For item with variants, each variant will be created as separate item.<br> For example: if in Shopify you have product with two variants with SKUs '1000' and '2000', in [!INCLUDE[prod_short](../includes/prod_short.md)] system will create two items with numbers '1000' and '2000'.|
|**Variant Code**|SKU field is not used in item mapping routine.|No impact on creation of item. When creating item variant system will use value of SKU field as Code. If SKU is empty, then system will generate code using **Variant Prefix** field.|
|**Item No. + Variant Code**| Select if SKU field contains item no. and item variant code separated by value defined in the **SKU Field Separator** field.|When creating item system will use first part of value of SKU field as **No.**. If SKU is empty, then system will generate item no using Number series defined in the **Item Template Code** or **Item Nos.** from the **Inventory Setup** window.<br>When creating item variant system will use the second part of value of SKU field as **Code**. If SKU is empty, then system will generate code using **Variant Prefix** field.|
|**Vendor Item No.**| Select if SKU field contains vendor item no. Note that system will not use **Item Vendor No.** in the **Item card** window, but **Vendor Item No.** from the **Item Vendor Catalog**. If founded Item Vendor Catalog record contains variant code, this variant code will be used by system to map Shopify variant.|If corresponding vendor exists in [!INCLUDE[prod_short](../includes/prod_short.md)] the SKU value will be used as **Vendor Item No.** in the **Item Card** and as **Item Reference** of type Vendor. <br>Prevents creation of variants. This can be useful if you want to use in sales order only main item. You still will be able to map variant manually from **Shopify Product** window.|
|**Barcode**| Select if SKU field contains barcode. System will perform search among **Item References** of type Vendor. If founded Item Reference record contains variant code, this variant code will be used by system to map Shopify variant.|No impact on creation of item. <br>Prevents creation of variants. This can be useful if you want to use in sales order only main item. You still will be able to map variant manually from **Shopify Product** window.|

The following table outlines the impact of **Barcode** field.

|Impact on mapping|Impact on creation|
|-----------------|------------------|
|System will perform search among **Item References** of type Barcode for value defined in the Barcode field in Shopify. If founded Item Reference record contains variant code, this variant code will be used by system to map Shopify variant.|Barcode is saved as **Item Reference** for item and/or item variant.|

> [!NOTE]
> You can trigger mapping for selected product/variants or all imported not mapped products by choosing **Try Find Product Mapping** (for selected) or **Try Find Mappings** (for all).

## Export items to Shopify

First you need to choose which elements of your item list will be exported to Shopify. Use **Add Item** action from the **Shopify Products** window to add items to the Shopify products list.

Following settings let you manage the process of exporting items:

|Field|Description|
|------|-----------|
|**Customer Price Group**|Determine which price should be used for an item in Shopify. The sales price of this customer price group is taken. If no group is entered, the price of the item card is used.|
|**Customer Discount Group**|Determine which discount should be used when calculation price for an item in Shopify. Discounted prices will be stored in the **Price** field, full price in the **Compare at Price** field.|
|**Sync Item Extended Text**|Select if you want to sync the extended text of the item. Because it will be added to Description, it can contain HTML code. |
|**Sync Item Attributes**|Select if you want to sync the item attributes of the item. Attributes will be formatted as table and included into Description field on Shopify.|
|**Language Code**|If selected system will use translated versions when for Title, Attributes and Extended text.|
|**SKU Mapping**|Choose how you want to populate SKU field in Shopify. Supported options are:<br> - **Item No.** to use Item No for both products and variants.<br> - **Item No.+ Variant Code**  to create SKU by concatenating values of two fields. For items without variants system will use only Item No.<br>- **Item Vendor No.** to use Item Vendor No defined in the Item Card for both products and variants.<br> - **Barcode** - uses **Item Reference** of type Barcode. This option respects variants. |
|**SKU Field Separator**|Define a separator for **Item. No + Variant Code** option.|
|**Inventory Tracked**|Select how system should populate Track Inventory field for products exported to Shopify. For products in Shopify, where Track Inventory is enabled you can update availability information from [!INCLUDE[prod_short](../includes/prod_short.md)]. For more information, see [Inventory](synchronize-items.md#sync-inventory-to-shopify)|
|**Default Inventory Policy**|Select Deny to prevent negative stock of Shopify side. |
|**Can Update Shopify Products**|Define if Business Central can only create items or also update items. Select if after initial sync triggered by **Add Item** action, you plan to update products manually using **Sync Product** action or via job queue for recurring updates. Remember to select **To Shopify** in the **Item Sync** field.|

### Fields mapping overview

|Shopify|Source when exported from [!INCLUDE[prod_short](../includes/prod_short.md)]|Target when imported to [!INCLUDE[prod_short](../includes/prod_short.md)]|
|------|-----------------|-----------------|
|Status|Accordingly to the **Status for Created Products** in the **Shopify Shop Card**. For more information, see [Ad-hock updates of Shopify Products](synchronize-items.md#ad-hock-updates-of-shopify-products).|Not used.|
|Title|**Description**. If Language Code defined and corresponding Item Translation exists, item translation will be used instead of Description.|**Description**|
|Description|Combines extended texts and attributes, if corresponding toggles in the Shopify Shop Card are enabled. Respects Language Code.|Not used.|
|SEO Page Title|Fix value: empty, see [Ad-hock updates of Shopify Products](synchronize-items.md#ad-hock-updates-of-shopify-products). |Not used.|
|SEO Meta description|Fix value: empty, see [Ad-hock updates of Shopify Products](synchronize-items.md#ad-hock-updates-of-shopify-products). |Not used.|
|Media|**Image**, for more information, see [Sync Item Images](synchronize-items.md#sync-item-images)|**Image**|
|Price|End-customer price calculated with respect of Item Price Group, Item Discount Group, Currency Code, Customer Template Code. |Not used.|
|Compare at price|Price without discount calculated with respect of Item Price Group, Item Discount Group, Currency Code, Customer Template Code. |Not used.|
|Cost per item|**Unit Cost**|**Unit Cost**|
|SKU|See **SKU Mapping** in the [Export items to Shopify](synchronize-items.md#export-items-to-shopify)| See [How SKU and Barcode defined in Shopify product impact mapping and creation of items and variants](synchronize-items.md#how-sku-and-barcode-defined-in-shopify-product-impact-mapping-and-creation-of-items-and-variants-in-business-central)|
|Barcode|**Item References** of type Barcode|**Item References** of type Barcode|
|Track quantity|Accordingly to the **Inventory Tracked** in the **Shopify Shop Card**. For more information, see [Inventory](synchronize-items.md#sync-inventory-to-shopify).|Not used.|
|Continue selling when out of stock|Accordingly to the **Default Inventory Policy** in the **Shopify Shop Card**. Not imported.|Not used.|
|Type|**Description** of **Item Category Code**. If Type doesn't exists on Shopify, it will be added as Custom Type.|**Item Category Code**. Mapping by Description.|
|Vendor|**Name** of vendor from **Vendor No.** |**Vendor No.** Mapping by Name.|
|Weight|**Gross Weight**.|Not used.|
|Taxable|Fixed value: Enabled.|Not used.|
|Tax Codes|**Tax Group Code**. Only relevant for sales taxes. For more information, see [taxes](synchronize-orders.md#tax-remarks). |Not used.|

### Tags

Imported tags can be reviewed in the **Tags** factbox in the **Shopify Product**. To edit tags, choose **Tags** action in the **Shopify Product** page.
If **To Shopify** options is selected in the **Sync Item** field, assigned tags will be exported to Shopify at next synchronization.

## Execute Item Synchronization

There are numbers of possibilities to perform full or partial synchronization of items.

### Initial sync of items from [!INCLUDE[prod_short](../includes/prod_short.md)] to Shopify

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and then choose the related link.
2. Choose the **Add Items** action.
3. Fill in the **Shop Code** field. If you open the **Shopify Product** window from the **Shop Card** window, the Shop Code will be populated automatically.
4. Define filters on items as necessary. For example you can filter by item no. or item category code.
5. Click ok.

In result items are automatically created in Shopify with prices, but without images and inventory levels. The operation might take some time if you are adding large number of items.

### Sync of products from Shopify to [!INCLUDE[prod_short](../includes/prod_short.md)]

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and then choose the related link.
2. Select the Shop for which you want to synchronize items to open **Shopify Shop Card** page.
3. Choose the **Sync Products** action.

Alternatively you can use the **Sync Products** action on the **Shopify Products** window or search for **Sync Products** batch job.

### Ad-hock updates of Shopify Products

When user updates records in the **Shopify Product** table following changes will be synchronized with Shopify.

Update:

* **Status** - you can choose between active, archived, or draft.
* **SEO Title**
* **SEO Description**

Deletion:
Based on value in the **Action for Removed Products** in **Shopify Shop Card**, system may update product in Shopify when record is deleted from the **Shopify Products** page.

* **Blank** - nothing will happen, if necessary user needs to perform needed action from Shopify Admin.
* **Status to Draft** - status of product in Shopify will be set to Draft.
* **Status to Archived** - product will be archived in Shopify.

## Sync item images

For already synchronized items you can also configure synchronization of images.

**Sync Item Images**

* **Blank** - synchronization of images is disabled
* **To Shopify** - picture of Items are exported to Shopify
* **From Shopify** - images from Shopify are imported to [!INCLUDE[prod_short](../includes/prod_short.md)]

You can initialize synchronization of images in two ways.

### Sync product images from the Shopify Shop window

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and then choose the related link.
2. Select the Shop for which you want to synchronize images to open **Shopify Shop Card** page.
3. Choose the **Sync Product Images** action.

### Sync product images from the Shopify Products window

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and then choose the related link.
2. Choose the **Sync Product Images** action.

### Image synchronization remarks

* When exporting images from [!INCLUDE[prod_short](../includes/prod_short.md)] to Shopify the new images will be added to Shopify, keeping old images intact. So if you updated image in [!INCLUDE[prod_short](../includes/prod_short.md)], you will need to delete old ones in Shopify Admin.
* Images exported to Shopify that doesn't comply with requirements defined by Shopify, will not be imported. For more information, see [Product Media Types on help.shopify.com](https://help.shopify.com/en/manual/products/product-media/product-media-types#images)

## Sync prices to Shopify

For synchronized items you can export prices:

### Sync prices from the Shopify Products window

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and then choose the related link.
2. Choose the **Sync Prices to Shopify** action.

### Price calculation remarks

* For price calculation it is important to have the **Default Customer Template** field filled in.
* Remember to fill in **Currency Code** if your online shop uses different currency than LCY.
* When determining price system uses "Lowest price" logic. Means if Unit Price defined in the Item Card is lower to what is defined in the price group, Unit Price from Item Card will be used.

## Sync Inventory to Shopify

For already synchronized items you can also configure synchronization of inventory. There are two conditions that must be met:

1. Inventory Tracking must be enabled for product in Shopify. If items are exported to Shopify, consider enabling **Inventory Tracked** toggle in the **Shopify Shop** card. For more information, see [Export items to Shopify](synchronize-items.md#export-items-to-shopify).
2. Inventory synch must be enabled for **Shopify Locations**

### To enable inventory sync

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and then choose the related link.
2. Select the Shop for which you want to synchronize inventory to open **Shopify Shop Card** page.
3. Choose the **Locations** action to open **Shopify Shop Locations**
4. Choose the **Get Shopify Locations** action to import all locations defined in the Shopify. You can find them in the [**Locations**](https://www.shopify.com/admin/settings/locations) settings in your **Shopify admin**.
5. Fill in the **Location Filter** if you want to include inventory only from some locations. For example you can enter *EAST|WEST*, so only inventory from these two locations will be available for sales via online shop.
6. Remove toggle from the **Disabled** field to enable inventory sync for selected Shopify locations

You can initialize synchronization of inventory in two ways.

### Sync inventory from the Shopify Shop window

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and then choose the related link.
2. Select the Shop for which you want to synchronize images to open **Shopify Shop Card** page.
3. Choose the **Sync inventory** action.

### Sync inventory from the Shopify Products window

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and then choose the related link.
2. Choose the **Sync inventory** action.

### Inventory remarks

* System calculates the **Projected Available Balance** and export it to Shopify
* You can inspect the Stock information received from Shopify is in the **Shopify Inventory Factbox** page. In this factbox you get an overview of the Shopify Stock and the last calculated inventory in Business Central. There is a record per location.
* If Stock information in Shopify is different from **Projected Available Balance** in [!INCLUDE[prod_short](../includes/prod_short.md)], then Stock will be updated in Shopify.
