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

Items in [!INCLUDE[prod_short](../includes/prod_short.md)] corresponds to *Products in Shopify*, which include physical goods, digital downloads, services, and gift cards that you sell. 
There are two main purposes of syncronization of items:
1. When master-data management is performed in [!INCLUDE[prod_short](../includes/prod_short.md)], and you need to export all or some data to Shopify and make it visible. You can export item name, description, image, prices, availability, variants, vendor details, barcodes, which can become immidiatelly visible or first reviewed and enchanced by responsible person. 
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
Either you import items from Shopify in bulk or together with import of orders, these items first will be added to the **Shopify Product** and **Shopify Variant** tables. Following settings let you manage the process:
|Field|Description|
|------|-----------|
|**Auto create unknown items**|When shopify products and variants are imported to [!INCLUDE[prod_short](../includes/prod_short.md)], system always tries to find matching record in the item list first. Enable this option if you want to create new item and/or for records where system didn't find the matching record. New item will be created using imported data and **Item Template Code**. **SKU Type** impacts how system performs matching and creates new Item and/or Item Variant. For more information, see [Product Mapping](synchronize-items.md#)||
|**Item Template Code**|Used together with **Auto create unknown items**.<br> Choose template to be used for automatically created items.|
|**SKU Type**|Choose how you want to use **SKU** value imported from Shopify during item/variant mapping and creation. For more information, see [How SKU and Barcode defined in Shopify product impact mapping and creation of items and variants](synchronize-items.md#how-sku-and-barcode-defined-in-shopify-product-impact-mapping-and-creation-of-items-and-variants-in-includeprod_short)|
|**SKU Field Separator**|Used together with **SKU Type** set to **Item. No + Variant Code** option.<br> Define a separator that system should use to split SKU. <br>For example: if in Shopify you create the variant with SKU '1000/001', fill '/' in the **SKU Field Separator** field to get the item number in [!INCLUDE[prod_short](../includes/prod_short.md)] as '1000' and the item variant code as '001'.
|**Variant Prefix**|Used together with **SKU Type** set to **Variant Code** or **Item. No + Variant Code** options as fallback strategy when SKU coming from Shopify is empty.<br>If you want system to create Item Variant in [!INCLUDE[prod_short](../includes/prod_short.md)], you will need to fill in **Code**. By default system will use value defined in the SKU field imported from Shopify. However if SKU is empty, it will generate code starting with defined variant prefix and "001".|
|**Shopify Can Update Item**|Select if you want system automatically update items and/or variants.|



### How SKU and Barcode defined in Shopify product impact mapping and creation of items and variants in [!INCLUDE[prod_short](../includes/prod_short.md)]
When products are imported from Shopify to **Shopify Products** and **Shopify Variants** tables, system tries to find existing records. The following table outlines the difference between the options in the **SKU Type** field.

|Option|Impact on mapping|Impact on creation|
|------|-----------------|------------------|
|**Blank**|SKU field is not used in item mapping routine.|No impact on creation of item. <br>Prevents creation of variants. This can be useful if you want to use in sales order only main item. You still will be able to map variant manually from **Shopify Product** window.|
|**Item No.**|Select if SKU field contains item no.|No impact on creation of item without variants. For item with variants, each variant will be created as separate item. Neither item variants nor main item will be created.<br> For example: iif in Shopify you create two variants with SKUs '1000' and '2000', in [!INCLUDE[prod_short](../includes/prod_short.md)] system will create two items with numbers '1000' and '2000'.|
|**Variant Code**|SKU field is not used in item mapping routine.|No impact on creation of item. When creating item variant system will use value of SKU field as Code. If SKU is empty, then system will generate code using **Variant Prefix** field.|
|**Item No. + Variant Code**| Select if SKU field contains item no. and item variant code separated by value defined in the **SKU Field Separator** field.|When creating item system will use first part of value of SKU field as **No.**. If SKU is empty, then system will generate item no using Number series defiend in the **Item Template Code** or **Item Nos.** from the **Inventory Setup** window.<br>When creating item variant system will use the second part of value of SKU field as **Code**. If SKU is empty, then system will generate code using **Variant Prefix** field.|
|**Vendor Item No.**| Select if SKU field contains vendor item no. Note that system will not use **Item Vendor No.** in the **Item card** window, but **Vendor Item No.** from the **Item Vendor Catalog**. If founded Item Vendor Catalor record contains variant code, this variant code will be used by system to map Shopify variant.|If corresponding vendor exists in [!INCLUDE[prod_short](../includes/prod_short.md)] the SKU value will be used as **Vendor Item No.** in the **Item Card** and as **Item Refernce** of type Vendor. <br>Prevents creation of variants. This can be useful if you want to use in sales order only main item. You still will be able to map variant manually from **Shopify Product** window.|
|**Barcode**| Select if SKU field contains barcode. System will perform search among **Item References** of type Vendor. If founded Item Reference record contains variant code, this variant code will be used by system to map Shopify variant.|No impact on creation of item. <br>Prevents creation of variants. This can be useful if you want to use in sales order only main item. You still will be able to map variant manually from **Shopify Product** window.|

The following table outlines the impact of **Barcode** field.
|Impact on mapping|Impact on creation|
|-----------------|------------------|
|System will perform search among **Item References** of type Barcode for value defined in the Barcode field in Shopify. If founded Item Reference record contains variant code, this variant code will be used by system to map Shopify variant.|Barcode is saved as **Item Reference** for item and/or item variant.|

## Export items to Shopify
First you need to choose which elements of your item list will be exported to Shopify. Use **Add Item** action from the **Shopify Products** window to add items to the Shopify products list. 

Following settings let you manage the process of exporting items:
|Field|Description|
|------|-----------|
|**Customer Price Group**|Determine which price should be used for an item in Shopify. The sales price of this customer price group is taken. If no group is entered, the price of the item card is used.|
|**Customer Discount Group**|Determine which discount should be used when calculation price for an item in Shopify. |
|**Sync Item Extended Text**|Select if you want to sync the extended text of the item. Because it will be added to Description, it can contain HTML code. |
|**Sync Item Attributes**|Select if you want to sync the item attributes of the item. Attributes will be formatted as table and included into Description field on Shopify.|
|**Language Code**|If selected system will use tranlsated versions when for Title, Attributes and Extended text.|
|**SKU Type**|Choose how you want to populate SKU field in Shopify. Supported options are:<br> - **Item No.** ot use Item No for both products and variants.<br> - **Item No.+ Variant Code**  to create SKU by concatenating values of two fields. For items without variants system will use only Item No.<br>- **Item Vendor No.** to use Item Vendor No defined in the Item Card for both products and variants.<br> - **Barcode** - uses **Item Reference** of type Barcode. This option respects variants. |
|**SKU Field Separator**|Define a separator for **Item. No + Variant Code** option.|
|**Inventory Tracked**|Select how system should populated Track Inventory field for products exported to Shopify. For products in Shopify, where Track Inventory is enabled you can update availability information from [!INCLUDE[prod_short](../includes/prod_short.md)]. For more information, see [Inventory](synchronize-items.md#Inventory)|
|**Default Inventory Policy**|Select Deny to prevent negative stock of Shopify side. |
|**Can Update Shopify Products**|Define if Business Central can only create items or also update items. Select if after initial sync triggered by **Add Item** action, you plan to update products manually using **Sync Product** action or via job queue for reccuring updates. Remeber to select **To Shopify** in the **Item Sync** field.|

### Price calculation remarks.
- For price calculation it is important to have the **Default Customer Template** field filled in. 
- Remember to fill in **Currency Code** if your online shop uses different currency than LCY. 
- When determining price system uses "Lowest price" logic. Means if Unit Price defined in the Item Card is lower to what is defined in the price group, Unit Price from Item Card will be used.
  
# WIP  
   
## Execute Item Synchronization

There are number of possibilities to perform full or partial synchronization of items.

### Initial sync of items from [!INCLUDE[prod_short](../includes/prod_short.md)] to Shopify
1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and then choose the related link.
2. Choose the **Add Items** action. 
3. Fill in Shop Code. If you open the **Shopify Product** window from the Shop Card, the Shop Code will be populated automatically.
4. Define filters on items as necessary. For example you can filter by item no. or item category code.
5. Click ok.

In result of items are automatically created in Shopify with prices, but without images and inventory levels. 


 

### Ad-hock updates of Shopify Products
When user updates records in the **Shopify Product** table following changes will be synchronized with Shopify.

Update:
* **Status** - you can choose between active, archived, or draft. 
* **SEO Title**
* **SEO Description**

Deletion:
Based on value in the **Remove Product Action** in **Shopify Shop Card**, system may update product in Shopify when record is deleted from the **Shopify Products** page.
- *Blank* - nothing will happen, if necessary user needs to perform needed action from Shopify Admin.
- *Status to Draft* - status of product in Shopify will be set to Draft.
- *Status to Archived* - product will be archived in Shopify.








## Sync item images
For already syncrhronized items you can also configure synchronization of images. 
**Sync Item Images**
- *Blank* - synchronizations of items is disabled
- *To Shopify* - Picture of Items are exported to Shopify
- *From Shopify* - Images from Shopify are imported to [!INCLUDE[prod_short](../includes/prod_short.md)]

You can initialize synchronization of items in two ways.

### Sync product images from the Shopify Shop window
1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, and then choose the related link.
2. Select the Shop for which you want to synchronize items to open **Shopify Shop Card** page.
3. Choose the **Sync Product Images** action. 

### Sync product images from the Shopify Products window
1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Products**, and then choose the related link.
2. Choose the **Sync Product Images** action. 


## 

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






## Inventory Synchronization

The inventory of Shopify goes to Business Central. If there is a difference with the calculated inventory in Business Central, the inventory is updated in Shopify.


On the tab 'Inventory Synchronization' of the Shopify Shop Card, you can enter to sync inventory.

![](media/image54.png)

- **Inventory Synchronization**  
    Define if you want to manage your inventory in Shopify based on Business Central.

- **Default Inventory Policy**  
    Define if you to prevent negative inventory.

    -   Continue: The inventory can go negative.

    -   Deny: You want to prevent negative inventory.


# Execute stock synchronization

On your Shopify Shop Card or on your Shopify Products, you can execute the function 'Sync inventory'.

The inventory of Shopify goes to Business Central. If there is a difference with the calculated inventory in Business Central, the inventory is updated in Shopify.

![](media/image56.png)

You can verify this on the admin page of your Shopify account.

![](media/image57.png)

On het Shopify Products page in Business Central, you can find the 'Shopify Inventory Factbox'. In this factbox you get an overview of the Shopify Stock and the last calculated inventory in Business Central. There is a record per location.

![](media/image58.png)









# Synchronize item to Shopify

 

When you navigate to 'Products' on you Shopify Shop Card, you can add the items from Dynamics 365 Business Central you want to synchronize to Shopify.






<u>Remark:</u> It is possible to add 'Item tags' to your items in Dynamics 365 Business Central. These tags are also synchronized to Shopify.

![Graphical user interface  application Description automatically generated](media/image30.png)

![Graphical user interface  application Description automatically generated](media/image31.png)

![Graphical user interface  application  table Description automatically generated](media/image32.png)




## Setup locations

In Shopify you can define more than one location via 'Settings' &gt; 'Locations'.

![](media/image33.png)

These locations need to be available in Microsoft Dynamics 365 Business Central.

On the Shopify Shop Card: Process &gt; Locations

![](media/image34.png)

Use the function 'Get Shopify Locations' to get the locations from Shopify.

![](media/image35.png)

The locations appear in Business Central. Link the Shopify location with the location in Business Central.

-   Table filter: determines the location(s) for which the stock must be counted.

-   Default location: determines the location to be used in the orders.

![](media/image36.png)

Uncheck 'Disable' if you want to sync the inventory for this location to Business Central.

## Execute Item Synchronization

## By batch task

In the Role center, use the search function to find the task "Sync products":

![](media/image37.png)

![](media/image38.png)

When executing this task, the configured items are synchronized to your Shopify account.

You can verify this on the admin page of your Shopify account.

## By action 'Sync'

When you navigate to 'Products' on you Shopify Shop Card, you can execute the function 'Sync Products' to synchronize the items to your Shopify Account. Only the updated products and fields are synchronized.

![Graphical user interface  text  application Description automatically generated](media/image39.png)

You can verify this on the admin page of your Shopify account.

![](media/image40.png)

![](media/image41.png)

![](media/image42.png)


## Sync Prices to Shopify

Once you've updated your prices in Dynamics 365 Business Central, you can only synchronize prices to Shopify using the 'Sync Prices to Shopify' function on the 'Shopify Products' page.

![Graphical user interface  application Description automatically generated](media/image44.png)

Remark: The price taken follows the standard price calculation of Dynamics 365 Business Central. The lowest valid price is taken.




