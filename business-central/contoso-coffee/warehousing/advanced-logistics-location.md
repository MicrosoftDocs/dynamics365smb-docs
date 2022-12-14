# Advanced Warehouse Location
The Advanced Warehouse Location scenarios use the following settings in the Warehouse FastTab on the Location Card:

|Scenario|Function|
|:--|:--|
|Require Receive|Enabled|
|Require Shipment|Enabled|
|Require Put-Away|Enabled|
|Require Pick|Enabled|
|Bin Mandatory|Enabled|
|Directed Put-away and Pick|Enabled|

In this configuration, documents such as Sales Orders, Purchase Orders, Transfer Orders, and Internal Movements are Source Documents that drive the creation of Warehouse documents, such as:

 - Warehouse Pick
 - Warehouse Shipment
 - Warehouse Put-Away
 - Warehouse Receipt
 - Movement

This allows the division of effort (and access) of different teams to generate the documents needed for Logistics operations in the Warehouse.

The Directed Put-Away and Pick functionality allows for more strict controls over how items are allowed to move through Bins throughout the warehousing processes.

Warehouse Receipts are created from various incoming Source Documents (Purchase, Sales Return, Transfers, etc.). Once a Warehouse Receipt is posted, the value and quantity of the items are in Inventory. However, the Items will not be available to ship until the Warehouse Put-Away is registered.

Warehouse Shipments are created from various outgoing Source Documents (Sales, Purchase Return, Transfers, etc.). Warehouse Shipments cannot be posted (in this configuration) until the Warehouse Pick has been created and Registered.

Movements are created via the Movement Worksheet.
Adjustments must be made directly through Warehouse Item Journals, then a secondary step must be completed which will create the Item Ledger Entries.

## Scenarios

1. Receiving Scenarios
    1.	[Receiving & Put-Away with Bin Defaults](advanced/receiving-put-away-with-bin-defaults.md)
    2.	[Receiving & Put-Away with Breakbulk](advanced/receiving-put-away-with-breakbulk.md)
    3.	[Receiving & Put-Away with Bin Capacity Limits](advanced/receiving-put-away-with-bin-capacity-limits.md)
2.	[Warehouse Shipments](advanced/warehouse-shipments.md)
3.	[Cross-Docking with Warehousing](advanced/cross-docking-with-warehousing.md)
4.	[Adjusting Items with Directed Pick & Put Away](advanced/adjusting-items-with-directed-pick-put-away.md)
5.	[Transferring Items](advanced/transferring-items.md)
6.	[Moving Items with Directed Pick & Put Away](advanced/moving-items-with-directed-pick-put-away.md)