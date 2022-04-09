---
title: 
description: 
ms.date: 03/21/2022
ms.topic: article
ms.service: dynamics365-business-central
author: AndreiPanko
ms.author: andreipa
manager: 
---

# Synchronize items and inventory 

Items in [!INCLUDE[prod_short](../includes/prod_short.md)] corresponds to Products in Shopify, which include physical goods, digital downloads, services, and gift cards that you sell. 
There are two main purposes of syncronization of items:
1. When master-data management is performed in [!INCLUDE[prod_short](../includes/prod_short.md)], and you need to all or some export data to Shopify and make it visible. You can export item name, description, image, prices, availability, variants, vendor details, barcodes, which can become immidiatelly visible or first reviewed and enchanced by responsible person. 
2. When importing order from Shopify, the information about items are essential for further processing of document in [!INCLUDE[prod_short](../includes/prod_short.md)].

These two scenarios are always enabled. 

3. Additional scenario is when master-data management is performed in Shopify and you want to import those items in bulk to [!INCLUDE[prod_short](../includes/prod_short.md)]. This can be useful for data-migration scenarios, when existing online shop connected to new [!INCLUDE[prod_short](../includes/prod_short.md)].


## To define item synchronizations

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**. Open a shop for which you want to configure item synchronization.
2. Fill in the **Sync item**, the following table outlines the difference between the options.

|Option|Description|
|------|-----------|
|**Blank**|Products will be imported together with import of orders. Products will be exported to Shopify if user runs **Add Item** action from the **Shopify Products** window. This is default behavior. |
|**To Shopify**| Select if after initial sync triggered by **Add Item** action, you plan to update products manually using **Sync Product** action or via job queue for reccuring updates. Other than that it equals to **Blank** option. For initial sync you must use **Add Item** action from the **Shopify Products** window. Remember to enable **Can Update Shopify Product** field.|
|**From Shopify**|Select if you plan import products from Shopify in bulk either manually using **Sync Product** action or via job queue for reccuring updates. Other than that it equals to **Blank** option.|

## Import items from Shopify
Either you import items from Shopify in bulk or together with import of orders, these items first will be added to Shopify Product and Shopify Variant tables. Following settings let you manage the process:
|Field|Description|
|------|-----------|
|**Auto create unknown items**|When shopify products and variants are imported to [!INCLUDE[prod_short](../includes/prod_short.md)], system always tries to find matching record in the item list first. Enable this option if you want to create new item and/or for records where system didn't find the matching record. New item will be created using imported data and **Item Template Code**. **SKU Type** impacts how system performs matching and creates new Item and/or Item Variant. For more information, see [Product Mapping](synchronize-items.md#)||
|**Item Template Code**|Used together with **Auto create unknown items**.<br> Choose template to be used for automatically created items.|
|**SKU Type**|Choose how you want to use **SKU** value imported from Shopify during item/variant mapping and creation. For more information, see [How SKU and Barcode defined in Shopify product impact mapping and creation of items and variants](synchronize-items.md#how-sku-and-barcode-defined-in-shopify-product-impact-mapping-and-creation-of-items-and-variants-in-includeprod_short)|
|**SKU Field Separator**|Used together with **SKU Type** set to **Item. No + Variant Code** option.<br> Define a separator that system should use to split SKU. <br>For example: if in Shopify you create the variant with SKU '1000/001', set fill */* into the **SKU Field Separator** to get the item number in [!INCLUDE[prod_short](../includes/prod_short.md)] as '1000' and the variant code as '001'.
|**Variant Prefix**|Used together with **SKU Type** set to **Variant Code** or **Item. No + Variant Code** options as fallback strategy when SKU is not defined.<br>
Shopify lets user to define variants of product that comes in more than one option, such as size or color. If you want system to create Item Variant in [!INCLUDE[prod_short](../includes/prod_short.md)], you will need to fill in **Code**. By default system will use value defined in the SKU field imported from Shopify. However if SKU is empty, it will generate code using defined prefix and "001".|
|**Shopify Can Update Item**|Select if you want system automatically update items and/or variants. |


### How SKU and Barcode defined in Shopify product impact mapping and creation of items and variants in [!INCLUDE[prod_short](../includes/prod_short.md)]
When products are imported from Shopify to **Shopify Products** and **Shopify Variants** tables, system tries to find existing records. The following table outlines the difference between the options in the **SKU Type** field.

|Option|Impact on mapping|Impact on creation|
|------|-----------------|------------------|
|**Blank**|SKU field is not used in item mapping routine.|No impact on creation of item. <br>Prevents creation of variants. This can be useful if you want to use in sales order only main item. You still will be able to map variant manually from **Shopify Product** window.|
|**Item No.**|Select if SKU field contains item no.|No impact on creation of item without variants. For item with variants, each variant will be created as separate item. Neither item variants nor main item will be created.<br> For example: iif in Shopify you create two variants with SKUs '1000' and '2000', in [!INCLUDE[prod_short](../includes/prod_short.md)] system will create two items with numbers '1000' and '2000'.|
|**Variant Code**|SKU field is not used in item mapping routine.|No impact on creation of item. When creating item variant system will use value of SKU field as Code. If SKU is empty, then system will generate code using **Variant Prefix** field.|
|**Item No. + Variant Code**| Select if SKU field contains item no. and item variant code separated by value defined in the **SKU Field Separator** field.|When creating item system will use value of SKU field as No.. If SKU is empty, then system will generate item no using Number series defiend in the ITem Template Code or **Item Nos.** from the **Inventory Setup** window.<br>When creating item variant system will use value of SKU field as Code. If SKU is empty, then system will generate code using **Variant Prefix** field.|
|**Vendor Item No.**| Select if SKU field contains vendor item no. Note that system will not use **Item Vendor No.** in the **Item card** window, but **Vendor Item No.** from the **Item Vendor Catalog**. If founded Item Vendor Catalor record contains variant code, this variant code will be used by system to map Shopify variant.|No impact on creation of item. <br>Prevents creation of variants. This can be useful if you want to use in sales order only main item. You still will be able to map variant manually from **Shopify Product** window.|
|**Barcode**| Select if SKU field contains barcode. System will perform search among **Item References** of type Vendor. If founded Item Reference record contains variant code, this variant code will be used by system to map Shopify variant.|No impact on creation of item. <br>Prevents creation of variants. This can be useful if you want to use in sales order only main item. You still will be able to map variant manually from **Shopify Product** window.|

The following table outlines the impact of **Barcode** field.
|Impact on mapping|Impact on creation|
|-----------------|------------------|
|System will perform search among **Item References** of type Barcode for value defined in the Barcode field in Shopify. If founded Item Reference record contains variant code, this variant code will be used by system to map Shopify variant.|Barcode is saved as **Item Reference** for item and/or item variant|

# WIP

## Export items to Shopify


On the tab 'Item Synchronization' of the Shopify Shop Card, you can enter to sync the items from Shopify.

![Graphical user interface  application Description automatically generated](media/image45.png)



## Sync item images
You can configur synchronization of images differently

- **Sync item images**  
    Sync your items 'From Shopify'

    1.  ### Setup to sync variants

On the tab 'Synchronization' of the Shopify Shop Card, you can indicate if and how you want to synchronize variants and stockkeeping units from Shopify to Dynamics 365 Business Central.

![Graphical user interface  text  application  email Description automatically generated](media/image46.png)

- **Variant Prefix**  
    The variants you have defined in Shopify are created in Business Central based on an increasing number. You can choose a prefix for the variants.

![](media/image47.png)


## Setup locations

In Shopify you can define more than one location via 'Settings' &gt; 'Locations'.

![](media/image48.png)

These locations need to be available in Microsoft Dynamics 365 Business Central.

On the Shopify Shop Card: Process &gt; Locations

![](media/image49.png)

Use the function 'Get Shopify Locations' to get the locations from Shopify.

![](media/image35.png)

The locations appear in Business Central. Link the Shopify location with the location in Business Central.

-   Table filter: determines the location(s) for which the stock must be counted.

-   Default location: determines the location to be used in the orders.

![](media/image36.png)

Uncheck 'Disable' if you want to sync the inventory for this location to Business Central.

## Setup to automatically create unknown items

On the tab 'Item Synchronization' of the Shopify Shop Card, you can indicate to automatically create unknown items from Shopify into Dynamics 365 Business Central based on an item template.

![](media/image50.png)

## Execute Item Synchronization

On the Products page, you can synchronize items from Shopify to Business Central via the function 'Sync Products'.

![](media/image51.png)

![Graphical user interface  table Description automatically generated](media/image52.png)

## Sync product images

When you navigate to 'Products' on you Shopify Shop Card, you can execute the function 'Sync Product Images' to synchronize the items in Business Central.

![Graphical user interface  application Description automatically generated](media/image53.png)

## Inventory Synchronization

The inventory of Shopify goes to Business Central. If there is a difference with the calculated inventory in Business Central, the inventory is updated in Shopify.


