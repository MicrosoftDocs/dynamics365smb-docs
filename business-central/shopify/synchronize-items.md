---
title: Synchronize items and inventory
description: Set up and run synchronizations of items between Shopify and Business Central
ms.date: 05/27/2022
ms.topic: article
ms.service: dynamics365-business-central
author: AndreiPanko
ms.author: andreipa
ms.reviewer: solsen
---

# Synchronize Items and Inventory

The **Items** in [!INCLUDE[prod_short](../includes/prod_short.md)] are equivalent to the *products* in Shopify, which includes physical goods, digital downloads, services, and gift cards that you sell. There are two main reasons to synchronize the items:

1. Primarily, the data management is performed in [!INCLUDE[prod_short](../includes/prod_short.md)], you need to export all or some data to Shopify and make it visible. You can export item name, description, image, prices, availability, variants, vendor details, and barcode. Once imported, the items can become immediately visible or they can be reviewed and enhanced by a responsible person first.
2. When an order from Shopify is imported, the information about items is essential for further processing of document in [!INCLUDE[prod_short](../includes/prod_short.md)].

These two scenarios are always enabled.

A third scenario is to manage data in Shopify but import those items in bulk to [!INCLUDE[prod_short](../includes/prod_short.md)]. This scenario can be useful for data migration events, when you want to connect an existing online shop with a new [!INCLUDE[prod_short](../includes/prod_short.md)] environment.

## To define item synchronizations

1. Choose the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**. Open a shop for which you want to configure item synchronization.
2. From the **Sync item** field, select the required option. <br>The following table outlines the difference among the options.

|Option|Description|
|------|-----------|
|**Blank**| Products are imported together with import of orders. Products are exported to Shopify if a user runs the **Add Item** action from the **Shopify Products** page. This process is the default behavior. |
|**To Shopify**| Select this option if, after initial sync triggered by **Add Item** action, you plan to update products manually using **Sync Product** action or via job queue for recurring updates. Remember to enable **Can Update Shopify Product** field. If not enabled, it's equal to **Blank** option. For more information, see [Export items to Shopify](synchronize-items.md#export-items-to-shopify)|
|**From Shopify**| Choose this option, if you plan to import products from Shopify in bulk; either manually using **Sync Product** action or via job queue for recurring updates. If no option is selected, it equals to **Blank** option. For more details about import of items, see [Import items from Shopify](synchronize-items.md#import-items-from-shopify)|

## Import items from Shopify

Either you import items from Shopify in bulk or together with import of orders, these items are added to the **Shopify Product** and **Shopify Variant** tables first. The following settings let you manage the process:

|Field|Description|
|------|-----------|
|**Auto create unknown items**|When shopify products and variants are imported to [!INCLUDE[prod_short](../includes/prod_short.md)], the [!INCLUDE[prod_short](../includes/prod_short.md)] function always tries to find matching record in the item list first. **SKU Mapping** impacts how the matching is performed and creates new item and/or item variant. Enable this option if you want to create a new item or when a matching record doesn't exist. The new item will be created using imported data and **Item Template Code**. If this option isn't enabled, you'll need to create an item manually and use **Map Product** action from **Shopify Products** page.|
|**Item Template Code**|Used together with **Auto create unknown items**. <br> Choose the template to be used for automatically created items.|
|**SKU Mapping**|Choose how you want to use **SKU** value imported from Shopify during item/variant mapping and creation. For more information, see [How SKU and Barcode defined in Shopify product affects mapping and creation of items and variants](synchronize-items.md#how-skus-and-barcodes-defined-in-shopify-product-affects-mapping-and-creation-of-items-and-variants-in-business-central)|
|**SKU Field Separator**|Used together with **SKU Mapping** set to **Item. No + Variant Code** option.<br> Define a separator that should be used to split SKU. <br>For example, if in Shopify you create the variant with SKU '1000/001', type '/' in the **SKU Field Separator** field to get the item number in [!INCLUDE[prod_short](../includes/prod_short.md)] as '1000' and the item variant code as '001'.
|**Variant Prefix**|Used together with **SKU Mapping** set to **Variant Code** or **Item. No + Variant Code** options as a fallback strategy when the SKU coming from Shopify is empty.<br>If you want to create the item variant in [!INCLUDE[prod_short](../includes/prod_short.md)] automatically, you'll need to enter a value in **Code**. By default, the value defined in the SKU field imported from Shopify is used. However, if the SKU is empty, it will generate code starting with defined variant prefix and "001".|
|**Shopify Can Update Item**| Choose this option if you want to update items and/or variants automatically.|

### How SKUs and barcodes defined in Shopify product affects mapping and creation of items and variants in Business Central

When products are imported from Shopify to **Shopify Products** and **Shopify Variants** tables, [!INCLUDE[prod_short](../includes/prod_short.md)] tries to find existing records. The following table outlines the difference among the options in the **SKU Mapping** field.

|Option|Effect on mapping|Effect on creation|
|------|-----------------|------------------|
|**Blank**|The SKU field isn't used in item mapping routine.|No effect on creation of the item. <br>Prevents creation of variants. It's useful when in sales order, only main item is used. A variant can still be mapped manually from **Shopify Product** window.|
|**Item No.**|Choose, if the SKU field contains the item no.|No effect on creation of item without variants. For an item with variants, each variant is created as a separate item.<br> For example, if Shopify has a product with two variants and their SKUs are '1000' and '2000', in [!INCLUDE[prod_short](../includes/prod_short.md)] system will create two items with numbers '1000' and '2000'.|
|**Variant Code**|The SKU field isn't used in the item mapping routine.|No effect on creation of the item. When an item variant is created, the value of SKU field is used as a Code. If the SKU is empty, a code is generated using the **Variant Prefix** field.|
|**Item No. + Variant Code**| Select if the SKU field contains an item no. and the item variant code separated by value defined in the **SKU Field Separator** field.|When an item is created, the first part of the value of the SKU field is used as **No.**. If the SKU is empty, an item no. is generated using number series defined in the **Item Template Code** or **Item Nos.** from the **Inventory Setup** window.<br>When an item is created, the variant function uses the second part of value of the SKU field as **Code**. If the SKU is empty, a code is generated  using the **Variant Prefix** field.|
|**Vendor Item No.**| Choose if the SKU field contains the vendor item no. In this case, the **Item Vendor No.** isn't used in the **Item card** window, but **Vendor Item No.** from the **Item Vendor Catalog**. If the found *Item Vendor Catalog* record contains a variant code, this variant code is used to map the Shopify variant.|If a corresponding vendor exists in [!INCLUDE[prod_short](../includes/prod_short.md)], the SKU value will be used as **Vendor Item No.** in the **Item Card** and as **Item Reference** of type Vendor. <br>Prevents creation of variants. It's useful when you want to use main item only in the sales order. You'll still be able to map a variant manually from **Shopify Product** window.|
|**Barcode**| Choose if the SKU field contains a barcode. A search is performed among **Item References** of type Vendor. If the found Item Reference record contains a variant code, this variant code will be used to map the Shopify variant.|No effect on creation of the item. <br>Prevents creation of variants. It can be useful if only main item is used in the sales order. A variant can still be mapped manually from **Shopify Product** window.|

The following table outlines the effect of **Barcode** field.

|Effect on mapping|Effect on creation|
|-----------------|------------------|
|A search is performed among **Item References** of the type barcode for the value defined in the Barcode field in Shopify. If the found item reference record contains a variant code, this variant code will be used to map the Shopify variant.|Barcode is saved as **Item Reference** for item and item variant.|

> [!NOTE]  
> You can trigger mapping for the selected product/variants or all imported unmapped products by choosing **Try Find Product Mapping** (for selected) or **Try Find Mappings** (for all).

## Export items to Shopify

Choose the elements from your item list, which will be exported to Shopify. Use the **Add Item** action from the **Shopify Products** window to add items to the Shopify products list.

The following settings let you manage the process of exporting items:

|Field|Description|
|------|-----------|
|**Customer Price Group**|Determine the price for an item in Shopify. The sales price of this customer price group is taken. If no group is entered, the price of the item card is used.|
|**Customer Discount Group**|Determine the discount to be used for calculating the price of an item in Shopify. Discounted prices are stored in the **Price** field and full price is stored in the **Compare at Price** field.|
|**Sync Item Extended Text**|Select to sync the extended text of the item. As it will be added to *Description*, it can contain HTML code. |
|**Sync Item Attributes**|Select to sync the item attributes. Attributes are formatted as a table and included in *Description* field on Shopify.|
|**Language Code**|If selected, the translated versions are used for title, attributes, and extended text.|
|**SKU Mapping**|Choose how you like to populate the SKU field in Shopify. Supported options are:<br> - **Item No.** to use item no. for both products and variants.<br> - **Item No.+ Variant Code**  to create a SKU by concatenating values of two fields. For items without variants, the item no. is used only.<br>- **Item Vendor No.** to use item vendor number defined in the *Item Card* for both products and variants.<br> - **Barcode** - uses **Item Reference** of barcode type. This option respects variants. |
|**SKU Field Separator**|Define a separator for **Item. No + Variant Code** option.|
|**Inventory Tracked**|Choose how the system should populate the **Track Inventory** field for products exported to Shopify. You can update availability information from [!INCLUDE[prod_short](../includes/prod_short.md)] for products in Shopify whose track inventory is enabled. For more information, see [Inventory](synchronize-items.md#sync-inventory-to-shopify).|
|**Default Inventory Policy**|Choose *Deny* to prevent negative stock of the Shopify side. |
|**Can Update Shopify Products**|Define if [!INCLUDE[prod_short](../includes/prod_short.md)] can only create items or can update items as well. Select this option, if you, after the initial sync triggered by the **Add Item** action, plan to update products manually using **Sync Product** action or via job queue for recurring updates. Remember to select **To Shopify** in the **Item Sync** field.|

### Fields mapping overview

|Shopify|Source when exported from [!INCLUDE[prod_short](../includes/prod_short.md)]|Target when imported to [!INCLUDE[prod_short](../includes/prod_short.md)]|
|------|-----------------|-----------------|
|Status|According to the **Status for Created Products** in the **Shopify Shop Card**. For more information, see [Ad-hock updates of Shopify Products](synchronize-items.md#ad-hock-updates-of-shopify-products).|Not used.|
|Title|**Description**. If the language code is defined and corresponding item translation exists, item translation will be used instead of description.|**Description**|
|Description|Combines extended texts and attributes if corresponding toggles in the Shopify shop card are enabled. Respects language code.|Not used.|
|SEO page title|Fix value: empty, see [Ad-hock updates of Shopify Products](synchronize-items.md#ad-hock-updates-of-shopify-products). |Not used.|
|SEO meta description|Fix value: empty, see [Ad-hock updates of Shopify Products](synchronize-items.md#ad-hock-updates-of-shopify-products). |Not used.|
|Media|**Image**, for more information, see [Sync Item Images](synchronize-items.md#sync-item-images)|**Image**|
|Price|The calculation of the end-customer price includes the item price group, item discount group, currency code, and customer template code. |Not used.|
|Compare at price|The calculation of price without discount includes the item price group, item discount group, currency code, and customer template code. |Not used.|
|Cost per item|**Unit Cost**|**Unit Cost**|
|SKU|See **SKU Mapping** in the [Export items to Shopify](synchronize-items.md#export-items-to-shopify)| See [How SKU and Barcode defined in Shopify product affect mapping and creation of items and variants](synchronize-items.md#how-skus-and-barcodes-defined-in-shopify-product-affects-mapping-and-creation-of-items-and-variants-in-business-central)|
|Barcode|**Item References** of barcode type|**Item References** of barcode type|
|Track quantity|According to the **Inventory Tracked** in the **Shopify Shop Card**. For more information, see [Inventory](synchronize-items.md#sync-inventory-to-shopify).|Not used.|
|Continue selling when out of stock|According to the **Default Inventory Policy** in the **Shopify Shop Card**. Not imported.|Not used.|
|Type|**Description** of **Item Category Code**. If type isn't specified on Shopify, it will be added as a custom type.|**Item Category Code**. Mapping by description.|
|Vendor|**Name** of vendor from **Vendor No.** |**Vendor No.** Mapping by name.|
|Weight|**Gross Weight**.|Not used.|
|Taxable|Fixed value: Enabled.|Not used.|
|Tax Codes|**Tax Group Code**. Only relevant for sales taxes. For more information, see [Setup taxes](setup-taxes.md). |Not used.|

### Tags

Review the imported tags in the **Tags** FactBox in the **Shopify Product** page. To edit tags, choose the **Tags** action in the **Shopify Product** page.
If the **To Shopify** option is selected in the **Sync Item** field, assigned tags are exported to Shopify at next synchronization.

## Run item synchronization

Full or partial synchronization of items can be performed in many different ways.

### Initial sync of items from Business Central to Shopify

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products** and choose the related link.
2. Choose the **Add Items** action.
3. In the **Shop Code** field, enter the code. If you open the **Shopify Product** window from the **Shop Card** window, the Shop Code will be populated automatically.
4. Define filters on items as required. For example, you can filter by item no. or item category code.
5. Choose **OK**.

The resulting items are automatically created in Shopify with prices but images and inventory levels aren't included. The operation might take some time if a large number of items is added.

### Sync products from Shopify to Business Central

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop** and choose the related link.
2. Select the Shop for which you want to synchronize items to open **Shopify Shop Card** page.
3. Choose the **Sync Products** action.

Alternatively, use the **Sync Products** action on the **Shopify Products** window or search for **Sync Products** batch job.

You can schedule the task to be performed in an automated manner. For more information, see [Schedule recurring tasks](background.md#to-schedule-recurring-tasks).

### Ad-hock updates of Shopify Products

When the records are updated in the **Shopify Product** table, the following changes are synchronized with Shopify.

Update:

* **Status** - you can choose between active, archived, or draft.
* **SEO Title**
* **SEO Description**

Deletion:

Based on the value in **Action for Removed Products** in **Shopify Shop Card**, the product gets updated in Shopify when record is deleted from the **Shopify Products** page.

* **Blank** - nothing will happen. If necessary, the user needs to perform the required action from Shopify Admin.
* **Status to Draft** - status of product in Shopify is set to *Draft*.
* **Status to Archived** - product is archived in Shopify.

## Sync item images

Synchronization of images can be configured for synchronized items. You can choose from following options:

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

Prices can be exported for synchronized items in the ways described below.

### Sync prices from the Shopify products window

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products** and choose the related link.
2. Choose the **Sync Prices to Shopify** action.

### Price calculation remarks

* For price calculation, it's important to have a value in the **Default Customer Template** field. For more information about, see [Setup taxes](tax-setup.md).
* Enter a **Currency Code** if your online shop uses different currency than LCY. The specified currency must have exchange rates configured. If your online shop uses same currency as [!INCLUDE[prod_short](../includes/prod_short.md)], leave the field empty.
* When determining a price, [!INCLUDE[prod_short](../includes/prod_short.md)] uses "Lowest price" logic. It means that if unit price defined in the item card is lower than what is defined in the price group, the unit price from the item card is used.

## Sync inventory to Shopify

Inventory synchronization can be configured for already synchronized items. There are two conditions that must be met:

1. Inventory tracking must be enabled for a product in Shopify. If items are exported to Shopify, consider enabling **Inventory Tracked** toggle in the **Shopify Shop** card. For more information, see [Export items to Shopify](synchronize-items.md#export-items-to-shopify).
2. Inventory synch must be enabled for **Shopify Locations**.

### To enable inventory sync

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop** and choose the related link.
2. Select the Shop for which you want to synchronize inventory to open **Shopify Shop Card** page.
3. Choose the **Locations** action to open **Shopify Shop Locations**.
4. Choose the **Get Shopify Locations** action to import all the locations defined in the Shopify. You can find them in the [**Locations**](https://www.shopify.com/admin/settings/locations) settings in your **Shopify admin**.
5. In the **Location Filter** field, add locations, if you want to include inventory from specific locations only. For example, you can enter *EAST|WEST*, so that inventory only from these two locations is available for sales via online shop.
6. Deselect the **Disabled** toggle to enable inventory sync for selected Shopify locations.

You can initialize inventory synchronization in two ways.

### Sync inventory from the Shopify shop window

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops** and choose the related link.
2. Select the Shop for which you want to synchronize inventory to open **Shopify Shop Card** page.
3. Choose the **Sync inventory** action.

### Sync inventory from the Shopify products window

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products** and choose the related link.
2. Choose the **Sync inventory** action.

### Inventory remarks

* The connector calculates the **Projected Available Balance** and export it to Shopify.
* You can inspect the stock information received from Shopify in the **Shopify Inventory FactBox** page. In this FactBox, you get an overview of the Shopify Stock and the last calculated inventory in [!INCLUDE[prod_short](../includes/prod_short.md)]. There's a record per location.
* If the stock information in Shopify is different from **Projected Available Balance** in [!INCLUDE[prod_short](../includes/prod_short.md)], then stock will be updated in Shopify.

## See Also

[Get Started with the Connector for Shopify](get-started.md)  
