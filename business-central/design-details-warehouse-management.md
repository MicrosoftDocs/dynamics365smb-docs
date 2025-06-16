---
title: Manage warehouse activities
description: In addition to receipts and shipments, Business Central supports a series of internal warehouse activities.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 05/19/2025
ms.custom: bap-template
---

# Warehouse management overview

There are two things that are important to all businesses that physically move goods in and out of their warehouse:

* They have an overview of inventory levels and item placement in the warehouse.
* They can quickly and accurately receive, pick, and ship items.

To help businesses achieve those things, warehouse features in [!INCLUDE[prod_short](includes/prod_short.md)] add the following capabilities to inventory management:

* Bins
* Warehouse shipments
* Inventory picks
* Movement worksheet

Implement these features in different combinations to tailor your warehouse processes for your business. Allow for increasing complexity as your company grows and your processes change.

## Overview of different configuration options

You can configure warehouse features in various ways. It's important to choose options that improve your processes without causing overhead. The following table gives an overview of typical configurations for dealing with physical goods.

|Complexity Level|Description|Settings|Bin Code|Example of Inbound Flow|Example of Outbound Flow|Example of Internal Flow|  
|---|----------------|----------|---------|------------------|------------------|------------------|
|No dedicated warehouse activity.|Posting from orders and journals.||Optional. Controlled by the **Bin Code is Mandatory** toggle.|Purchase order|Sales order| Production order -> Consumption journal|  
|Basic|Consolidated receive/ship posting for multiple orders.|**Require Receipt**<br>**Require Ship**.|Optional. Controlled by the Bin Code is Mandatory toggle|Purchase Orders -> Warehouse Receipt|Sales Order -> Warehouse Shipment|Same as above.|
|Basic|Order-by-order.|Purchase, Sales, Service & Transfer: Require Put-away or Require Pick. </br><br/> Production, Assembly, Projects: Inventory Picks, Inventory Movement, Inventory Put-Away </br></br>**NOTE**: You can still post receipts, shipments, consumption, output directly from the source documents at locations where you activated these settings.|Optional. Controlled by the **Bin Code is Mandatory** toggle.|Purchase Order -> Inventory Put-away|Sales Order -> Inventory Pick|Production Order -> Inventory Pick|
|Advanced|Consolidated receive/ship posting for multiple orders.<br /><br />Consolidated pick/put-away activities for multiple source documents.|Purchase, Sales, Service & Transfer: Require Receive + Require Put-away,</br> Require Ship + Require Pick</br></br> Production, Assembly, Projects: Warehouse Picks |Optional. Controlled by the Bin Code is Mandatory toggle|Purchase Orders -> Warehouse Receipt -> Warehouse Put-away|Sales Orders -> Warehouse Shipments -> Pick Worksheet -> Warehouse Picks| Production order -> Pick Worksheet -> Warehouse Picks -> Consumption journal|
|Advanced|Same as above + Directed pick/put-away activities|Directed Pick and Put-away (dependent toggles are enabled automatically)|Mandatory|Same as above.|Same as above.| Production order -> Pick Worksheet -> Warehouse Picks Consumption journal|

Complexity increases with the size of your organization and how many departments and people are involved. A process can be simple, for example, when the same person creates and posts a sales document. Processes can also be more complex, and involve several steps and people. The following steps are an example of a more complex process:

1. An order processor creates a sales order.
1. A warehouse manager creates pick instructions.
1. A warehouse employee finishes the flow by posting the warehouse shipment.

The types of documents you use in your warehouse activities also affect the level of complexity. For example, you can use warehouse receipt and warehouse put-away documents for your inbound flow, but use inventory pick documents for your outbound flow.

Another factor that impacts complexity is how your physical warehouse is represented in [!INCLUDE[prod_short](includes/prod_short.md)]. Learn more at [Modeling the physical warehouse](#modeling-the-physical-warehouse).

## Modeling the physical warehouse

You have several options for representing the real-world setup of your warehouse in [!INCLUDE[prod_short](includes/prod_short.md)]. Your choices determine how you work with warehouse features.

The placement of items can be shelves, locations, or bins, and there are pros and cons for each option.

### Locations and bins

To handle physical goods, you must have at least one location. You can use multiple locations or use bins to model your warehouse and organizational structure.

Typically, locations are the preferred way to organize operations that are distributed across geographic areas. In some cases, however, you might want to create several locations that are located at the same place. Using locations has the following advantages:

* Grant access by using the **Warehouse Employee** and **Responsibility Centers** pages.
* Define calendars, routings, and inbound and outbound handling times for date calculation and planning. Learn more at [About Planning Functionality](production-about-planning-functionality.md).
* Specify default dimensions and use different inventory posting setups.
* Set up planning parameters. Learn more at [Planning parameters](production-about-planning-functionality.md#planning-parameters).  
* Use different warehouse features for each location.

### Shelves and bins

If you always store an item in the same place, you can use the **Shelf No.** field on the **Item Card** or **Stock-keeping Unit Card** pages. This field can be a basic manual storage system in environments without bins. The field's value is copied from the item card to document lines and reports, but it's only informational. The value isn't used in warehouse activities or availability calculations.

Bins represent the basic warehouse structure, and are used to make suggestions about the placement of items:

* One or more fixed bins for an item.
* Bins for specific operations, such as a shipping bin or a production output bin.
* Bin capacity and weight restrictions (for directed put-away and pick only).
* Bin rating (for directed put-away and pick only).

## Typical warehouse workflow

The following table describes a sequence of tasks, with links to the articles that describe them.

|**To**|**See**|  
|------------|-------------|  
|In a basic flow on an order-by-order basis, use an inventory put-away to record the receipt of items at locations, including any over-receipt. Or, if you're consolidating multiple orders in the receipt, use a warehouse receipt.|[Inbound flow](design-details-inbound-warehouse-flow.md)|
|Record the shipment of items from warehouse locations. On an order-by-order basis, use an inventory pick. Or, if you're consolidating multiple orders in the shipment, use a warehouse shipment.|[Outbound flow](design-details-outbound-warehouse-flow.md)|
|Handle items within the warehouse location. For example, when you move components to production or do a physical inventory count.|[Internal flow](design-details-internal-warehouse-flows.md)|

Set up the warehouse processes that are right for your business. Learn more at [Setting Up Warehouse Management](warehouse-setup-warehouse.md).

## Terminology related to warehouse management

### Complexity levels

We use the terms "basic" and "advanced" to differentiate between levels of complexity. This simple differentiation covers several levels of complexity in location setups, each supported by different warehouse documents. The most advanced level of warehousing is referred to as "Directed put-away and pick." To use directed put-away and pick for a location, turn on the **directed put-away and pick** toggle on the **Location Card** page.

### Warehouse flows

* Inbound flow - Move items into the warehouse location and make them available, such as purchases and inbound transfers.
* Outbound flow - Pick and ship items to customers or other locations.
* Internal flow - Handle items within a location. For example, move components to production or count physical inventory.

### Basic documents  

The following documents are used in basic warehouse flows.

* Inventory Put-away
* Inventory Picks
* Inventory Movement
* Item Journal
* Item Reclassification Journal

### Advanced documents  

The following documents are used in advanced warehouse flows.

* Warehouse Receipt
* Put-away Worksheet
* Warehouse Put-away
* Pick Worksheet
* Warehouse Picks
* Movement Worksheet
* Warehouse Movement
* Internal Warehouse Picks
* Internal Warehouse Put-away
* Bin Creation Worksheet
* Bin Content Creation Worksheet
* Warehouse Item Journal
* Warehouse Item Reclassification Journal

### Pages and settings

This section describes the concepts behind the key pages and settings for warehousing.

#### Bins and bin content

A bin is a storage device designed to contain discrete parts. It's the smallest container unit in [!INCLUDE[prod_short](includes/prod_short.md)]. Item quantities in bins are referred to as *bin contents*. A lookup from the **Item** field or **Bin Code** field on any warehouse-related document line displays the calculated availability of the item in the bin.  

Bin contents can be **Fixed**, **Dedicated**, or **Default** to define how to use the bin content. Bins with none of these properties are referred to as *floating* bins.  

A fixed bin holds items that are assigned to the bin code. The fixed bin property ensures that even if the bin is emptied, the bin content doesn't disappear. You can select the bin again as soon as its contents are replenished.  

A dedicated bin holds bin content that can only be picked for the dedicated resource that uses the bin. For example, a machine center. Other nonpick content, such as outbound quantities on a shipment posting, can be consumed from a dedicated bin. Only bin content considered by the **Create Pick** algorithm is protected in a dedicated bin.  

[!INCLUDE [prod_short](includes/prod_short.md)] uses the **Default** bin property to suggest bins for warehouse activities. At locations that use directed put-away and pick, the default bin property isn't used. At locations where bins are required, the property specifies where to place items in inbound flows. In outbound flows, the property specifies where to take items from.  

> [!NOTE]  
> If outbound items are in several bins, items are taken from the nondefault bins to empty that bin content first. The remaining items are taken from the default bin.  

You can have one default bin per item per location.  

#### Bin type

Locations that use directed put-away and pick can use bin types. Bin types control the activities that you allow for a bin. 

The following types of bins are available:  

|Bin Type|Description|  
|------------------|---------------------------------------|  
|RECEIVE|Items that are received but aren't put away.|  
|SHIP|Items that are picked for warehouse shipment lines but aren't posted as shipped.|  
|PUT AWAY|Typically, items to store in large units of measure but that you don't want to access for picking purposes. These bins aren't used for picking, either for production orders or shipments, so their use might be limited. This type of bin is useful when you purchase a large quantity of items. The bins should always have a low bin-ranking, so that items with higher-ranking PUTPICK bins are put away first. Regularly replenish this type of bin so that their items are available in PUTPICK or PICK type bins.|  
|PICK|Items to be used for picking only. You can only use movements to replenishment of these bins, not put-aways.|  
|PUTPICK|Items in bins that are suggested for both put-aways and picks. Bins of this type probably have different bin rankings. Set up your bulk storage bins with lower bin rankings than ordinary pick bins or bins in your forward picking area.|  
|QC|This bin is used for inventory adjustments if you specify this bin on the location card in the **Adjustment Bin Code** field. You can also set up bins of this type for defective items and items being inspected. You can move items to this type of bin if you want to make them inaccessible to the usual item flow. **Note:**  Unlike all other bin types, the **QC** bin type has none of the item handling checkboxes selected by default. Content you place in a QC bin is excluded from item flows.|  

You can operate your warehouse with all of the eight possible bin types, or you can choose to operate with just the RECEIVE, PUTPICK, SHIP, and QC bin types. These four bin types enable suggestions to be made that support the flow of items and allow you to record inventory discrepancies.
With the exceptions of the PICK, PUTPICK, and PUTAWAY types of bins, the bin type defines the activity allowed for a bin. For example, you can only use a RECEIVE type of bin to receive items or pick items from.  

> [!NOTE]  
> You must use movements to move items to RECEIVE and QC bins. Similarly, use movements to move items from SHIP and QC bins.  

#### Bin ranking

In advanced warehousing, you can automate and optimize how to collect items in put-away and pick worksheets by ranking bins. Items are suggested for picks and put-aways based on the bin ranks.

Put-away processes are optimized according to bin ranking by suggesting higher-ranking bins before lower-ranking bins. Pick processes suggest items with the highest bin ranking from bin content first. Bin replenishment suggests lower-ranking bins before higher-ranking bins.  

Bin ranking and bin contents are the basic properties that guide warehouse employees in the warehouse.  

#### Bin setup

In advanced warehousing, you can specify the following capacity values to control how, and in which, bins you store items:

* Quantity
* Total cubage
* Weight  

You can assign a base unit of measure (UOM) to items. A base UOM might be pieces, pallets, liters, grams, or boxes. You can also create larger UOMs based on your base UOM. For example, if pieces are your base UOM, a pallet might equal 16 pieces.  

If an item has more than one UOM, set the maximum quantity for every UOM on the item card. If you handle an item in pieces and pallets, the **Max. Qty.** field on the **Bin Content** page for that item must also be in pieces and pallets. Otherwise, the allowed quantity for that bin isn't calculated correctly.  

Before you set capacity restrictions for bin contents on a bin, make sure that the UOM and dimensions of the item are set up on the item.  

> [!NOTE]  
> You can only use multiple UOMs at locations that use directed put-away and pick. In all other configurations, you can only use bin contents in the base UOM. In transactions with a UOM that's larger than the item's base UOM, the quantity is converted to the base UOM.  

#### Zone

In advanced warehousing, bins can be grouped in zones to manage how the workflow of warehouse activities is directed for locations.  

A zone could be a receiving zone or a stocking zone, and each zone can consist of one or more bins.  

Most properties assigned to a zone are assigned to the bins that are created for the zone.  

#### Warehouse class

In advanced warehousing, you can assign warehouse class codes to the following entities: 

* Items
* Bins
* Zones

Warehouse classes control where to store items. You can divide a zone into several warehouse classes. For example, you might store items in the receiving zone as frozen, hazardous, or another class.

When you work with warehouse classes and a default receiving/shipping bin, you must manually choose the appropriate bins in the warehouse receipt and shipment lines.  

In inbound flows, the class code is only highlighted on inbound lines where the item class code doesn't match the default receiving bin. If the correct default bins aren't assigned, then the quantity can't be received.  

#### Location

A location is a physical structure or place where inventory is received, stored, and shipped. A location can be a warehouse, service car, showroom, plant, or an area in a plant. Inventory is often organized in bins and zones.

#### First expired first out (FEFO)

If you select the **Pick According to FEFO** checkbox on the **Bin Policies** FastTab on the **Location Card** page, item-tracked items are picked at the location according to their expiration date. Items with the earliest expiration dates are picked first.  

Warehouse activities in all pick and movement documents are sorted according to FEFO, unless the items have serial or lot numbers assigned. If some, but not all, of the quantity on the line has serial or lot numbers assigned, the remaining quantity is sorted according to FEFO.  

When using FEFO, items that expire first are gathered in a temporary item tracking list based on the expiration date. If two items have the same expiration date, the item with the lowest lot or serial number is picked first. If the lot or serial numbers are the same, the item that was registered first is selected first. Standard criteria for selecting items in pick bins, such as Bin Ranking and Break Bulk, are applied to the temporary FEFO item tracking list.  

Learn more at [Enable Picking Items by FEFO](warehouse-picking-by-fefo.md).

#### Put-away template

Put-away templates specify a set of prioritized rules that apply when you create put-aways. For example, a put-away template can require you to place items in a bin with bin content that has the same UOM. If a similar bin with enough capacity can't be found, the item must be placed in an empty bin. You assign a put-away template to an item and a location.  


## Related information

[Inventory and warehouse reports](inventory-WMS-reports.md)   
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
