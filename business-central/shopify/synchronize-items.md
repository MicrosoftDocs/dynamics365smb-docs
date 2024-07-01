---
title: Synchronize items and inventory
description: Set up and run synchronizations of items between Shopify and Business Central
ms.date: 04/28/2024
ms.topic: article
ms.search.form: 30116, 30117, 30126, 30127, 
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.custom: bap-template
---

# Synchronize items and inventory

**Items** in [!INCLUDE[prod_short](../includes/prod_short.md)] are equivalent to **products** in Shopify. They're the physical goods, digital downloads, services, and gift cards that you sell. There are two main reasons to synchronize items:

1. When you primarily manage data in [!INCLUDE[prod_short](../includes/prod_short.md)]. You need to export all or some data from there into Shopify and make it visible. You can export the item name, description, image, prices, availability, variants, vendor details, and barcode. Once exported, you can review the items or make them visible immediately.
2. When an order from Shopify is imported, the information about items is vital to further document processing in [!INCLUDE[prod_short](../includes/prod_short.md)].

The preceding two scenarios are always enabled.

A third scenario is to manage data in Shopify but import those items in bulk to [!INCLUDE[prod_short](../includes/prod_short.md)]. This scenario can be useful for data migration events, such as when you want to connect an existing online shop with a new [!INCLUDE[prod_short](../includes/prod_short.md)] environment.

## Define item synchronizations

1. Choose the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon and enter **Shopify Shop**. Open the shop for which you want to configure the item synchronization.
2. From the **Sync item** field, select the required option.

   The following table outlines the options.

   |Option|Description|
   |------|-----------|
   |**Blank**| Products are imported together with the importing of orders. Products are exported to Shopify if a user runs the **Add Item** action from the **Shopify Products** page. This option is the default process.|
   |**To Shopify**| Select this option if, after the initial sync is triggered by the **Add Item** action, you plan to update products manually using the **Sync Product** action or using the job queue for recurring updates. Remember to enable the **Can Update Shopify Product** field. If it isn't enabled, it equals the **Blank** (default process) option. Learn more in the [Export items to Shopify](synchronize-items.md#export-items-to-shopify) section.|
   |**From Shopify**| Choose this option if you plan to import products from Shopify in bulk, either manually using the **Sync Product** action or using the job queue for recurring updates. Learn more in the [Import items from Shopify](synchronize-items.md#import-items-from-shopify) section.|

   > [!NOTE]
   > Changing **Sync Item** from **From Shopify** to **To Shopify** won't have an effect unless you enable **Can Update Shopify Products**.

## Import items from Shopify

First, import items either in bulk from Shopify or together with orders to add them to the **Shopify Product** and **Shopify Variant** tables. Then map imported products and variants to items and variants in [!INCLUDE[prod_short](../includes/prod_short.md)]. Manage the process using the following settings:

|Field|Description|
|------|-----------|
|**Auto create unknown items**|When Shopify products and variants are imported into [!INCLUDE[prod_short](../includes/prod_short.md)], the [!INCLUDE[prod_short](../includes/prod_short.md)] function first tries to find the matching record in the item list. **SKU Mapping** impacts how the matching is performed and creates a new item and/or item variant. Enable this option if you want to create a new item or when a matching record doesn't exist. The new item is created using imported data and the **Item Template Code**. If this option isn't enabled, create an item manually and use the **Map Product** action on the **Shopify Products** page.|
|**Item Template Code**|Use this field with the **Auto create unknown items** toggle.<br>Choose the template you want to use for automatically created items.|
|**SKU Mapping**|Choose how you want to use the **SKU** value imported from Shopify during the item/variant mapping and creation. Learn more in the [Effect of Shopify product SKUs and barcodes on mapping and creating items and variants in Business Central](synchronize-items.md#effect-of-shopify-product-skus-and-barcodes-on-mapping-and-creating-items-and-variants-in-business-central) section.|
|**SKU Field Separator**|Use this field with **SKU Mapping** set to the **[Item. No + Variant Code](synchronize-items.md#effect-of-shopify-product-skus-and-barcodes-on-mapping-and-creating-items-and-variants-in-business-central)** option.<br>Define a separator to be used to split the SKU.<br>So, if in Shopify you create the variant with the SKU '1000/001', you'd type '/' in the **SKU Field Separator** field to make the item number in [!INCLUDE[prod_short](../includes/prod_short.md)] '1000' and the item variant code '001'. If you create the variant with the SKU '1000/001/111' in Shopify, the item number in [!INCLUDE[prod_short](../includes/prod_short.md)] is '1000' and the item variant code is '001'. The '111' part is ignored. |
|**Variant Prefix**|Use together with **SKU Mapping** set to either the **Variant Code** or **Item No. + Variant Code** option as a fallback function when the SKU coming from Shopify is empty.<br>If you want to create the item variant in [!INCLUDE[prod_short](../includes/prod_short.md)] automatically, you to enter a value in **Code**. By default, the value defined in the SKU field imported from Shopify is used. However, if the SKU is empty, it generates code starting with the defined variant prefix and '001.'|
|**Shopify Can Update Item**|Choose this option if you want to update items and/or variants automatically.|
|**UoM as Variant**| Choose this option if you want all item units of measure to be exported as separate variants. To add the field, personalize the page. Learn more in the [Unit of Measure as Variant](synchronize-items.md#unit-of-measure-as-variant) section.|
|**Variant Option Name for UoM**| Use this field with **UoM as Variant** to specify under which option to add variants that represent units of measure. The default value is *Unit of Measure*. Use personalization to add the field to the page.|

## Export items to Shopify

There are multiple ways to export items to Shopify:

* Use the **Add item to Shopify** action directly from the **Item card** page.
* Use the **Add Item** action on the **Shopify Products** page.
* Run item synchronization once or repeatedly with automation.

No matter how you export items, specific item information is transferred to the Shopify products list depending on your choice of settings for item synchronization.

Before it exports an item to Shopify, the connector checks whether an item already exists. First, it checks whether there's a product or variant with a barcode, because it's defined in the **Item References** entry of a barcode type. If the **SKU Mapping** field is populated, the connector checks whether there's a product or variant with the SKU populated. To learn more, go to [Effect of Shopify product SKUs and barcodes on mapping and creating items and variants in Business Central](synchronize-items.md#effect-of-shopify-product-skus-and-barcodes-on-mapping-and-creating-items-and-variants-in-business-central).

> [!IMPORTANT]
> The product is added only to the **Online Store** sales channel. You need to publish products to other sales channels, like Shopify POS, from Shopify.

You manage the process of exporting items using these settings:

|Field|Description|
|------|-----------|
|**Sync Item Extended Text**|Select this field to sync the extended text of the item. Because it will be added to the **Description** field, it can contain HTML code. |
|**Sync Item Attributes**|Select this field to sync the item attributes. Attributes are formatted as a table and included in the **Description** field in Shopify.|
|**Sync Item Marketing Text**|Select this field to sync marketing text for the item. Although marketing text is a kind of description, it's different from an item's **Description** field. The **Description** field is typically used as a concise display name to quickly identify the product. The marketing text, on the other hand, is more rich and descriptive. Its purpose is to add marketing and promotional content. This text can then be published with the item in Shopify. There are two ways to create the marketing text. Use Copilot, which suggests AI-generated text for you, or start from scratch.|
|**Language Code**|Select this field if you want the translated versions used for title, attributes, and extended text.|
|**SKU Mapping**|Choose how you want to populate the SKU field in Shopify. Supported options are:<br> - **Item No.** to use the item number for both products and variants.<br> - **Item No.+ Variant Code** to create an SKU by concatenating values of two fields. For items without variants, the item number only is used.<br>- **Item Vendor No.** to use the item vendor number defined in the **Item Card** for both products and variants.<br> - **Barcode** to use the barcode type of **Item Reference**. This option respects variants.<br>If **Can Update Shopify Products** is enabled, changes in the **SKU Mapping** field will be propagated to Shopify after the next sync for all products and variants listed in the **Shopify Products** page for the selected shop.|
|**SKU Field Separator**|Define a separator for the **Item. No + Variant Code** option.|
|**Inventory Tracked**| Choose how the system should populate the **Track Inventory** field for products exported to Shopify. You can update availability information from [!INCLUDE[prod_short](../includes/prod_short.md)] for products in Shopify whose track inventory is enabled. Learn more in the [Inventory](synchronize-items.md#sync-inventory-to-shopify) section.|
|**Default Inventory Policy**|Choose *Deny* to prevent negative stock on the Shopify side. <br>If **Can Update Shopify Products** is enabled, changes in the **Default Inventory Policy** field will be propagated to Shopify after next sync for all products and variants listed in the **Shopify Products** page for selected shop.|
|**Can Update Shopify Products**|Define this field if [!INCLUDE[prod_short](../includes/prod_short.md)] can only create items or can update items as well. Select this option if, after the initial sync is triggered by the **Add Item** action, you plan to update products manually using the **Sync Product** action or using the job queue for recurring updates. Remember to select **To Shopify** in the **Item Sync** field.<br>**Can Update Shopify Products** doesn't impact synchronization of prices, images or inventory levels, which are configured by independent controls.<br>If **Can Update Shopify Products** is enabled, the following fields on the Shopify side will be updated on the product and, if needed, the variant level: **SKU**, **Barcode**, **Weight**. The **Title**, **Product Type**, **Vendor**, and **Description** on the product will be also updated if the exported values aren't empty. For description, this means you need to enable any of the **Sync Item Extended Text**, **Sync Item Marketing Text**, and **Sync Item Attributes** toggles and  attributes, extended or marketing text must have values. If the product uses variants, then the variant is added or removed if necessary. <br>If the product on Shopify is configured to use a variant matrix that combines two or more options, the Shopify Connector can't create a variant for that product. In [!INCLUDE[prod_short](../includes/prod_short.md)] there's no way to define an option matrix—that's why the connector uses the **Variant Code** as the only option. However, Shopify expects several options and refuses to create a variant if information about a second and other options is missing. |
|**UoM as Variant**| Choose this option if you want some options to be exported as imported as units of measure instead of variants. Personalize the page to add the field. Learn more in the [Unit of Measure as Variant](synchronize-items.md#unit-of-measure-as-variant) section.|
|**Variant Option Name for UoM**| Use this field with **UoM as Variant** to specify which option contains variants that represent units of measure. The default valie is *Unit of Measure*. Personalize the page to add the field.|

> [!NOTE]
> When you want to export many items and variants, some might be blocked. You can't include blocked items and variants in price calculations, so they aren't exported. The Connector skips those items and variants, so you don't need to filter them on the **Add Item to Shopify** request page.

## Advanced details

### Effect of Shopify product SKUs and barcodes on mapping and creating items and variants in Business Central

When products are imported from Shopify to **Shopify Products** and **Shopify Variants** tables, [!INCLUDE[prod_short](../includes/prod_short.md)] tries to find existing records.

The following table outlines the differences between options in the **SKU Mapping** field.

|Option|Effect on mapping|Effect on creation|
|------|-----------------|------------------|
|**Blank**|The SKU field isn't used in the item-mapping routine.|No effect on the creation of the item.<br>This option prevents the creation of variants. When in a sales order, only the main item is used. A variant can still be mapped manually on the **Shopify Product** page.|
|**Item No.**|Choose if the SKU field contains the item number.|No effect on the creation of an item without variants. For an item with variants, each variant is created as a separate item.<br>If Shopify has a product with two variants and their SKUs are '1000' and '2000', [!INCLUDE[prod_short](../includes/prod_short.md)] will create two items numbered '1000' and '2000'.|
|**Variant Code**|The SKU field isn't used in the item-mapping routine.|No effect on creation of the item. When an item variant is created, the value of the SKU field is used as a code. If the SKU is empty, a code is generated using the **Variant Prefix** field.|
|**Item No. + Variant Code**|Select this option if the SKU field contains an item number and the item variant code is separated by the value defined in the **SKU Field Separator** field.|When an item is created, the first part of the value of the SKU field is designated **No.**. If the SKU field is empty, an item number is generated using the number series defined in the **Item Template Code** or **Item Nos.** field of the **Inventory Setup** page.<br>When an item is created, the variant function uses the second part of the value of the SKU field as **Code**. If the SKU field is empty, a code is generated using the **Variant Prefix** field.|
|**Vendor Item No.**|Choose if the SKU field contains the vendor item number. In this case, the **Item Vendor No.** isn't used on the **Item Card** page; rather the **Vendor Item No.** from the **Item Vendor Catalog** is used. If the found *Item Vendor Catalog* record contains a variant code, that code is used to map the Shopify variant.|If a corresponding vendor exists in [!INCLUDE[prod_short](../includes/prod_short.md)], the SKU value will be used as the **Vendor Item No.** on the **Item Card** page and as the **Item Reference** of the *vendor* type. <br>Prevents the creation of variants. It's useful when you want to use only the main item in the sales order. You're still able to map a variant manually from the **Shopify Product** page.|
|**Barcode**|Choose if the SKU field contains a barcode. A search is performed among **Item References** of the *barcode* type. If the found item reference record contains a variant code, that variant code is used to map the Shopify variant.|No effect on the creation of the item. <br>Prevents the creation of variants. It's useful when you want to use only the main item in the sales order. You're still able to map a variant manually from the **Shopify Product** page.|

The following table outlines the effects of the **Barcode** field.

|Effect on mapping|Effect on creation|
|-----------------|------------------|
|A search is performed on the **Item References** containing a barcode type as the value in the **Barcode** field in Shopify. If the found item reference record contains a variant code, that variant code is used to map the Shopify variant.|The barcode is saved as **Item Reference** for the item and item variant.|

> [!NOTE]  
> You can trigger mapping of the selected products/variants by choosing **Try Find Product Mapping** or of all the imported unmapped products by choosing **Try Find Mappings**.

### Fields-mapping overview

|Shopify|Source when exported from [!INCLUDE[prod_short](../includes/prod_short.md)]|Target when imported to [!INCLUDE[prod_short](../includes/prod_short.md)]|
|------|-----------------|-----------------|
|Status|According to the **Status for Created Products** field in the **Shopify Shop Card**. Learn more in the [Ad hoc updates of Shopify products](synchronize-items.md#ad-hoc-updates-of-shopify-products) section.|Not used.|
|Title | **Description**. If the language code is defined and a corresponding item translation exists, the item translation will be used instead of the description.|**Description**|
|Variant title | **Variant Code**.<br>The reason to use **Code** and not **Description** is because Shopify requires unique variant titles per product. In [!INCLUDE[prod_short](../includes/prod_short.md)] the **Code** is unique, while **Description** is not. Not unique descriptions will lead to issues during product export.|**Description** of variant|
|Description|Combines extended texts, marketing text, and attributes if you enable the corresponding toggles on the Shopify shop card. Respects the language code.|Not used.|
|SEO page title|Fixed value: empty. Learn more in the [Ad hoc updates of Shopify products](synchronize-items.md#ad-hoc-updates-of-shopify-products) section.|Not used.|
|SEO meta description|Fixed value: empty. Learn more in the [Ad hoc updates of Shopify products](synchronize-items.md#ad-hoc-updates-of-shopify-products) section.|Not used.|
|Media|**Image**. Learn more in the [Sync item images](synchronize-items.md#sync-item-images) section|**Image**|
|Price|The calculation of the end-customer price includes the item unit price, customer price group, customer discount group, and currency code. Learn more in the [Sync prices](synchronize-items.md#sync-prices-with-shopify) section|**Unit Price**. The price is only imported to newly created items, but it won't be updated in later synchronizations.|
|Compare at price|The calculation of the price without a discount. If the value is less than or equal to **Price**, the connector sends 0 (null) instead of the actual value.|Not used.|
|Cost per item|**Unit Cost**|**Unit Cost**. The unit cost is only imported to newly created items, and it won't be updated in later synchronizations.|
|SKU|Learn about SKUs under **SKU Mapping** in the [Export items to Shopify](synchronize-items.md#export-items-to-shopify) section.|Learn about SKUs in the [Effect of Shopify product SKUs and barcodes on mapping and creating items and variants in Business Central](synchronize-items.md#effect-of-shopify-product-skus-and-barcodes-on-mapping-and-creating-items-and-variants-in-business-central) section.|
|Barcode|**Item References** of the barcode type.|**Item References** of the barcode type.|
|Inventory will be stocked at| Depends on Shopify Shop Locations. If **Business Central Fulfillment Services** has **Default Product Location** field enabled, inventory is stocked and shipped from **Business Central Fulfillment Services**. Otherwise, the Shopify primary location or multiple locations are used. Learn more in the [Two approaches to manage fulfillments](synchronize-items.md#two-approaches-to-manage-fulfillments) section.| Not used.|
|Track quantity|According to the **Inventory Tracked** field on the **Shopify Shop Card** page. Learn more in the [Inventory](synchronize-items.md#sync-inventory-to-shopify) section. Only used when you export a product for the first time.|Not used.|
|Continue selling when out of stock|According to the **Default Inventory Policy** in the **Shopify Shop Card**.|Not used.|
|Type|**Description** of **Item Category Code**. If the type isn't specified in Shopify, it's added as a custom type.|**Item Category Code**. Mapping by description.|
|Vendor|**Name** of vendor from **Vendor No.**|**Vendor No.** Mapping by name.|
|Weight|**Gross Weight**.|Not used.|
|Taxable|Fixed value: enabled.|Not used.|
|Tax codes|**Tax Group Code**. Only relevant for sales taxes. Learn more at [Set up Taxes](setup-taxes.md).|Not used.|

### Tags

Review the imported tags in the **Tags** FactBox on the **Shopify Product** page. On the same page, to edit tags, choose the **Tags** action.

If the **To Shopify** option is selected in the **Sync Item** field, assigned tags are exported to Shopify at the next synchronization.

### Unit of measure as variant

Shopify doesn't support multiple units of measure. If you want to sell same product as for example piece and set and use different prices or discounts, you need to create unit of measure as product variants.
Shopify connector can be configured to export units of measure as variants, or import variants as units of measure.

To enable this capability use the **UoM as Variant** and **Variant Option Name** fields in the **Shopify Shop Card**. The fields are hidden by default; use personalization to add them to the page.

**Unit of measure as variant remarks**

* When dealing with matrix of variants, for example Color and UoM and you want to import products into [!INCLUDE[prod_short](../includes/prod_short.md)], you should set *Item No. + Variant Code* in the **SKU Mapping** field and make sure that **SKU** field in Shopify has same value for all units of measure and include both item no. and variant code.
* In [!INCLUDE[prod_short](../includes/prod_short.md)] availability is calculated per item/item variant and not by unit of measure. It means same availability will be assigned to each variant representing unit of measure (with respect to **Qty. per Unit of Measure**), that can lead to cases when avaialble quantity in Shopify is not accurate. Example: Item that is sold in PCS and Box of 6. The inventory in [!INCLUDE[prod_short](../includes/prod_short.md)] is 6 PCS. Item exported to Shopify as Product with two variants. Once inventory sync executed the inventory level in Shopify will be 6 for varaint PCS and 1 for variant BOX. Buyer can explore only store and see that product is available in both options and place order for 1 BOX. The next buyer will see that BOX is not avaialble, but there are still 6 PCS. This will be fixed with the next inventory sync.
* You won't be able to add Unit of measure option to existing products with variants (specific result depends on other setting, like **SKU Mapping**).

### URL and Preview URL

An item added to Shopify or imported from Shopify might have the **URL** or **Preview URL** populated. The **URL** field will be empty if the product isn't published to the online store—for example, because its status is draft. The **URL** will be empty if the store is password protected—for example, because this is a development store. In most cases you can use the **Preview URL** to check how the product will look once published.

## Run item synchronization

Full or partial item synchronization can be performed in many different ways.

### Initial sync of items from Business Central to Shopify

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and choose the related link.
2. Choose the **Add Items** action.
3. In the **Shop Code** field, enter the code. If you open the **Shopify Product** window from the **Shop Card** page, the shop code will be populated automatically.
4. If you configured image and inventory sync, you can include them in the same process. Including them in the same process is convenient for demo scenarios or when dealing with smaller amounts of data.
5. Define filters on items as required. For example, you can filter by the item number or item category code.
6. Choose **OK**.

The resulting items are automatically created in Shopify with prices. Depending on choices you made, images and inventory levels might be included. The operation might take some time if a large number of items are added.

Alternatively, you can sync one item by choosing the **Add to Shopify** action in the **Item Card** page.  

> [!NOTE]  
> Initial sync of items from [!INCLUDE[prod_short](../includes/prod_short.md)] to Shopify doesn't consider **Sync Item** and **Can Update Shopify Products** settings. 

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

* **Blank**: Nothing will happen. If necessary, you'll need to perform the required action from the **Shopify admin**.
* **Status to Draft**: The status of the product in Shopify is set to *Draft*.
* **Status to Archived**: The product is archived in Shopify.

## Sync item images

Synchronization of images can be configured for synchronized items. Choose from the following options:

* **Disabled**: Image synchronization is deactivated.
* **To Shopify**: Pictures of items are exported to Shopify.
* **From Shopify**: Images from Shopify are imported to [!INCLUDE[prod_short](../includes/prod_short.md)].

Image synchronization can be initialized in the two ways described below.

### Sync product images from the Shopify shop page

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and choose the related link.
2. Select the shop for which you want to synchronize images to open the **Shopify Shop Card** page.
3. Choose the **Sync Product Images** action.

### Sync product images from the Shopify products page

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and choose the related link.
2. Choose the **Sync Product Images** action.

### Image synchronization remarks

* When you export images from [!INCLUDE[prod_short](../includes/prod_short.md)] to Shopify, the images replace those you exported previously. The earlier images are no longer available.
* If you delete an image in [!INCLUDE[prod_short](../includes/prod_short.md)], the image in Shopify isn't also deleted. You'll need to manually delete the old images in the **Shopify Admin**.
* Images you export to Shopify must comply with Shopify's requirements. Otherwise, you can't import them. To learn more about media requirements, go to [product media types on help.shopify.com](https://help.shopify.com/en/manual/products/product-media/product-media-types#images).

## Sync prices with Shopify

You manage the process of exporting prices using these settings:

|Field|Description|
|------|-----------|
|**Customer Price Group**|Determine the price for an item in Shopify. The sales price of this customer price group is taken. If no group is specified, the price on the item card is used.|
|**Customer Discount Group**|Determine the discount to use when calculating the price of an item in Shopify. Discounted prices are stored in the **Price** field and the full price is stored in the **Compare at Price** field.|
|**Allow Line Disc.**|Specifies whether you allow a line discount when calculating prices for Shopify. This setting applies only for prices on the item. Prices for the customer price group have their own toggle on lines.|
|**Prices including VAT**|Specifies whether price calculations for Shopify include VAT. Learn more at [Set up Taxes](setup-taxes.md).|
|**VAT Business Posting Group**|Specifies which VAT business posting group is used to calculate prices in Shopify. This should be the group you use for domestic customers. Learn more at [Set up Taxes](setup-taxes.md).|
|**Currency Code**|Enter a currency code only if your online shop uses a different currency than the local currency (LCY). The specified currency must have exchange rates configured. If your online shop uses the same currency as [!INCLUDE[prod_short](../includes/prod_short.md)], leave the field empty.|

You can export prices for synchronized items in the two ways described below.

### Sync prices from the Shopify products page

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and choose the related link.
2. Choose the **Sync Prices to Shopify** action.

### Price calculation remarks

* When determining a price, [!INCLUDE[prod_short](../includes/prod_short.md)] uses the "lowest price" logic. However, the lowest price logic ignores the unit price defined on the item card if a price is defined in the price group. This is true even if the unit price from the item card price is lower.
* To calculate prices, the connector creates a temporary sales quote for the item with a quantity of 1, and uses standard price calculation logic. Only prices and discounts that are applicable for quantity 1 are used. You can't export different prices or discounts based on quantity.
* The connector sends a request to update prices in Shopify if the price in [!INCLUDE[prod_short](../includes/prod_short.md)] has changed. For example, if you synchronized products and prices and then changed a price in Shopify, choosing the **Sync Prices to Shopify** action won't have any impact on the price in the Shopify because the new price calculated by the connector is the same as the price stored in the Shopify Variant from the previous sync. The **Compare at Price** is updated only if the main price has changed.

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
6. Select the stock calculation method to use for the selected Shopify locations.
7. Enable **Default Product Location** if you want location to be used for creation of inventory records and to participate in the inventory synchronization.

You can initialize inventory synchronization in the two ways described below.

### Sync inventory from the Shopify shop page

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and choose the related link.
2. Select the shop for which you want to synchronize inventory to open the **Shopify Shop Card** page.
3. Choose the **Sync inventory** action.

### Sync inventory from the Shopify products page

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and choose the related link.
2. Choose the **Sync inventory** action.

### Inventory remarks

* There are two standard stock calculation methods: **Projected Available Balance at date** and **Free Inventory (Not reserved)**. With extensibility, you can add more options. To learn more about extensibility, go to [examples](/dynamics365/business-central/dev-itpro/developer/devenv-extending-shopify#stock-calculation). 
* You can inspect the stock information received from Shopify on the **Shopify Inventory FactBox** page. In this FactBox, you get an overview of the Shopify stock and the last calculated inventory in [!INCLUDE[prod_short](../includes/prod_short.md)]. There's one record per location.
* If the stock information in Shopify is different than the **Projected Available Balance** in [!INCLUDE[prod_short](../includes/prod_short.md)], then the stock will be updated in Shopify.
* When you add a new location in Shopify, you also need to add inventory records for it. Shopify doesn't do that automatically for existing products and variants and the connector won't synchronize inventory levels for such items in the new location. To learn more, go to [Assigning inventory to locations](https://help.shopify.com/manual/locations/assigning-inventory-to-locations).
* Both **Business Central Fulfillment Services** and normal locations are supported and can be used for shipping and inventory.

#### Example of calculation of projected available balance

There are 10 pieces of item A available on hand and two outstanding sales orders. One for Monday with quantity *One* and one for Thursday with quantity *Two*. Depending on when you sync inventory, the system will update the stock level in Shopify with different quantities:

|When sync inventory is run|Value used to update stock level|Comment|
|------|-----------------|-----------------|
|Tuesday|9|Inventory 10 minus sales order set to ship on Monday|
|Friday|7|Inventory 10 minus both sales orders|

####  Example of calculation of free inventory (not reserved)

There are 10 pieces of item A available on hand and three outstanding sales orders. One order with quantity *1* reserved from item ledger entry, one with quantity *2* not reserved, and one with quantity *3* reserved from a purchase order. For this method, the date of synchronization isn't important.

|Value used to update stock level|Comment|
|-----------------|-----------------|
|9|Inventory 10 minus the sales order with reserved inventory from item ledger entry. Other sales orders are ignored.|

### Two approaches to manage fulfillments

There are two ways to deal with fulfillment in Shopify:

* Shopify "built-in" fulfillment and inventory tracking
* Third-party fulfillment and inventory tracking

Inventory for each product in Shopify can be either stocked by Shopify or by 3PL.

If you use Shopify fulfillment, then you can also define multiple locations in Shopify. Once order is created, Shopify selects location based on availability and priority. You can also specify on which location(s) you plan to track specific product, for example never sell from location *ShowRoom*.

If you use 3PL physical handling is taken care of by 3PL provider, so locations are not needed. For 3PL the SKU field becoming mandatory.

When you decide on which location to track item, Shopify creates records in the **Inventory Levels** table, which can be updated manually with inventory availability.

The connector supports both modes. It can send inventory to multiple Shopify locations or work as a fulfillment service.

From the [!INCLUDE[prod_short](../includes/prod_short.md)] perspective, when you create item and want to send it to Shopify you also want to:

* Use **Default Product Location** toggle to specify if this item will be fulfilled by Shopify fulfillment or by 3PL. There is always **Business Central Fulfillment Service**, but there can be more fulfillments services if more apps are installed. You can enable **Default Product Location** only in one record if you want to use fulfillment service. 
* use **Default Product Location** toggle to specify which locations you want to use to track inventory. You can turn on **Default Product Location** for multiple locations where **Is Fulfillment Service** is disabled. Notice that inventory will be always tracked for primary location.

#### What's the difference?

Shopify fulfillment is useful when using Shopify POS and there are multiple physical stores. You want employees in the physical store to know their current inventory. In this case, you create multiple locations in Shopify, multiple locations in [!INCLUDE[prod_short](../includes/prod_short.md)], and activate a **Default Product Location** for all these locations.  

If logistics is handled in [!INCLUDE[prod_short](../includes/prod_short.md)], where it can have as many locations as needed representing distribution centers, you don't create locations in Shopify, the connector creates Business Central Fulfillment Services automatically and you can link inventory via location filters from several locations to one fulfillment services record. As a result, in Shopify there's no information about where goods are sent from—it only has tracking information, while in [!INCLUDE[prod_short](../includes/prod_short.md)], you can select based on availability and proximity to the destination.

#### Example of using Default Product Location toggle

After you choose the **Get Shopify Locations** action in the **Shopify Locations** page, you see the following locations:

|Name|Is Fulfillment Service|Is Primary|
|------|-----------------|-----------------|
|Main| |**Yes**|
|Second| | |
|Business Central Fulfillment Service|**Yes**| |

Let's review the impact of enabling the Default Product Location toggle:

|Name of locations where Default Product Location toggle is turned on|Impact on how product is created in Shopify|
|------|-----------------|
|Main| Inventory will be stocked at: Multiple locations; Selected locations: Main (primary) |
|Main and Second| Inventory will be stocked at: Multiple locations; Selected locations: Main and Second |
|Business Central Fulfillment Service|Inventory will be stocked at: Business Central Fulfillment Service; Selected locations: (App) Business Central Fulfillment Service|
|Business Central Fulfillment Service and Main| Error: You can't use standard Shopify Locations with FulFillment Service Locations|

## See also

[Get Started with the Connector for Shopify](get-started.md)  
