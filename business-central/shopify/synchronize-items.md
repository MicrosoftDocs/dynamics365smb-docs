---
title: Synchronize items and inventory
description: Set up and run synchronizations of items between Shopify and Business Central.
ms.date: 07/14/2025
ms.topic: how-to
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

A third scenario is to manage data in Shopify but import those items in bulk to [!INCLUDE[prod_short](../includes/prod_short.md)]. This scenario can be useful for data migration events, such as when you want to connect an existing online shop with a new [!INCLUDE[prod_short](../includes/prod_short.md)] environment. The connector always creates or updates product variants in bulk.

## Define item synchronizations

1. Choose the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon and enter **Shopify Shop**. Open the shop for which you want to configure the item synchronization.
2. From the **Sync item** field, select the required option.

   The following table outlines the options.

   |Option|Description|
   |------|-----------|
   |**Blank**| Products are imported together with the importing of orders. Products are exported to Shopify if a user runs the **Add Item** action from the **Shopify Products** page. This option is the default process.|
   |**To Shopify**| Select this option if, after the initial sync is triggered by the **Add Item** action, you plan to update products manually using the **Sync Product** action or using the job queue for recurring updates. Remember to enable the **Can Update Shopify Product** field. If it isn't enabled, it equals the **Blank** (default process) option. Learn more in the [Export items to Shopify](synchronize-items.md#export-items-to-shopify) section.|
   |**From Shopify**| Choose this option if you plan to import products from Shopify in bulk, either manually using the **Sync Product** action or using the job queue for recurring updates. To learn more, go to [Import items from Shopify](synchronize-items.md#import-items-from-shopify).|

   > [!NOTE]
   > Changing **Sync Item** from **From Shopify** to **To Shopify** won't have an effect unless you enable **Can Update Shopify Products**.

## Overview of ways to manage product information in both apps

Shopify and [!INCLUDE [prod_short](../includes/prod_short.md)] both offer extensive features for managing products and variants. Depending on your needs, you can choose different options. In Shopify, where you focus on convenience for customers, and in [!INCLUDE [prod_short](../includes/prod_short.md)], where other criteria is taken into consideration, such as the ability to define an assembly BOM.

|Product Information  |Business Central: Flat item list.<br><br>Only items, no variants  |Business Central: Items with item variants  |
|---------|---------|---------|
|Shopify: Flat product list.</br>Only products, no variants.     | Supported<br><br>Import into [!INCLUDE [prod_short](../includes/prod_short.md)]<br><br>To point to an item in [!INCLUDE [prod_short](../includes/prod_short.md)], use the barcode or SKU fields on the Shopify product.<br><br>Export items from [!INCLUDE [prod_short](../includes/prod_short.md)] by using the **Add Item to Shopify** action.| Not supported<br><br>You can manually create products/items in both system independently, and use the barcode or SKU for automatic mapping or map products to item variants manually.|
|Shopify: Products with variants| Supported<br><br>We recommend that you select **Item No.**, **Vendor Item No.**, or **Barcode** in the **SKU Mapping** field and add the barcode or SKU on the variant to ensure that when a product/variant is imported from Shopify it finds the corresponding item in [!INCLUDE [prod_short](../includes/prod_short.md)].<br><br>Export from [!INCLUDE [prod_short](../includes/prod_short.md)] by using the **Add Items as Shopify Variants** action.| Supported<br><br>We recommend that you select **Item No.+Variant Code** in the **SKU Mapping** field and add the barcode or SKU on the variant to ensure that when you import the product or variant from Shopify it finds the corresponding item or variant in [!INCLUDE [prod_short](../includes/prod_short.md)].<br><br>Export from [!INCLUDE [prod_short](../includes/prod_short.md)] by using the **Add Item to Shopify** action.|

To learn more, go to [Effect of Shopify product SKUs and barcodes on mapping and creating item variants in Business Central](/dynamics365/business-central/shopify/synchronize-items#effect-of-shopify-product-skus-and-barcodes-on-mapping-and-creating-items-and-variants-in-business-central).

## Import items from Shopify

First, import items either in bulk from Shopify or together with orders to add them to the **Shopify Product** and **Shopify Variant** tables. Then, map imported products and variants to items and variants in [!INCLUDE[prod_short](../includes/prod_short.md)]. The connector always creates or updates product variants in bulk. Manage the process using the following settings:

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
* Use the **Add Item as Shopify Variants** action on the **Shopify Products** page.
* Run item synchronization once or repeatedly with automation.

No matter how you export items, specific item information is transferred to the Shopify products list depending on your choice of settings for item synchronization.

Before it exports an item to Shopify, the connector checks whether an item already exists. First, it checks whether there's a product or variant with a barcode, because it's defined in the **Item References** entry of a barcode type. If the **SKU Mapping** field is filled in, the connector checks whether there's a product or variant with a SKU. To learn more, go to [Effect of Shopify product SKUs and barcodes on mapping and creating items and variants in Business Central](synchronize-items.md#effect-of-shopify-product-skus-and-barcodes-on-mapping-and-creating-items-and-variants-in-business-central).

You manage the process of exporting items using these settings:

|Field|Description|
|------|-----------|
|**Sync Item Extended Text**|Select this field to sync the extended text of the item. Because it's added to the **Description** field, it can contain HTML code. |
|**Sync Item Attributes**|Select this field to sync the item attributes. Attributes are formatted as a table and included in the **Description** field in Shopify.|
|**Sync Item Marketing Text**|Select this field to sync marketing text for the item. Although marketing text is a kind of description, it's different from an item's **Description** field. The **Description** field is typically used as a concise display name to quickly identify the product. The marketing text, on the other hand, is more rich and descriptive. Its purpose is to add marketing and promotional content. This text can then be published with the item in Shopify. There are two ways to create the marketing text. Use Copilot, which suggests AI-generated text for you, or start from scratch.|
|**Language Code**|Select this field if you want the translated versions used for title, attributes, and extended text. You can also export additional translations. To learn more, go to [Sync product translations to Shopify](synchronize-items.md#sync-product-translations-to-shopify).|
|**SKU Mapping**|Choose how you want to populate the SKU field in Shopify. Supported options are:</br> - **Item No.** to use the item number for both products and variants.</br> - **Item No.+ Variant Code** to create an SKU by concatenating values of two fields. For items without variants, the item number only is used.</br>- **Item Vendor No.** to use the item vendor number defined in the **Item Card** for both products and variants.</br> - **Barcode** to use the barcode type of **Item Reference**. This option respects variants.</br>If **Can Update Shopify Products** is enabled, changes in the **SKU Mapping** field will be propagated to Shopify after the next sync for all products and variants listed in the **Shopify Products** page for the selected shop.|
|**SKU Field Separator**|Define a separator for the **Item. No + Variant Code** option.|
|**Inventory Tracked**| Choose how the system should populate the **Track Inventory** field for products exported to Shopify. You can update availability information from [!INCLUDE[prod_short](../includes/prod_short.md)] for products in Shopify whose track inventory is enabled. Learn more in the [Inventory](synchronize-items.md#sync-inventory-to-shopify) section.|
|**Default Inventory Policy**|Choose *Deny* to prevent negative stock on the Shopify side. </br>If **Can Update Shopify Products** is enabled, changes in the **Default Inventory Policy** field will be propagated to Shopify after next sync for all products and variants listed in the **Shopify Products** page for selected shop.|
|**Can Update Shopify Products**|Define this field if [!INCLUDE[prod_short](../includes/prod_short.md)] can only create items or can update items as well. Select this option if, after the initial sync is triggered by the **Add Item** action, you plan to update products manually using the **Sync Product** action or using the job queue for recurring updates. Remember to select **To Shopify** in the **Item Sync** field.</br>**Can Update Shopify Products** doesn't impact synchronization of prices, images, or inventory levels, which are configured by independent controls.</br>If **Can Update Shopify Products** is enabled, the following fields on the Shopify side are updated on the product and, if needed, the variant level: **SKU**, **Barcode**, **Weight**. The **Title**, **Product Type**, **Vendor**, and **Description** on the product are also updated if the exported values aren't empty. For description, this means you need to enable any of the **Sync Item Extended Text**, **Sync Item Marketing Text**, and **Sync Item Attributes** toggles and  attributes, extended or marketing text must have values. If the product uses variants, then the variant is added or removed if necessary. </br>If the product on Shopify is configured to use a variant matrix that combines two or more options, the Shopify Connector can't create a variant for that product. In [!INCLUDE[prod_short](../includes/prod_short.md)], you can't define an option matrix, so the connector uses the **Variant Code** as the only option. However, Shopify expects several options and refuses to create a variant if information about other options is missing. |
|**UoM as Variant**| Choose this option if you want some options to be exported as imported as units of measure instead of variants. Personalize the page to add the field. Learn more in the [Unit of Measure as Variant](synchronize-items.md#unit-of-measure-as-variant) section.|
|**Variant Option Name for UoM**| Use this field with **UoM as Variant** to specify which option contains variants that represent units of measure. The default value is **Unit of Measure**. To add the field, personalize the page.|
|**Weight Unit**|When you enable the connector, it imports the default weight unit of measure from Shopify and uses it when it sends the weight of the product. You can change whether the **Net weight** field in [!INCLUDE [prod_short](../includes/prod_short.md)] stores values with different unit of measure.|

> [!NOTE]
> When you want to export many items and variants, some might be blocked. You can't include blocked items and variants in price calculations, so they aren't exported. The Connector skips those items and variants, so you don't need to filter them on the **Add Item to Shopify** request page.

### Activate sales channels

When you sync products from [!INCLUDE [prod_short](../includes/prod_short.md)] to Shopify, you can choose which sales channels to activate directly from the **Shopify Sales Channels** page. The **Shopify Sales Channels** page shows all available channels in Shopify. Just activate the ones you want, and the Shopify Connector handles the rest. If you haven't set up this page yet, don't worry. Your products default to the Online Store.

### Sync product translations to Shopify

Automatically synchronizing translations from [!INCLUDE [prod_short](../includes/prod_short.md)] to Shopify guarantees consistent product descriptions and details across various languages. Offering customers product information in their native language enhances accessibility and satisfaction, which can boost conversion rates and foster customer loyalty.

To include translations to the product synchronization, follow these steps:

1. Choose the **Tell Me**  icon, enter **Shopify shops**, and choose the related link.
2. Select the shop to open the **Shopify Shop Card** page.
3. To open the **Shopify Languages** page, choose the **Languages** action.
4. To import languages enabled on Shopify, choose the **Refresh** action. Notice that the primary language isn't be listed. For the primary language, continue to use the **Language Code** field in the **Shopify Shop Card**.
5. For each language to include in synchronization, fill in the **Language Code** field and turn on the **Sync translations** toggle.

> [!NOTE]
>
> * Marketing text is only added for the primary language.
> * Extended texts are added for each language, plus extended texts where the **All Languages** toggle is turned on.
> * Attributes are added for each language. If a translation is missing, the primary language is used.
> * Item translations are added for each language if a translation is defined.
> * Variant translations aren't used because the connector only exports the variant code, and not its description.

## Advanced details

### Effect of Shopify product SKUs and barcodes on mapping and creating items and variants in Business Central

When products are imported from Shopify to **Shopify Products** and **Shopify Variants** tables, [!INCLUDE[prod_short](../includes/prod_short.md)] tries to find existing records.

The following table outlines the differences between options in the **SKU Mapping** field.

|Option|Effect on mapping|Effect on creation|
|------|-----------------|------------------|
|**Blank**|The SKU field isn't used in the item-mapping routine.|No effect on the creation of the item.</br>This option prevents the creation of variants. When in a sales order, only the main item is used. A variant can still be mapped manually on the **Shopify Product** page.|
|**Item No.**|Choose if the SKU field contains the item number.|No effect on the creation of an item without variants. For an item with variants, each variant is created as a separate item.</br>If Shopify has a product with two variants and their SKUs are '1000' and '2000', [!INCLUDE[prod_short](../includes/prod_short.md)] creates two items numbered '1000' and '2000'.|
|**Variant Code**|The SKU field isn't used in the item-mapping routine.|No effect on creation of the item. When an item variant is created, the value of the SKU field is used as a code. If the SKU is empty, a code is generated using the **Variant Prefix** field.|
|**Item No. + Variant Code**|Select this option if the SKU field contains an item number and the item variant code is separated by the value defined in the **SKU Field Separator** field.|When an item is created, the first part of the value of the SKU field is designated **No.**. If the SKU field is empty, an item number is generated using the number series defined in the **Item Template Code** or **Item Nos.** field of the **Inventory Setup** page.</br>When an item is created, the variant function uses the second part of the value of the SKU field as **Code**. If the SKU field is empty, a code is generated using the **Variant Prefix** field.|
|**Vendor Item No.**|Choose if the SKU field contains the vendor item number. In this case, the **Item Vendor No.** isn't used on the **Item Card** page; rather the **Vendor Item No.** from the **Item Vendor Catalog** is used. If the *Item Vendor Catalog* record contains a variant code, that code is used to map the Shopify variant.|If a corresponding vendor exists in [!INCLUDE[prod_short](../includes/prod_short.md)], the SKU value is used as the **Vendor Item No.** on the **Item Card** page and as the **Item Reference** of the *vendor* type. </br>Prevents the creation of variants. It's useful when you want to use only the main item in the sales order. You're still able to map a variant manually from the **Shopify Product** page.|
|**Barcode**|Choose if the SKU field contains a barcode. A search is performed among **Item References** of the *barcode* type. If the item reference record contains a variant code, that variant code is used to map the Shopify variant.|No effect on the creation of the item. </br>Prevents the creation of variants. It's useful when you want to use only the main item in the sales order. You're still able to map a variant manually from the **Shopify Product** page.|

The following table outlines the effects of the **Barcode** field.

|Effect on mapping|Effect on creation|
|-----------------|------------------|
|A search is performed on the **Item References** containing a barcode type as the value in the **Barcode** field in Shopify. If the item reference record contains a variant code, that variant code is used to map the Shopify variant.|The barcode is saved as **Item Reference** for the item and item variant.|

> [!NOTE]  
> You can trigger mapping for the selected products/variants by choosing **Try Find Product Mapping** or for all the imported unmapped products by choosing **Try Find Mappings**.

### Fields-mapping overview

|Shopify|Source when exported from [!INCLUDE[prod_short](../includes/prod_short.md)]|Target when imported to [!INCLUDE[prod_short](../includes/prod_short.md)]|
|------|-----------------|-----------------|
|Status|According to the **Status for Created Products** field in the **Shopify Shop Card**. Learn more in the [Ad hoc updates of Shopify products](synchronize-items.md#ad-hoc-updates-of-shopify-products) section.|Not used.|
|Title | **Description**. If the language code is defined and a corresponding item translation exists, the item translation is used instead of the description.|**Description**|
|Variant title | **Variant Code**.</br>The reason to use **Code** and not **Description** is because Shopify requires unique variant titles per product. In [!INCLUDE[prod_short](../includes/prod_short.md)] the **Code** is unique, while **Description** isn't. Descriptions that aren't unique cause issues during product export.|**Description** of variant|
|Description|Combines extended texts, marketing text, and attributes if you enable the corresponding toggles on the Shopify shop card. Respects the language code.|Not used.|
|SEO page title|Fixed value: empty. Learn more in the [Ad hoc updates of Shopify products](synchronize-items.md#ad-hoc-updates-of-shopify-products) section.|Not used.|
|SEO meta description|Fixed value: empty. Learn more in the [Ad hoc updates of Shopify products](synchronize-items.md#ad-hoc-updates-of-shopify-products) section.|Not used.|
|Media|**Image**. Learn more in the [Sync item images](synchronize-items.md#sync-item-images) section|**Image**|
|Price|The calculation of the end-customer price includes the item unit price, customer price group, customer discount group, and currency code. Learn more in the [Sync prices](synchronize-items.md#sync-prices-with-shopify) section|**Unit Price**. The price is only imported to newly created items and doesn't update in later synchronizations.|
|Compare at price|The calculation of the price without a discount. If the value is less than or equal to **Price**, the connector sends 0 (null) instead of the actual value.|Not used.|
|Cost per item|**Unit Cost**|**Unit Cost**. The unit cost is only imported to newly created items and doesn't update in later synchronizations.|
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

### Import and export product information using Shopify Metafields

Shopify's platform includes data models for fundamental commerce concepts. However, commerce is diverse and often requires more complex or specific data models. The custom data platform enables you to extend Shopify's data models and create your own by using metafields. Metafields are a flexible way to add and store additional information about a Shopify resource, such as a product or variant. The additional information stored in metafields can be almost anything related to a resource. Some examples are specifications, size charts, downloadable documents, release dates, images, or part numbers.

You can import and export data stored in metafields. [!INCLUDE [prod_short](../includes/prod_short.md)]. Also, there's an extensibility model that allows developers to map standard or custom fields, attributes, or other related entries in [!INCLUDE [prod_short](../includes/prod_short.md)] to metafields in Shopify.

You can access and edit metafields on the **Shopify Metafields** page, which you open from the **Shopify Products** and **Shopify Variants** pages.

> [!NOTE]
> The page is editable if the **Product Sync** field is set to **Products to Shopify**, and the **Can update Shopify products** toggle is turned on. When you add a record, the connector immediately sends a request to Shopify and stores the entry only when it gets a response with the Shopify ID for the metafield.
> Further edits of records synchronize with Shopify during the next product synchronization.
> You can't edit types that have AssistEdit functionality defined directly on the line.

If standard metafields are defined, you can use the **Get Metafield Definitions** action to get the list from Shopify. All supported metafields are imported. You only need to update the values.

#### Supported metafield content types

> [!NOTE]
> Metafields definitions with *List of values* aren't supported.

**Date and time:**

* Date
* Date and time

**Measurements:**

* Dimension
* Volume
* Weight

**Number:**

* Decimal
* Integer

**Text:**

* Single line text
* Multi-line text

> [!NOTE]
> Rich text isn't supported.

**References:**

* Product
* Variant
* Collection
* File
* Metaobject
* Page
* Company
* Customer

**Other:**

* True or false
* Color
* URL
* Money

> [!NOTE]
> Link and Rating aren't supported.

**Advanced:**

* Mixed reference
* JSON

### Tags

Review the imported tags in the **Tags** FactBox on the **Shopify Product** page. On the same page, to edit tags, choose the **Tags** action.

If the **To Shopify** option is selected in the **Sync Item** field, assigned tags are exported to Shopify at the next synchronization.

### Unit of measure as variant

Shopify doesn't support multiple units of measure. If you want to sell the same product as, for example, piece, and set and use different prices or discounts, you must create units of measure as product variants.

You can configure the Shopify connector to export units of measure as variants, or import variants as units of measure.

To enable this capability, use the **UoM as Variant** and **Variant Option Name** fields on the **Shopify Shop Card** page. The fields are hidden by default. To add them to the page, use personalization.

> [!NOTE]
>
> * When you're dealing with a matrix of variants, for example Color and UoM, and you want to import products into [!INCLUDE[prod_short](../includes/prod_short.md)], you should set *Item No. + Variant Code* in the **SKU Mapping** field and make sure that the **SKU** field in Shopify has the same value for all units of measure and include both item numbers and variant codes.
> * [!INCLUDE[prod_short](../includes/prod_short.md)] calculates availability per item/item variant and not by unit of measure. The same availability is assigned to each variant representing the unit of measure (with respect to **Qty. per Unit of Measure**), which can lead to cases where the available quantity in Shopify isn't accurate. Example: Item that is sold in PCS and Box of six. The inventory in [!INCLUDE[prod_short](../includes/prod_short.md)] is six PCS. Item is exported to Shopify as Product with two variants. After inventory syncs, the inventory level in Shopify is six for variant PCS and one for variant Box. The buyer can explore the store and see that product is available in both options and place an order for one Box. The next buyer can see that Box isn't available, but there are still six PCS. The value will update with the next inventory sync.
> * You can't add a unit of measure option to existing products with variants (specific result depends on other settings, such as **SKU Mapping**).

### URL and Preview URL

An item added to Shopify or imported from Shopify might have the **URL** or **Preview URL** populated. The **URL** field is blank if the product isn't published to the online store—for example, because its status is draft. The **URL** is empty if the store is password protected—for example, because it's a development store. In most cases, you can use the **Preview URL** to check how the product looks when you publish it.

## Run item synchronization

Full or partial item synchronization can be performed in many different ways.

### Initial sync of items from Business Central to Shopify

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and choose the related link.
2. Choose the **Add Items** action.
3. In the **Shop Code** field, enter the code. If you open the **Shopify Product** window from the **Shop Card** page, the shop code is filled in automatically.
4. If you configured image and inventory sync, you can include them in the same process. Including them in the same process is convenient for demo scenarios or when dealing with smaller amounts of data.
5. Define filters on items as required. For example, you can filter by the item number or item category code.
6. Choose **OK**.

The resulting items are automatically created in Shopify with prices. Depending on choices you made, images and inventory levels might be included. The operation might take some time if a large number of items are added.

Alternatively, you can sync one item by choosing the **Add to Shopify** action in the **Item Card** page.  

> [!NOTE]  
> Initial sync of items from [!INCLUDE[prod_short](../includes/prod_short.md)] to Shopify doesn't consider **Sync Item** and **Can Update Shopify Products** settings. 

### Adding an item as a variant to Shopify products

If your products in Shopify have variants, but the list of items is flat on the [!INCLUDE [prod_short](../includes/prod_short.md)] side you can use the **Add item as Variant** action on the **Variants** FastTab of the **Shopify Products** page.

Shopify always creates a variant for each product, even if none are explicitly defined. This default variant is labeled *Default Title*. When you add additional variants through **Shopify Admin**, this technical default entry is automatically removed.

However, the Shopify connector follows slightly different logic. When the first item is added to Shopify as a product, the Default Title variant is created both in Shopify and in [!INCLUDE [prod_short](../includes/prod_short.md)]. Later, when you use the **Add Item as Shopify Variants** action, the selected item is added as a new variant. The original Default Title variant is retained to represent the original item and includes its SKU, barcode, and price. As a result, a product that initially had no variants becomes a product with two:

 - One variant reflects the characteristics of the original product.
 - The second variant inherits details from the newly added item.

If you add item as a variant to product that already has options/variants defined, then items are added as Shopify variants under the existing product option. For example, color, material, or title, if the product only had one default variant. If the Shopify product has more than one option, you can't add the item as a Shopify variant.

> [!NOTE]
> You can add item as variants if it has its own item variants, however, only the item itself is added, and not item variants.
>
> You can't add an item as a variant if the **UOM as Variant** toggle is turned on on the **Shopify Shop Card** page.
>
> When it adds an item as a variant, the connector doesn’t search by SKU or barcode.

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

Based on the value in **Action for Removed Products and Blocked Items** on the **Shopify Shop Card** page, the product gets updated in Shopify when the record is deleted from the **Shopify Products** page.

* **Blank**: Nothing happens. If needed, perform the required action from the **Shopify admin**.
* **Status to Draft**: The status of the product in Shopify is set to *Draft*.
* **Status to Archived**: The product is archived in Shopify.

## Sync item images

Synchronization of images can be configured for synchronized items. Choose from the following options:

* **Disabled** - Image synchronization is deactivated.
* **To Shopify** - Images of items are exported to Shopify.
* **From Shopify** - Images from Shopify are imported to [!INCLUDE[prod_short](../includes/prod_short.md)].

You can start image synchronization in the ways described in the next sections in this article.

### Sync product images from the Shopify shop page

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and choose the related link.
2. Select the shop for which you want to synchronize images to open the **Shopify Shop Card** page.
3. Choose the **Sync Product Images** action.

### Sync product images from the Shopify products page

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and choose the related link.
2. Choose the **Sync Product Images** action.

> [!NOTE]
> There are a few things to note about image synchronization.
>
> * When you export images from [!INCLUDE[prod_short](../includes/prod_short.md)] to Shopify, the images replace the ones you exported previously. The earlier images are no longer available.
> * If you delete an image in [!INCLUDE[prod_short](../includes/prod_short.md)], the image in Shopify isn't also deleted. You need to manually delete the old images in the **Shopify Admin**.
> * Images you export to Shopify must comply with Shopify's requirements. Otherwise, you can't import them. To learn more about media requirements, go to [product media types on help.shopify.com](https://help.shopify.com/en/manual/products/product-media/product-media-types#images).

## Sync prices with Shopify

The Shopify Connector allows you to sync product pricing to your Shopify store. 

It can send both the main selling price (shown as **Price** in Shopify) and the original, non-discounted price (displayed as **Compare at Price**) to the Shopify Product (Shopify Variant) pages. Learn more at [Synchronize market-specific prices with Shopify](#sync-prices-to-the-shopify-products-page).

If you use Markets in Shopify, which can represent different countries/regions, B2B companies, or POS locations - you can link product catalogs to these markets and sync market-specific prices through the connector. Learn more at [Synchronize market-specific prices with Shopify](#synchronize-market-specific-prices-with-shopify).

For Shopify PLUS merchants, there is an additional option to connect catalogs to company locations, making it easier to manage B2B pricing scenarios. Learn more at [Synchronize market-specific prices with Shopify](#synchronize-market-specific-prices-with-shopify).

### Sync prices to the Shopify products page

The following table describes the settings you can use to manage the process of defining and exporting prices.

|Field|Description|
|------|-----------|
|**Customer Price Group**|Determine the price for an item in Shopify. The sales price of this customer price group is taken. If no group is specified, the price on the item card is used.|
|**Customer Discount Group**|Determine the discount to use when calculating the price of an item in Shopify. Discounted prices are stored in the **Price** field and the full price is stored in the **Compare at Price** field.|
|**Allow Line Disc.**|Specifies whether you allow a line discount when calculating prices for Shopify. This setting applies only for prices on the item. Prices for the customer price group have their own toggle on lines.|
|**Prices including VAT**|Specifies whether price calculations for Shopify include VAT. Learn more at [Set up Taxes](setup-taxes.md).|
|**VAT Business Posting Group**|Only needed if you want to include taxes into price. Here you can specify which VAT business posting group is used to calculate prices with taxes in Shopify. Use your group for domestic customers. Learn more at [Set up Taxes](setup-taxes.md).|
|**Currency Code**|Enter a currency code only if your online shop uses a different currency than the local currency (LCY). The specified currency must have exchange rates configured. If your online shop uses the same currency as [!INCLUDE[prod_short](../includes/prod_short.md)], leave the field empty.|

To export prices for synchronized items do following:

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and choose the related link.
2. Choose the **Sync Prices to Shopify** action.

> [!NOTE]
> There are a few things to note about price calculations and synchronization.
>
> * When it determines a price, [!INCLUDE[prod_short](../includes/prod_short.md)] uses the "lowest price" logic. However, the lowest price logic ignores the unit price defined on the item card if a price is defined in the price group. This is true even if the unit price from the item card price is lower.
> * To calculate prices, the connector creates a temporary sales quote for the item with a quantity of 1, and uses standard price calculation logic. Only prices and discounts that are applicable for quantity 1 are used. You can't export different prices or discounts based on quantity.
> * The connector sends a request to update prices in Shopify if the price in [!INCLUDE[prod_short](../includes/prod_short.md)] changed. For example, if you synchronized products and prices and then changed a price in Shopify, choosing the **Sync Prices to Shopify** action doesn't affect the price in the Shopify because the new price calculated by the connector is the same as the price stored in the Shopify Variant from the previous sync. 
> * If there are 100 or more prices to be updated, the connector executes update asynchronously. You can check the status of the synchronization in the **Shopify Bulk Operations** page.

### Price synchronization for B2B

[!INCLUDE [shopify-preview](../includes/shopify-preview.md)]

If you use Shopify B2B, you can configure the Connector to synchronize prices for Shopify Catalogs linked to B2B customers.

#### Synchronize B2B catalogs from the Shopify

1. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify B2B Catalogs**, and select the related link.
2. Select **Get Catalogs**.

You can only access catalogs linked to B2B companies. To learn more, go to [B2B Companies](synchronize-customers.md#b2b-companies). Note that catalogs in [!INCLUDE[prod_short](../includes/prod_short.md)] don't contain information about products. You manage catalog content in Shopify Admin.

#### Sync prices for B2B Catalog

1. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify B2B Catalogs**, and select the related link.
2. Select the entry for which to define and export prices, and then fill in the fields as necessary.

   You can use two strategies. One is the default strategy, where you can use settings similar to the ones for synchronizing the **Price** and **Compare at Price** fields for Shopify products (Shopify variant). The following table describes settings for the default strategy.

   |Field|Description|
   |------|-----------|
   |**Customer Price Group**|Determine the price for an item in Shopify. The sales price of this customer price group is taken. If no group is specified, the price on the item card is used.|
   |**Customer Discount Group**|Determine the discount to use when calculating the price of an item in Shopify. Discounted prices are stored in the **Price** field and the full price is stored in the **Compare at Price** field. |
   |**Allow Line Disc.**|Specifies whether you allow a line discount when calculating prices for Shopify. This setting applies only for prices on the item. Prices for the customer price group have their own toggle on lines.|
   |**Prices including VAT**|Specifies whether price calculations for Shopify include VAT. Learn more at [Set up Taxes](setup-taxes.md).|
   |**VAT Business Posting Group**|Only needed if you want to include taxes into price. Here you can specify which VAT business posting group is used to calculate prices with taxes in Shopify. Use your group for domestic customers. Learn more at [Set up Taxes](setup-taxes.md).|
   
   The second strategy is to use the **Customer No.** field. In this case, the connector uses the customer to calculate the price. It ignores other values defined in the Shopify Catalog entry, and uses the **Customer Price Group**, **Customer Discount Group**, and **Allow Line Discount** fields from the customer card. Use personalization to add the **Customer No.** field to the **Shopify Catalog** page.

4. After you enter the settings, turn on the **Sync Prices** toggle and choose **Sync Prices** action to start synchronizing catalog prices.

### Synchronize market-specific prices with Shopify

If you use Markets in Shopify, you can set up the connector to sync prices for Shopify catalogs that link to those markets.

#### Synchronize market catalogs from the Shopify

1. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Market Catalogs**, and select the related link.
2. Select **Get Catalogs**.

Market can represent region, POS Location or Company Location (B2B). 

#### Sync prices for Market Catalog

1. Select the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Market Catalogs**, and select the related link.
2. On the **Shopify Market Catalogs** page, select the entry where you want to define and export prices. Fill in the fields as needed. The following table describes the fields.

   |Field|Description|
   |------|-----------|
   |**Customer Price Group**|Determine the price for an item in Shopify. The sales price of this customer price group is taken. If no group is specified, the price on the item card is used.|
   |**Customer Discount Group**|Determine the discount to use when calculating the price of an item in Shopify. Discounted prices are stored in the **Price** field and the full price is stored in the **Compare at Price** field. |
   |**Allow Line Disc.**|Specifies whether you allow a line discount when calculating prices for Shopify. This setting applies only for prices on the item. Prices for the customer price group have their own toggle on lines.|
   |**Prices including VAT**|Specifies whether price calculations for Shopify include VAT. Learn more at [Set up Taxes](setup-taxes.md).|
   |**VAT Business Posting Group**|Only needed if you want to include taxes into price. Here you can specify which VAT business posting group is used to calculate prices with taxes in Shopify. Use your group for domestic customers. Learn more at [Set up Taxes](setup-taxes.md).|
   |**Currency Code**|Specifies the currency code for the catalog. The specified currency must have exchange rates configured. If catalog uses the same currency as [!INCLUDE[prod_short](../includes/prod_short.md)], the field will be empty.|

3. Enter the settings, turn on the **Sync Prices** toggle, and then select **Sync Prices** to synchronize catalog prices.

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

You can initialize inventory synchronization in the ways described in the following sections in this article.

### Sync inventory from the Shopify shop page

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and choose the related link.
2. Select the shop for which you want to synchronize inventory to open the **Shopify Shop Card** page.
3. Choose the **Sync inventory** action.

### Sync inventory from the Shopify products page

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and choose the related link.
2. Choose the **Sync inventory** action.

> [!NOTE]
> There are a few things to note about synchronizing inventory:
>
> * There are two standard stock calculation methods: **Projected Available Balance at date** and **Free Inventory (Not reserved)**. With extensibility, you can add more options. To learn more about extensibility, go to [examples](/dynamics365/business-central/dev-itpro/developer/devenv-extending-shopify#stock-calculation). 
> * If the stock information in Shopify is different than the **Projected Available Balance** in [!INCLUDE[prod_short](../includes/prod_short.md)], the stock updates in Shopify.
> * When you add a new location in Shopify, you also need to add inventory records for it. Shopify doesn't do that automatically for existing products and variants, and the connector doesn't synchronize inventory levels for such items in the new location. To learn more, go to [Assigning inventory to locations](https://help.shopify.com/manual/locations/assigning-inventory-to-locations).
> * Both **Business Central Fulfillment Services** and normal locations are supported and can be used for shipping and inventory.
> * When dealing with bundles, check whether adjusting inventory via an API is allowed for those products. For example, the **Shopify Bundles** app calculates availability of bundles based on the availability of the components and prevents updates via APIs. It's good idea to map Shopify products of the type Bundle to items of the type Non-inventory. Non-inventory and service items are excluded from the inventory synchronization.

#### Example of calculation of projected available balance

There are 10 pieces of item A available on hand and two outstanding sales orders. One for Monday with quantity *One* and one for Thursday with quantity *Two*. Depending on when you sync inventory, the stock level in Shopify updates with different quantities.

|When sync inventory is run|Value used to update stock level|Comment|
|------|-----------------|-----------------|
|Tuesday|9|Inventory 10 minus sales order set to ship on Monday|
|Friday|7|Inventory 10 minus both sales orders|

#### Example of calculation of available inventory (not reserved)

There are 10 pieces of item A available on hand and three outstanding sales orders. One order with quantity *1* reserved from item ledger entry, one with quantity *2* not reserved, and one with quantity *3* reserved from a purchase order. For this method, the date of synchronization isn't important.

|Value used to update stock level|Comment|
|-----------------|-----------------|
|9|Inventory 10 minus the sales order with reserved inventory from item ledger entry. Other sales orders are ignored.|

### Two approaches to manage fulfillments

There are two ways to deal with fulfillment in Shopify:

* Shopify "built-in" fulfillment and inventory tracking
* Third party fulfillment and inventory tracking

Inventory for each product in Shopify can be stocked by Shopify or by 3PL.

If you use Shopify fulfillment, then you can also define multiple locations in Shopify. Once order is created, Shopify selects location based on availability and priority. You can also specify the locations where you plan to track a specific product, for example never sell from location *ShowRoom*.

If you use 3PL physical handling is taken care of by 3PL provider, so locations aren't needed. For 3PL the SKU field becoming mandatory.

When you decide on which location to track item, Shopify creates records in the **Inventory Levels** table, which can be updated manually with inventory availability.

The connector supports both modes. It can send inventory to multiple Shopify locations or work as a fulfillment service.

From the [!INCLUDE[prod_short](../includes/prod_short.md)] perspective, when you create item and want to send it to Shopify you also want to:

* Use **Default Product Location** toggle to specify whether the item is fulfilled by Shopify fulfillment or by 3PL. There's always **Business Central Fulfillment Service**, but there can be more fulfillments services if more apps are installed. You can enable **Default Product Location** only in one record if you want to use a fulfillment service.
* use **Default Product Location** toggle to specify which locations you want to use to track inventory. You can turn on **Default Product Location** for multiple locations where **Is Fulfillment Service** is disabled. Note that inventory is always tracked for a primary location.

#### What's the difference?

Shopify fulfillment is useful when using Shopify POS and there are multiple physical stores. You want employees in the physical store to know their current inventory. In this case, you create multiple locations in Shopify, multiple locations in [!INCLUDE[prod_short](../includes/prod_short.md)], and activate a **Default Product Location** for all these locations.  

If you handle logistics in [!INCLUDE[prod_short](../includes/prod_short.md)], where you can have many locations, you don't create locations in Shopify. The connector creates Business Central Fulfillment Services automatically and you can link inventory via location filters from several locations to one fulfillment services record. As a result, in Shopify there's no information about where goods are sent from—it only has tracking information, while in [!INCLUDE[prod_short](../includes/prod_short.md)], you can select based on availability and proximity to the destination.

#### Example of using Default Product Location toggle

After you choose the **Get Shopify Locations** action in the **Shopify Locations** page, you see the following locations:

|Name|Is Fulfillment Service|Is Primary|
|------|-----------------|-----------------|
|Main| |**Yes**|
|Second| | |
|Business Central Fulfillment Service|**Yes**| |

Let's review the affect of enabling the **Default Product Location** toggle:

|Name of locations where Default Product Location toggle is turned on|Effect on how the product is created in Shopify|
|------|-----------------|
|Main| Inventory is stocked at: Multiple locations; Selected locations: Main (primary) |
|Main and Second| Inventory is stocked at: Multiple locations; Selected locations: Main and Second |
|Business Central Fulfillment Service|Inventory is stocked at: Business Central Fulfillment Service; Selected locations: (App) Business Central Fulfillment Service|
|Business Central Fulfillment Service and Main| Error: You can't use standard Shopify Locations with FulFillment Service Locations|

### Troubleshooting inventory synchronization

If the inventory level fails to sync with Shopify, try these checks.

1. Go to the **Shopify Shop Locations** page and verify the value chosen in the **Stock calculation** field. To learn more, go to [To enable inventory sync](synchronize-items.md#to-enable-inventory-sync).
2. In the **Shopify admin**, go to **Products** or **Variants** and check that the **Track quantity** toggle is turned on.
3. In the **Shopify admin**, go to **Products** or **Variants** and see whether all locations appear in the **Inventory** section. If a location is missing, it means the inventory level isn't defined. To learn more, go to [Assigning inventory to locations](https://help.shopify.com/manual/locations/assigning-inventory-to-locations).
4. Go to the **Shopify Products** page, locate the specific product, and ensure that the Shopify variant is linked to the item and item variant, if needed. To do that, examine the **Item No.** and **Variant No.** fields in the **Shopify Variants** part.
5. Go to the **Shopify Products** page, locate the specific product, and check the stock details in the **Shopify Inventory** FactBox. The FactBox gives an overview of the Shopify stock and the last calculated inventory in [!INCLUDE[prod_short](../includes/prod_short.md)]. It also shows when when the specific inventory level was last synchronized. There's one record per location.
6. Go to the **Shopify Log Entries** page, and check for entries with the **Has Error** enabled around the time the inventory level was synched (see previous step). To limit records, apply the **mutation inventorySetOnHandQuantities** filter to the **Request Preview** field. If such entries exist, open the **Shopify Log Entry** page and inspect the **Response Data** field. If there's a validation error on Shopify's side, the response includes the additional information in the **userErrors** section. To learn more about logging, go to [Logs](troubleshoot.md#logs).

## Related information

[Shopify Connector overview](shopify-connector-overview.md)  
[FAQ for the Shopify connector](shopify-faq.md)  
[Troubleshoot the Shopify Connector](troubleshoot.md)  
[Walkthrough: Setting Up and Using Shopify Connector](walkthrough-setting-up-and-using-shopify.md)  
