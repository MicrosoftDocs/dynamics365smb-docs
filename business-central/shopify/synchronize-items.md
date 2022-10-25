---
title: Synchronize items and inventory
description: Set up and run synchronizations of items between Shopify and Business Central
ms.date: 05/27/2022
ms.topic: article
ms.service: dynamics365-business-central
ms.search.form: 30116, 30117, 30126, 30127, 
author: AndreiPanko
ms.author: andreipa
ms.reviewer: solsen
---

# Synchronize Items and Inventory

The **Items** in [!INCLUDE[prod_short](../includes/prod_short.md)] are equivalent to the *products* in Shopify and include physical goods, digital downloads, services, and gift cards that you may sell. There are two main reasons to synchronize the items:

1. Data management is primarily performed in [!INCLUDE[prod_short](../includes/prod_short.md)]. You need to export all or some data from there into Shopify and make it visible. You can export the item name, description, image, prices, availability, variants, vendor details, and barcode. Once exported, you can review the items or have them made visible immediately.
2. When an order from Shopify is imported, the information about items is vital to further document processing in [!INCLUDE[prod_short](../includes/prod_short.md)].

The preceding two scenarios are always enabled.

A third scenario is to manage data in Shopify but import those items in bulk to [!INCLUDE[prod_short](../includes/prod_short.md)]. This scenario can be useful for data migration events, such as when you want to connect an existing online shop with a new [!INCLUDE[prod_short](../includes/prod_short.md)] environment.

## Define item synchronizations

1. Choose the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon and enter **Shopify Shop**. Open the shop for which you want to configure the item synchronization.
2. From the **Sync item** field, select the required option.

   The following table outlines the options.

|Option|Description|
|------|-----------|
|**Blank**| Products are imported together with the importing of orders. Products are exported to Shopify if a user runs the **Add Item** action from the **Shopify Products** page. This is the default process.|
|**To Shopify**| Select this option if, after the initial sync is triggered by the **Add Item** action, you plan to update products manually using the **Sync Product** action or using the job queue for recurring updates. Remember to enable the **Can Update Shopify Product** field. If it's not enabled, it equals the **Blank** (default process) option. Learn more in the [Export items to Shopify](synchronize-items.md#export-items-to-shopify) section.|
|**From Shopify**| Choose this option if you plan to import products from Shopify in bulk, either manually using the **Sync Product** action or using the job queue for recurring updates. Learn more in the [Import items from Shopify](synchronize-items.md#import-items-from-shopify) section.|

## Import items from Shopify

First, import items either in bulk from Shopify or together with orders to add them to the **Shopify Product** and **Shopify Variant** tables. Then map imported products and variants to items and variants in [!INCLUDEprod_short]. Manage the process using the following settings:

|Field|Description|
|------|-----------|
|**Auto create unknown items**|When Shopify products and variants are imported into [!INCLUDE[prod_short](../includes/prod_short.md)], the [!INCLUDE[prod_short](../includes/prod_short.md)] function first tries to find the matching record in the item list. **SKU Mapping** impacts how the matching is performed and creates a new item and/or item variant. Enable this option if you want to create a new item or when a matching record doesn't exist. The new item is created using imported data and the **Item Template Code**. If this option isn't enabled, you'll need to create an item manually and use the **Map Product** action on the **Shopify Products** page.|
|**Item Template Code**|Use this with the **Auto create unknown items** toggle.<br>Choose the template you want to use for automatically created items.|
|**SKU Mapping**|Choose how you want to use the **SKU** value imported from Shopify during the item/variant mapping and creation. Learn more in the [Effect of Shopify product SKUs and barcodes on mapping and creating items and variants in Business Central](synchronize-items.md#effect-of-shopify-product-skus-and-barcodes-on-mapping-and-creating-items-and-variants-in-business-central) section.|
|**SKU Field Separator**|Use this with **SKU Mapping** set to the **[Item. No + Variant Code](synchronize-items.md#effect-of-shopify-product-skus-and-barcodes-on-mapping-and-creating-items-and-variants-in-business-central)** option.<br>Define a separator to be used to split the SKU.<br>So, if in Shopify you create the variant with the SKU '1000/001', you'd type '/' in the **SKU Field Separator** field to make the item number in [!INCLUDE[prod_short](../includes/prod_short.md)] '1000' and the item variant code '001'.|
|**Variant Prefix**|Use together with **SKU Mapping** set to either the **Variant Code** or **Item No. + Variant Code** option as a fallback function when the SKU coming from Shopify is empty.<br>If you want to create the item variant in [!INCLUDE[prod_short](../includes/prod_short.md)] automatically, you'll need to enter a value in **Code**. By default, the value defined in the SKU field imported from Shopify is used. However, if the SKU is empty, it will generate code starting with the defined variant prefix and "001".|
|**Shopify Can Update Item**|Choose this option if you want to update items and/or variants automatically.|

### Effect of Shopify product SKUs and barcodes on mapping and creating items and variants in Business Central

When products are imported from Shopify to **Shopify Products** and **Shopify Variants** tables, [!INCLUDE[prod_short](../includes/prod_short.md)] tries to find existing records.

The following table outlines the differences between options in the **SKU Mapping** field.

|Option|Effect on mapping|Effect on creation|
|------|-----------------|------------------|
|**Blank**|The SKU field isn't used in the item mapping routine.|No effect on the creation of the item.<br>This option prevents the creation of variants. When in sales order, only the main item is used. A variant can still be mapped manually on the **Shopify Product** page.|
|**Item No.**|Choose if the SKU field contains the item number|No effect on the creation of an item without variants. For an item with variants, each variant is created as a separate item.<br>So, if Shopify has a product with two variants and their SKUs are '1000' and '2000', [!INCLUDE[prod_short](../includes/prod_short.md)] will create two items numbered '1000' and '2000'.|
|**Variant Code**|The SKU field isn't used in the item mapping routine.|No effect on creation of the item. When an item variant is created, the value of the SKU field is used as a code. If the SKU is empty, a code is generated using the **Variant Prefix** field.|
|**Item No. + Variant Code**|Select this if the SKU field contains an item number and the item variant code is separated by the value defined in the **SKU Field Separator** field.|When an item is created, the first part of the value of the SKU field is designated **No.**. If the SKU field is empty, an item number is generated using the number series defined in the **Item Template Code** or **Item Nos.** field of the **Inventory Setup** page.<br>When an item is created, the variant function uses the second part of the value of the SKU field as **Code**. If the SKU field is empty, a code is generated using the **Variant Prefix** field.|
|**Vendor Item No.**|Choose if the SKU field contains the vendor item number. In this case, the **Item Vendor No.** isn't used on the **Item Card** page; rather the **Vendor Item No.** from the **Item Vendor Catalog** is used. If the found *Item Vendor Catalog* record contains a variant code, that code is used to map the Shopify variant.|If a corresponding vendor exists in [!INCLUDE[prod_short](../includes/prod_short.md)], the SKU value will be used as the **Vendor Item No.** on the **Item Card** page and as the **Item Reference** of the vendor type. <br>Prevents the creation of variants. It's useful when you want to use only the main item in the sales order. You're still able to map a variant manually from the **Shopify Product** page.|
|**Barcode**|Choose if the SKU field contains a barcode. A search is performed among **Item References** of the vendor type. If the found item reference record contains a variant code, that variant code is used to map the Shopify variant.|No effect on the creation of the item. <br>Prevents the creation of variants. It's useful when you want to use only the main item in the sales order. You're still able to map a variant manually from the **Shopify Product** page.|

The following table outlines the effects of the **Barcode** field.

|Effect on mapping|Effect on creation|
|-----------------|------------------|
|A search is performed on the **Item References** containing a barcode type as the value in the **Barcode** field in Shopify. If the found item reference record contains a variant code, that variant code is used to map the Shopify variant.|The barcode is saved as **Item Reference** for the item and item variant.|

> [!NOTE]  
> You can trigger mapping of the selected products/variants by choosing **Try Find Product Mapping** or of all the imported unmapped products by choosing **Try Find Mappings**.

## Export items to Shopify

Choose the elements from your item list to be exported to Shopify. Use the **Add Item** action on the **Shopify Products** page to add items to the Shopify products list.

You manage the process of exporting items using these settings:

|Field|Description|
|------|-----------|
|**Customer Price Group**|Determine the price for an item in Shopify. The sales price of this customer price group is taken. If no group is entered, the price on the item card is used.|
|**Customer Discount Group**|Determine the discount to be used for calculating the price of an item in Shopify. Discounted prices are stored in the **Price** field and full price is stored in the **Compare at Price** field.|
|**Sync Item Extended Text**|Select this to sync the extended text of the item. As it will be added to the *Description* field, it can contain HTML code. |
|**Sync Item Attributes**|Select this to sync the item attributes. Attributes are formatted as a table and included in the *Description* field in Shopify.|
|**Language Code**|Select this if you want the translated versions used for title, attributes, and extended text.|
|**SKU Mapping**|Choose how you want to populate the SKU field in Shopify. Supported options are:<br> - **Item No.** to use the item no. for both products and variants.<br> - **Item No.+ Variant Code**  to create an SKU by concatenating values of two fields. For items without variants, the item number only is used.<br>- **Item Vendor No.** to use the item vendor number defined in the *Item Card* for both products and variants.<br> - **Barcode** to use the barcode type of **Item Reference**. This option respects variants.|
|**SKU Field Separator**|Define a separator for the **Item. No + Variant Code** option.|
|**Inventory Tracked**| Choose how the system should populate the **Track Inventory** field for products exported to Shopify. You can update availability information from [!INCLUDE[prod_short](../includes/prod_short.md)] for products in Shopify whose track inventory is enabled. Learn more in the [Inventory](synchronize-items.md#sync-inventory-to-shopify) section.|
|**Default Inventory Policy**|Choose *Deny* to prevent negative stock on the Shopify side.|
|**Can Update Shopify Products**|Define this if [!INCLUDE[prod_short](../includes/prod_short.md)] can only create items or can update items as well. Select this option if, after the initial sync is triggered by the **Add Item** action, you plan to update products manually using the **Sync Product** action or using the job queue for recurring updates. Remember to select **To Shopify** in the **Item Sync** field.|
|**Customer Template Code**|Choose the default template to be used during price calculation. Learn more at [Set up Taxes](setup-taxes.md).|

### Fields mapping overview

|Shopify|Source when exported from [!INCLUDE[prod_short](../includes/prod_short.md)]|Target when imported to [!INCLUDE[prod_short](../includes/prod_short.md)]|
|------|-----------------|-----------------|
|Status|According to the **Status for Created Products** field in the **Shopify Shop Card**. Learn more in the [Ad-hoc updates of Shopify products](synchronize-items.md#ad-hoc-updates-of-shopify-products) section.|Not used.|
|Title | **Description**. If the language code is defined and a corresponding item translation exists, the item translation will be used instead of the description.|**Description**|
|Description|Combines extended texts and attributes if the corresponding toggles on the Shopify shop card are enabled. Respects the language code.|Not used.|
|SEO page title|Fixed value: empty. Learn more in the [Ad-hoc updates of Shopify products](synchronize-items.md#ad-hoc-updates-of-shopify-products) section.|Not used.|
|SEO meta description|Fixed value: empty. Learn more in the [Ad-hoc updates of Shopify products](synchronize-items.md#ad-hoc-updates-of-shopify-products) section.|Not used.|
|Media|**Image**. Learn more in the [Sync item images](synchronize-items.md#sync-item-images) section|**Image**|
|Price|The calculation of the end-customer price includes the item price group, item discount group, currency code, and customer template code.|**Unit Price**|
|Compare at price|The calculation of the price without a discount includes the item price group, item discount group, currency code, and customer template code.|Not used.|
|Cost per item|**Unit Cost**|**Unit Cost**|
|SKU|Learn about this under **SKU Mapping** in the [Export items to Shopify](synchronize-items.md#export-items-to-shopify) section.|Learn about this in the [Effect of Shopify product SKUs and barcodes on mapping and creating items and variants in Business Central](synchronize-items.md#effect-of-shopify-product-skus-and-barcodes-on-mapping-and-creating-items-and-variants-in-business-central) section.|
|Barcode|**Item References** of the barcode type.|**Item References** of the barcode type.|
|Track quantity|According to the **Inventory Tracked** field on the **Shopify Shop Card** page. Learn more in the [Inventory](synchronize-items.md#sync-inventory-to-shopify) section.|Not used.|
|Continue selling when out of stock|According to the **Default Inventory Policy** in the **Shopify Shop Card**. Not imported.|Not used.|
|Type|**Description** of **Item Category Code**. If the type isn't specified in Shopify, it is added as a custom type.|**Item Category Code**. Mapping by description.|
|Vendor|**Name** of vendor from **Vendor No.**|**Vendor No.** Mapping by name.|
|Weight|**Gross Weight**.|Not used.|
|Taxable|Fixed value: enabled.|Not used.|
|Tax codes|**Tax Group Code**. Only relevant for sales taxes. Learn more at [Set up Taxes](setup-taxes.md).|Not used.|

### Tags

Review the imported tags in the **Tags** FactBox on the **Shopify Product** page. On the same page, to edit tags, choose the **Tags** action.
If the **To Shopify** option is selected in the **Sync Item** field, assigned tags are exported to Shopify at the next synchronization.

## Run item synchronization

Full or partial item synchronization can be performed in many different ways.

### Initial sync of items from Business Central to Shopify

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and choose the related link.
2. Choose the **Add Items** action.
3. In the **Shop Code** field, enter the code. If you open the **Shopify Product** window from the **Shop Card** page, the shop code will be populated automatically.
4. Define filters on items as required. For example, you can filter by the item no. or item category code.
5. Choose **OK**.

The resulting items are automatically created in Shopify with prices but images and inventory levels aren't included. The operation might take some time if a large number of items are added.

### Sync products from Shopify to Business Central

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and choose the related link.
2. Select the shop for which you want to synchronize items to open the **Shopify Shop Card** page.
3. Choose the **Sync Products** action.

Alternatively, use the **Sync Products** action on the **Shopify Products** page or search for the **Sync Products** batch job.

You can schedule the task to be performed in an automated manner. Learn more at [Schedule recurring tasks](background.md#to-schedule-recurring-tasks).

### Ad-hoc updates of Shopify products

When the records are updated in the **Shopify Product** table, the following changes are synchronized with Shopify.

Update:

* **Status** - You can choose between active, archived, or draft.
* **SEO Title**
* **SEO Description**

Deletion:

Based on the value in **Action for Removed Products** on the **Shopify Shop Card** page, the product gets updated in Shopify when the record is deleted from the **Shopify Products** page.

* **Blank** - Nothing will happen. If necessary, you'll need to perform the required action from the **Shopify admin**.
* **Status to Draft** - The status of the product in Shopify is set to *Draft*.
* **Status to Archived** - The product is archived in Shopify.

## Sync item images

Synchronization of images can be configured for synchronized items. Choose from the following options:

* **Disabled** - Image synchronization is deactivated.
* **To Shopify** - Pictures of items are exported to Shopify.
* **From Shopify** - Images from Shopify are imported to [!INCLUDE[prod_short](../includes/prod_short.md)].

Image synchronization can be initialized in the two ways described below.

### Sync product images from the Shopify shop page

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and choose the related link.
2. Select the shop for which you want to synchronize images to open the **Shopify Shop Card** page.
3. Choose the **Sync Product Images** action.

### Sync product images from the Shopify products page

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and choose the related link.
2. Choose the **Sync Product Images** action.

### Image synchronization remarks

* When exporting images from [!INCLUDE[prod_short](../includes/prod_short.md)] to Shopify, the new images are added to Shopify, keeping old images intact. If an image is updated in [!INCLUDE[prod_short](../includes/prod_short.md)], you'll need to delete the old images in the **Shopify Admin**.
* Images exported to Shopify that don't comply with requirements defined by Shopify won't be imported. Learn more about [product media types on help.shopify.com](https://help.shopify.com/en/manual/products/product-media/product-media-types#images).

## Sync prices with Shopify

Prices for synchronized items can be exported in the two ways described below.

### Sync prices from the Shopify products page

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and choose the related link.
2. Choose the **Sync Prices to Shopify** action.

### Price calculation remarks

* For price calculation, it's important to have a value in the **Default Customer Template** field. Learn more at [Set up Taxes](setup-taxes.md).
* Enter a **currency code** only if your online shop uses a different currency than the local currency (LCY). The specified currency must have exchange rates configured. If your online shop uses the same currency as [!INCLUDE[prod_short](../includes/prod_short.md)], leave the field empty.
* When determining a price, [!INCLUDE[prod_short](../includes/prod_short.md)] uses the "lowest price" logic. That means if the unit price defined on the item card is lower than what is defined in the price group, the unit price from the item card price is used.

## Sync inventory to Shopify

Inventory synchronization can be configured for already synchronized items. There are two conditions that must be met:

1. Inventory tracking must be enabled for a product in Shopify. If items are exported to Shopify, consider enabling the **Inventory Tracked** toggle on the **Shopify Shop** page. Learn more in the [Export items to Shopify](synchronize-items.md#export-items-to-shopify) section.
2. Inventory sync must be enabled for **Shopify Locations**.

### To enable inventory sync

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and choose the related link.
2. Select the shop for which you want to synchronize inventory to open the **Shopify Shop Card** page.
3. Choose the **Locations** action to open **Shopify Shop Locations**.
4. Choose the **Get Shopify Locations** action to import all the locations defined in Shopify. You can find them in the [**Locations**](https://www.shopify.com/admin/settings/locations) settings in your **Shopify Admin**.
5. In the **Location Filter** field, add locations if you want to include inventory from specific locations only. So, you could enter *EAST|WEST* to make the inventory from only these two locations available for sales via the online shop.
6. Deselect the **Disabled** toggle to enable inventory sync for selected Shopify locations.

You can initialize inventory synchronization in the two ways described below.

### Sync inventory from the Shopify shop page

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and choose the related link.
2. Select the shop for which you want to synchronize inventory to open the **Shopify Shop Card** page.
3. Choose the **Sync inventory** action.

### Sync inventory from the Shopify products page

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and choose the related link.
2. Choose the **Sync inventory** action.

### Inventory remarks

* The connector calculates the **Projected Available Balance** and exports it to Shopify.
* You can inspect the stock information received from Shopify on the **Shopify Inventory FactBox** page. In this FactBox, you get an overview of the Shopify stock and the last calculated inventory in [!INCLUDE[prod_short](../includes/prod_short.md)]. There's one record per location.
* If the stock information in Shopify is different than the **Projected Available Balance** in [!INCLUDE[prod_short](../includes/prod_short.md)], then the stock will be updated in Shopify.

## See also

[Get Started with the Connector for Shopify](get-started.md)  
