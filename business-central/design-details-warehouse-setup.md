---
    title: Design Details - Warehouse Setup | Microsoft Docs
    description: Warehouse functionality in Business Central contains different levels of complexity, as defined by license permissions in the offered granules. The level of complexity in a warehouse solution is largely defined by the bin setup on location cards, which in turn is license-controlled so that access to bin setup fields is defined by the license.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Design Details: Warehouse Setup
Warehouse functionality in [!INCLUDE[d365fin](includes/d365fin_md.md)] contains different levels of complexity, as defined by license permissions in the offered granules. The level of complexity in a warehouse solution is largely defined by the bin setup on location cards, which in turn is license-controlled so that access to bin setup fields is defined by the license. In addition, the application objects in the license govern which UI document to use for the supported warehouse activities.  

The following warehouse-related granules exist:  

-   Basic Inventory (4010)  
-   Bin (4170)  
-   Put Away (4180)  
-   Warehouse Receipt (4190)  
-   Pick (4200)  
-   Warehouse Shipment (4210)  
-   Warehouse Management Systems (4620)  
-   Internal Picks and Put-aways (4630)  
-   Automated Data Capture System (4640) 
-   Bin Setup (4660)  

For more information about each granule, see [[!INCLUDE[d365fin](includes/d365fin_md.md)] Price Sheets](https://go.microsoft.com/fwlink/?LinkId=238341) (requires PartnerSource account).  

The following table shows which granules are required to define different warehouse complexity levels, which UI documents support each level, and which location codes reflect these levels in the [!INCLUDE[d365fin](includes/d365fin_md.md)] demonstration database.  

|Complexity Level|Description|UI Document|CRONUS Location|Minimum Granule Requirement|  
|----------------------|---------------------------------------|-----------------|---------------------------------|---------------------------------|  
|1|No dedicated warehouse activity.<br /><br /> Receive/ship posting from orders.|Order|BLUE|Basic Inventory|  
|2|No dedicated warehouse activity.<br /><br /> Receive/ship posting from orders.<br /><br /> Bin code is required.|Order, with bin code|SILVER|Basic Inventory/Bin|  
|3 <br /><br /> **NOTE**: Even though the settings are called **Require Pick** and **Require Put-away**, you can still post receipts and shipments directly from the source business documents at locations where you select these check boxes.|Basic warehouse activity, order-by-order.<br /><br /> Receive/ship posting from inventory put-away/pick documents. <br /><br /> Bin code is required.|Inventory Put-away/Inventory Movement/Inventory Pick, with bin code|(SILVER + Require Put-away or Require Put-away)|Basic Inventory/Bin/Put Away/Pick|  
|4|Advanced warehouse activity, for multiple orders.<br /><br /> Consolidated receive/ship posting based on warehouse put-away/pick registrations.|Warehouse Receipt/Warehouse Put-away/Warehouse Pick/Warehouse Shipment/Pick Worksheet|GREEN|Basic Inventory/Warehouse Receipt/Put Away/Pick/Warehouse Shipment|  
|5|Advanced warehouse activity, for multiple orders.<br /><br /> Consolidated receive/ship posting based on warehouse put-away/pick registrations.<br /><br /> Bin code is required.|Warehouse Receipt/Warehouse Put-away/Warehouse Pick/Warehouse Shipment/Pick Worksheet/Put-away Worksheet, with bin code|(GREEN + Bin Mandatory)|Basic Inventory/Bin/Warehouse Receipt/Put Away/Pick/Warehouse Shipment|  
|6 <br /><br /> **Note**: This level is referred to as “WMS”, since it requires the most advanced granule, Warehouse Management Systems.|Advanced warehouse activity, for multiple orders<br /><br /> Consolidated receive/ship posting based on warehouse put-away/pick registrations<br /><br /> Bin code is required.<br /><br /> Zone/Class code is optional.<br /><br /> Warehouse workers directed by workflow<br /><br /> Bin replenishment planning<br /><br /> Bin ranking<br /><br /> Bin setup by capacity<br /><br /> Slotting <!-- Hand-held device integration -->|Warehouse Receipt/Warehouse Put-away/Warehouse Pick/Warehouse Shipment/Warehouse Movement/Pick Worksheet/Put-away Worksheet/Internal Whse. Pick/Internal Warehouse Put-away, with bin/class/zone code<br /><br /> Various worksheets for bin management<br /><br /> ADCS screens|WHITE|Basic Inventory/Bin/Put Away/Warehouse Receipt/Pick/Warehouse Shipment/Warehouse Management Systems/Internal Picks and Put-aways/Bin Setup/<!-- Automated Data Capture System/ -->Bin Setup|  

For examples of how the UI documents are used per warehouse complexity level, see [Design Details: Inbound Warehouse Flow](design-details-outbound-warehouse-flow.md).  

## Bin and Bin Content  
A bin is a storage device designed to contain discrete parts. It is the smallest container unit in [!INCLUDE[d365fin](includes/d365fin_md.md)]. Item quantities in bins are referred to as bin content. A lookup from the **Item** field or **Bin Code** field on any warehouse-related document line displays the calculated availability of the item in the bin.  

A bin content can be given a property of Fixed, Dedicated, or Default to define how the bin content can be used. Bins with none of these properties are referred to as floating bins.  

A fixed bin holds items that are assigned to the bin code in question. The Fixed bin property ensures that even if the bin content is momentarily emptied, the bin content does not disappear, and the bin is therefore selected again as soon as it has been replenished.  

A dedicated bin holds bin content that can only be picked for the dedicated resource, such as a machine center, that uses the bin in question. Other non-pick content, such as quantities outbound on a shipment posting, can still be consumed from a dedicated bin. Only bin content considered by the **Create Pick** algorithm is protected in a dedicated bin.  

The Default bin property is used by the system to suggest bins for warehouse activities. At WMS locations, the Default bin property is not used. At locations where bins are required, the property is used in inbound flows to specify where to place items. In outbound flows, the property is used to specify where to take items from.  

> [!NOTE]  
>  If the outbound items are placed in several bins, then items are first taken from the non-default bins, to empty that bin content, and then the remaining items are taken from the default bin.  

There can only be one default bin per item per location.  

## Bin Type  
In WMS installations, you can restrict the warehouse activities that are allowed for a bin by assigning a bin type to it. The following bin types exist:  

|Bin Type|Description|  
|------------------|---------------------------------------|  
|RECEIVE|Items posted as received but not yet put away.|  
|SHIP|Items picked for warehouse shipment lines but not yet posted as shipped.|  
|PUT AWAY|Typically, items to be stored in large units of measure but that you do not want to access for picking purposes. Because these bins are not used for picking, either for production orders or shipments, your use of a Put Away type bin might be limited, but this bin type could be useful if you have purchased a large quantity of items. Bins of this type should always have a low bin-ranking, so that when received items are put away, other higher-ranking PUTPICK bins fixed to the item are put away first. If you are using this type of bin, you must regularly perform bin replenishment so that the items stored in these bins are also available in PUTPICK or PICK type bins.|  
|PICK|Items to be used for picking only. The replenishment of these bins can only be made by movement, not by put-away.|  
|PUTPICK|Items in bins that are suggested for both the put-away and pick functions. Bins of this type probably have different bin rankings. You can set up your bulk storage bins as this type of bin with low bin rankings compared to your ordinary pick bins or forward picking area bins.|  
|QC|This bin is used for inventory adjustments if you specify this bin on the location card in the **Adjustment Bin Code** field. You can also set up bins of this type for defective items and items being inspected. You can move items to this type of bin if you want to make them inaccessible to the usual item flow. **Note:**  Unlike all other bin types, the **QC** bin type has none of the item handling check boxes selected by default. This indicates that any content you place in a QC bin is excluded from item flows.|  

For all bin types, except PICK, PUTPICK, and PUTAWAY, no other activity is allowed for the bin than what is defined by its bin type. For example, a bin of type **Receive** can only be used to receive items into or pick items from.  

> [!NOTE]  
>  Only movement can be made to bins of type RECEIVE and QC. Similarly, only movements can be made from bins of type SHIP and QC.  

## Bin Ranking  
In advanced warehousing, you can automate and optimize how items are collected in put-away and pick worksheets by ranking bins so that items are suggested taken or placed according to rank criteria to use warehouse space optimally.  

Put-away processes are optimized according to bin ranking by suggesting higher-ranking bins before lower-ranking bins. Similarly, pick processes are optimized by first suggesting items from bin content with high bin ranking. Furthermore, bin replenishments are suggested from lower-ranking bins to higher-ranking bins.  

Bin ranking together with bin content information are the basic properties that allow users to slot items in the warehouse.  

## Bin Setup  
In advanced warehousing, bins can be set up with capacity values, such as quantity, total cubage, and weight to control which and how items are stored in the bin.  

On each item card, you can assign a unit of measure (UOM) for the item, such as pieces, pallets, liters, grams, or boxes. You can also have a base UOM for an item and specify larger UOMs that are based on it. For example, you can define a pallet to equal 16 pieces, the latter being the base UOM.  

If you want to set a maximum quantity of a specific item to be stored in an individual bin and the item has more than one UOM, then you must set the maximum quantity for every UOM that exists on the item card. Accordingly, if an item has been set up to be handled in pieces and pallets, then the **Max. Qty.** field on the **Bin Content** page for that item must also be in pieces and pallets. Otherwise, the allowed quantity for that bin is not calculated correctly.  

Before you set capacity restrictions for bin contents on a bin, you must first make sure that the UOM and dimensions of the item have been set up on the item card.  

> [!NOTE]  
>  It is only possible to operate with multiple UOMs in WMS installations. I all other configurations, bin contents can only be in the base UOM. In all transactions with a UOM higher than the item’s base UOM, the quantity is converted to the base UOM.  

## Zone  
In advanced warehousing, bins can be grouped in zones to manage how the workflow of warehouse activities is directed.  

A zone could be a receiving zone or a stocking zone, and each zone can consist of one or several bins.  

Most properties assigned to a zone will by default be assigned to the bin that is created from that zone.  

## Class  
In advanced warehousing, you can assign warehouse class codes to items, bins, and zones to control where different item classes are stored, such as frozen goods. You can divide a zone into several warehouse classes. For example, items in the receiving zone can be stored as frozen, hazardous, or other class.  

When you work with warehouse classes and a default receiving/shipping bin, you must manually fill in the appropriate bins in the warehouse receipt and shipment lines.  

In inbound flows, the class code is only highlighted on inbound lines where the item class code does not match the default receiving bin. If the correct default bins are not assigned, then the quantity cannot be received.  

## Location  
A location is a physical structure or place where inventory is received, stored, and shipped, potentially organized in bins. A location can be a warehouse, service car, showroom, plant, or an area in a plant.  

## First Expired First Out  
If you select the **Pick According to FEFO** check box on the **Bin Policies** FastTab on the location card, then item-tracked items are picked according to their expiration date. The items with the earliest expiration dates are picked first.  

Warehouse activities in all pick and movement documents are sorted according to FEFO, unless the items in question already have serial/lot numbers assigned. If only a part of the quantity on the line already has serial/lot numbers assigned, then the remaining quantity to be picked is sorted according to FEFO.  

When picking by FEFO, the available items that expire first are gathered in a temporary item tracking list based on the expiration date. If two items have the same expiration date, then the item with the lowest lot or serial number is picked first. If the lot or serial numbers are the same, then the item that was registered first is selected first. Standard criteria for selecting items in pick bins, such as Bin Ranking and Break Bulk, are applied to this temporary FEFO item tracking list.  

## Put-away Template  
The put-away template can be assigned to an item and to a location. The put-away template specifies a set of prioritized rules that must be respected when creating put-aways. For example, a put-away template may require that the item is placed in a bin with bin content that matches the UOM, and if a similar bin with enough capacity cannot be found, then the item must be placed in an empty bin.  

## See Also  
[Design Details: Warehouse Management](design-details-warehouse-management.md)   
[Design Details: Availability in the Warehouse](design-details-availability-in-the-warehouse.md)
