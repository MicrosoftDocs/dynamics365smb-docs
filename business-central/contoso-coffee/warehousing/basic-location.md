# Basic Location
​​The Basic Location scenarios use the following settings in the Warehouse FastTab on the Location Card:

|Scenario|Function|
|:--|:--|
|Require Receive |Disabled|
|Require Shipment |Disabled|
|Require Put-Away |Enabled|
|Require Pick |Enabled|
|Bin Mandatory |Enabled|
|Directed Put-away and Pick|Disabled|

> [!NOTE]
> Even though the settings are called **Require Pick** and **Require Put-away**, you can still post receipts and shipments directly from the source business documents at locations where you select these checkboxes.

In this configuration, documents such as Sales Orders, Purchase Orders, Transfer Orders, and Internal Movements are Source Documents that drive the creation of Logistics documents, such as:
-  Inventory Pick
-  Inventory Put-Away
-  Inventory Movement

This allows the division of effort (and access) of different teams to generate the documents needed for Logistics operations in the Warehouse.

Adjustments can be made through Item Journals, which will create Item Ledger Entries.

Bin Codes are mandatory in this configuration but note that some Pages may require you to Personalize the column layouts to show the Bin Codes.  Often, Items may have Bins set to ‘Default,’ which will auto-populate the Bin Code fields even if hidden.

## Scenarios

The Contoso Coffee demo data currently supports the following warehousing scenarios for test and training in the Basic configuration:

1. [Receiving Items with Inventory Put-Away](basic/receiving-items-with-inventory-put-away.md)
2.	[Shipping Items with Inventory Picks](basic/shipping-items-with-inventory-picks.md)
3.	[Transferring Items](basic/transferring-items.md)
4.	[Moving Items Between Bins](basic/moving-items-between-bins.md)
5.	[Adjusting Items out of Inventory](basic/adjusting-items-out-of-inventory.md)

## See also

[Setting Up Inventory](../../inventory-setup-inventory)
[How to Setup Locations](../../inventory-how-setup-locations.md)