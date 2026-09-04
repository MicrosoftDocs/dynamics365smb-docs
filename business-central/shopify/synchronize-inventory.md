---
title: Synchronize inventory with Shopify
description: Set up and run inventory synchronization between Business Central and Shopify, including location mapping and fulfillment strategies.
ms.date: 09/03/2026
ms.topic: how-to
ms.search.form: 30102, 30116, 30117, 30126, 30127
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Synchronize inventory with Shopify

Inventory synchronization sends current stock levels from [!INCLUDE[prod_short](../includes/prod_short.md)] to Shopify so that product availability is accurate across all your Shopify sales channels. [!INCLUDE[prod_short](../includes/prod_short.md)] acts as the system of record for inventory. When you receive goods, complete production, or transfer stock between warehouses, the connector automatically updates Shopify.

You can configure inventory synchronization for items that are already synchronized if two conditions are met:

1. Inventory tracking is enabled for a product in Shopify. If you export items to Shopify, consider enabling the **Inventory Tracked** toggle on the **Shopify Shop** page. Learn more at [Export items to Shopify](synchronize-items.md#export-items-to-shopify) section.
1. Inventory sync is enabled for **Shopify Locations**.

## Enable inventory sync

1. [!INCLUDE [open-search](../includes/open-search.md)], enter **Shopify Shop**, and choose the related link.
1. Select the shop for which you want to synchronize inventory to open the **Shopify Shop Card** page.
1. Choose the **Locations** action to open **Shopify Shop Locations**.
1. Choose the **Get Shopify Locations** action to import all the locations defined in Shopify. You can find the locations in the [Locations](https://www.shopify.com/admin/settings/locations) settings in your **Shopify Admin**.
1. In the **Location Filter** field, add locations if you want to include inventory from specific locations only. For example, enter **EAST|WEST** to make the inventory from only these two locations available for sales via the online shop.
1. Select the stock calculation method to use for the selected Shopify locations.
1. Enable **Default Product Location** if you want the location to be used for creation of inventory records and to participate in the inventory synchronization.

The remaining sections in this article describe ways to synchronize inventory.

## Run inventory sync from the Shopify shop page

1. [!INCLUDE [open-search](../includes/open-search.md)], enter **Shopify Shops**, and choose the related link.
1. Select the shop for which you want to synchronize inventory to open the **Shopify Shop Card** page.
1. Choose the **Sync inventory** action.

## Run inventory sync from the Shopify products page

1. [!INCLUDE [open-search](../includes/open-search.md)], enter **Shopify Products**, and choose the related link.
1. Choose the **Sync inventory** action.

## Run a targeted inventory sync

Use the **Sync Stock to Shopify** report to synchronize specific variants or to skip importing inventory from Shopify before export.

1. [!INCLUDE [open-search](../includes/open-search.md)], enter **Sync Stock to Shopify**, and select the related link.
1. On the request page, specify the shop and any of the following options:

    |Option|Description|
    |------|-----------|
    |**Variant ID Filter**|Synchronize only the Shopify variants that match the filter. Use standard filter expressions, such as `1000|2000`, to include multiple variant IDs. The filter applies only when you export inventory to Shopify. It doesn't limit the inventory that the connector first imports from Shopify.|
    |**Skip Import Stock**|Skip importing inventory from Shopify and export the calculated inventory from [!INCLUDE [prod_short](../includes/prod_short.md)]. The connector exports matching inventory even when the calculated quantity equals the last imported Shopify quantity.|

    > [!CAUTION]
    > Before you select **Skip Import Stock**, run the report with this option turned off. Continue to run the report with the option turned off periodically to refresh Shopify quantities and remove obsolete local inventory records. The first run also creates the local inventory records for the variants and locations.

1. Select **OK** to run the report.

## Understand inventory synchronization

Consider the following information when you synchronize inventory:

* There are two standard stock calculation methods, **Projected Available Balance at Today** and **Free Inventory (not reserved)**. However, you can use extensibility to add more. Learn more at [examples](/dynamics365/business-central/dev-itpro/developer/devenv-extending-shopify#stock-calculation).
* If the stock information in Shopify differs from the **Projected Available Balance** in [!INCLUDE[prod_short](../includes/prod_short.md)], the stock updates in Shopify.
* When you add a new location in Shopify, you must also add inventory records for it. Shopify doesn't automatically add inventory records for existing products and variants, and the connector doesn't synchronize inventory levels for such items in the new location. Learn more at [Assigning inventory to locations](https://help.shopify.com/manual/locations/assigning-inventory-to-locations).
* You can use both **Business Central Fulfillment Services** and normal locations for shipping and inventory.
* When you deal with bundles, check whether adjusting inventory via an API is allowed for those products. For example, the **Shopify Bundles** app calculates availability of bundles based on the availability of the components and prevents updates via APIs. It's a good idea to map Shopify products of the type **Bundle** to items of the type **Non-inventory**. Non-inventory and service items are excluded from inventory synchronization.

### Example of a projected available balance calculation

There are 10 pieces of item A available on-hand and two outstanding sales orders. One order is for Monday with a quantity of *1*, and one order is for Thursday with quantity *2*. Depending on when you sync inventory, the stock level in Shopify updates with different quantities.

|When sync inventory is run|Value used to update stock level|Comment|
|------|-----------------|-----------------|
|Tuesday|9|Inventory 10 minus sales order set to ship on Monday|
|Friday|7|Inventory 10 minus both sales orders|

### Example of calculation of available inventory (not reserved)

There are 10 pieces of item A available on hand and three outstanding sales orders. One order with quantity *1* reserved from item ledger entry, one order with quantity *2* that isn't reserved, and one order with quantity *3* that is reserved from a purchase order. For this method, the date of synchronization isn't important.

|Value used to update stock level|Comment|
|-----------------|-----------------|
|9|Inventory 10 minus the sales order with reserved inventory from item ledger entry. Other sales orders are ignored.|

## Manage fulfillments and locations

In Shopify, you can manage fulfillment in two ways:

* Shopify **built-in** fulfillment and inventory tracking
* Third-party fulfillment and inventory tracking

Shopify can stock inventory for each product, or a 3PL can stock it.

If you use Shopify fulfillment, you can also define multiple locations in Shopify. When you create an order, Shopify selects a location based on availability and priority. You can also specify the locations where you plan to track a specific product. For example, you can set the product to never sell from the *ShowRoom* location.

If you use 3PL, the 3PL provider takes care of physical handling, so you don't need locations. For 3PL, the SKU field is mandatory.

When you decide which location to track an item, Shopify creates records in the **Inventory Levels** table. You can update these records manually with inventory availability.

The connector supports both modes. It can send inventory to multiple Shopify locations or work as a fulfillment service.

From the [!INCLUDE[prod_short](../includes/prod_short.md)] perspective, when you create an item and want to send it to Shopify, you also want to:

* Use the **Default Product Location** toggle to specify whether Shopify fulfillment or 3PL fulfills the item. There's always **Business Central Fulfillment Service**, but there can be more fulfillment services if you install more apps. You can enable **Default Product Location** in only one record if you want to use a fulfillment service.
* Use the **Default Product Location** toggle to specify which locations you want to use to track inventory. You can turn on **Default Product Location** for multiple locations where **Is Fulfillment Service** isn't enabled. The system always tracks inventory for a primary location.

### What's the difference?

Shopify fulfillment is useful when you use Shopify POS and there are multiple physical stores. You want employees in the physical store to know their current inventory. In this case, you create multiple locations in Shopify, multiple locations in [!INCLUDE[prod_short](../includes/prod_short.md)], and activate a **Default Product Location** for all these locations.  

If you handle logistics in [!INCLUDE[prod_short](../includes/prod_short.md)], where you can have many locations, don't create locations in Shopify. The connector automatically creates Business Central Fulfillment Services, and you can link inventory via location filters from several locations to one fulfillment services record. As a result, there's no information about where goods are sent from in Shopify. The system only has tracking information, while in [!INCLUDE[prod_short](../includes/prod_short.md)] you can select locations based on availability and proximity to the destination.

### Example of using Default Product Location toggle

After you choose the **Get Shopify Locations** action in the **Shopify Locations** page, you have the following locations:

|Name|Is Fulfillment Service|Is Primary|
|------|-----------------|-----------------|
|Main| |**Yes**|
|Second| | |
|Business Central Fulfillment Service|**Yes**| |

The following table describes what happens when you enable the **Default Product Location** toggle:

|Name of locations where Default Product Location toggle is turned on|Effect on how the product is created in Shopify|
|------|-----------------|
|Main| Inventory is stocked at: Multiple locations; Selected locations: Main (primary) |
|Main and Second| Inventory is stocked at: Multiple locations; Selected locations: Main and Second |
|Business Central Fulfillment Service|Inventory is stocked at: Business Central Fulfillment Service; Selected locations: (App) Business Central Fulfillment Service|
|Business Central Fulfillment Service and Main| Error: You can't use standard Shopify Locations with Fulfillment Service Locations|

## Plan replenishment in [!INCLUDE[prod_short](../includes/prod_short.md)]

[!INCLUDE[prod_short](../includes/prod_short.md)] is your system of record for supply chain operations. Use the system to plan and execute replenishment, then let the inventory sync keep your Shopify storefront up to date.

The following capabilities in [!INCLUDE[prod_short](../includes/prod_short.md)] feed your Shopify inventory levels:

* **Requisition worksheets** calculate reorder suggestions based on sales demand, safety stock, and lead times. When you carry out the action messages and post the resulting purchase receipts, Shopify stock levels update on the next sync.
* **Purchase orders** with vendor-specific lead times, quantity discounts, and receiving workflows ensure stock arrives on time and in the right quantities.
* **Transfer orders** move inventory between warehouses. If you map multiple [!INCLUDE[prod_short](../includes/prod_short.md)] locations to Shopify locations, each transfer receipt updates the correct Shopify stock levels.
* **Assembly and production output** post finished goods to inventory. For make-to-stock items sold on Shopify, completing production immediately makes them available for sale.

Because the connector sends [!INCLUDE[prod_short](../includes/prod_short.md)] calculated availability (not just on-hand quantities), your Shopify customers have realistic stock levels that account for outstanding demand and incoming supply.

> [!TIP]
> Use the [job queue](background.md) to run inventory synchronization on a schedule. A frequency of every 15-30 minutes keeps Shopify stock levels current without manual intervention.

## Troubleshooting inventory synchronization

If the inventory level doesn't sync with Shopify, try these checks.

1. Go to the **Shopify Shop Locations** page and verify the value in the **Stock calculation** field. Learn more at [Enable inventory sync](#enable-inventory-sync).
    * If you use a calculation method added by an extension, ask the extension provider to verify that the enum value implements both `Shpfy Stock Calculation` and `Shpfy IStock Available`. The `Shpfy IStock Available` implementation determines whether the calculation method permits inventory export. Learn more at [Stock calculation](/dynamics365/business-central/dev-itpro/developer/devenv-extending-shopify#stock-calculation).
1. In the **Shopify admin**, go to **Products** or **Variants** and:
    * check that the **Track quantity** toggle is turned on.
    * check whether the affected location appears in the **Inventory** section. If the location is missing, inventory isn't assigned to that location. Learn more at [Assigning inventory to locations](https://help.shopify.com/manual/locations/assigning-inventory-to-locations).
1. Go to the **Shopify Products** page, locate the product, and verify that the Shopify variant is linked to the correct item and item variant, if needed. Check the **Item No.** and **Variant No.** fields in the **Shopify Variants** part. The connector excludes non-inventory and service items from inventory synchronization.
1. Go to the **Shopify Products** page, locate the product, and check the stock details in the **Shopify Inventory** FactBox for the affected variant and location. The FactBox shows the stock in Shopify, the last stock calculated in [!INCLUDE[prod_short](../includes/prod_short.md)], and when each value was updated. There's one record per location.
    * Compare **Shopify Stock** with **Last Calculated Stock**. If the values are equal, the connector doesn't send an update to Shopify.
    * If the values differ, check **Last Synced On** and **Last Calculated On**. **Last Synced On** shows when the stock was last imported from Shopify. **Last Calculated On** shows when the stock was last calculated in [!INCLUDE[prod_short](../includes/prod_short.md)].

1. Go to the **Shopify Log Entries** page, and check for entries with **Has Error** enabled around the time the inventory level was synchronized. To limit the records, apply the `*inventorySetQuantities*` filter to the **Request Preview** field. If such entries exist, open the **Shopify Log Entry** page and inspect the **Response Data** field. If there's a validation error on Shopify's side, the response includes more information in the **userErrors** section.
1. On the **Shopify Shop Card** page, temporarily set **Logging Mode** to **All**, and then run the inventory synchronization again. Go to the **Shopify Log Entries** page and review entries created during that run. To find inventory update requests, filter the **Request Preview** field by `*inventorySetQuantities*`. If the calculated stock differs from the Shopify stock but no `inventorySetQuantities` request exists, the connector skipped the update before communicating with Shopify. Recheck the item type, location setup, mapping, and any custom stock calculation implementation. After you finish troubleshooting, restore the previous **Logging Mode** setting.

To learn more about logging, go to [Logs](troubleshoot.md#logs).

## Related information

[Synchronize items with Shopify](synchronize-items.md)  
[Synchronize prices with Shopify](synchronize-prices.md)  
[Shopify Connector overview](shopify-connector-overview.md)  
[FAQ for the Shopify connector](shopify-faq.md)  
[Troubleshoot the Shopify Connector](troubleshoot.md)  
