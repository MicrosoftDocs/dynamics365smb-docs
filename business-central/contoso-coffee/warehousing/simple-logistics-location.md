# Simple Warehouse Location
The Simple Warehouse Location scenarios use the following settings in the Warehouse FastTab on the Location Card:

|Scenario|Function|
|:--|:--|
|Require Receive|Enabled|
|Require Shipment|Enabled|
|Require Put-Away|Enabled|
|Require Pick|Enabled|
|Bin Mandatory|Disabled|
|Directed Put-away and Pick|Disabled|

In this configuration, documents such as Sales Orders, Purchase Orders, Transfer Orders, and Internal Movements are Source Documents that drive the creation of Warehouse documents, such as:

 - Warehouse Pick
 - Warehouse Shipment
 - Warehouse Put-Away
 - Warehouse Receipt
 - Movement

This allows the division of effort (and access) of different teams to generate the documents needed for Logistics operations in the Warehouse.

Warehouse Receipts are created from various incoming Source Documents (Purchase, Sales Return, Transfers, etc.). Once a Warehouse Receipt is posted, the value and quantity of the items are in Inventory. However, the Items will not be available to ship until the Warehouse Put-Away is registered.

Warehouse Shipments are created from various outgoing Source Documents (Sales, Purchase Return, Transfers, etc.). Warehouse Shipments cannot be posted (in this configuration) until the Warehouse Pick has been created and Registered.

Movements are created via the Movement Worksheet.
Adjustments can be made directly through Item Journals, which will create the Item Ledger Entries.

## Scenarios

1.	[Receiving a Single Order with Whse. Receipt](warehousing/simple/receiving-a-single-order-with-whse-receipt.md)
2.	[Combining Orders on a Whse. Receipt](warehousing/simple/combining-orders-on-a-whse-receipt.md)
3.	[Shipping a Single Order with Whse. Shipment](warehousing/simple/shipping-a-single-order-with-whse-shipment.md)
4.	[Combining Orders on a Whse. Shipment](warehousing/simple/combining-orders-on-a-whse-shipment.md)
5.	[Transferring Items](warehousing/simple/transferring-items.md)
