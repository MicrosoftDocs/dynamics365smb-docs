---
author: edupont04

ms.service: dynamics365-business-central
ms.topic: include
ms.date: 04/01/2021
ms.author: edupont
---

The following table describes some of the key reports in inventory and warehouse reporting.

|Report |Object ID|Description  |
|---------|---------|---------|
|**Inventory Availability Plan**|707|If you would like to have an overview about specific items/stockkeeping units and their availability. This report shows cumulated values like gross requirements, scheduled and planned receipts, the inventory, and so on. |
|**Inventory Valuation**|1001|Displays inventory valuation for selected items in your inventory. The report also shows information about the value of increases and decreases in inventory over time.|
|**Item Expiration - Quantity**|5809|Shows an overview of the quantities of selected items in your inventory whose expiration dates fall within a certain period. The list shows the number of units of the selected item that will expire in a given time period. For each of the items that you specify when setting up the report, the printed document shows the number of units that will expire during each of three periods of equal length and the total inventory quantity of the selected item.<br>You can specify what is included in the report by setting filters. If you do not set any filters, the report will include all your records. The quantities in the report reflect only the quantities of the item for which expiration dates have been defined.|
|**Item Age Composition - Quantity** or **Item Age Composition - Value**|5807 or 5808|Shows an overview of the current age composition of selected items in your inventory. The list shows the number of units or value of the selected item that were added to or removed from inventory and at which point in time. Items can be added to or removed from inventory as a result of purchases, sales, and positive and negative adjustments.|
|**Inventory Cost and price list**|716|Displays a list of price information for the selected items or stockkeeping units: direct unit cost, last direct cost, unit price, profit percentage, and profit. |
|**Warehouse Bin List**|7319|Shows an overview of warehouse bins, their setup, and the quantity of items within the bins. This report can be used for all locations, which have “bin” as mandatory field. |
|**Warehouse Shipment Status**|7313|Shows an overview of open source documents with items shipped or due for shipping per location. This report can be used for all locations, were **Required Shipments** is enabled. **Warehouse Shipment Status** shows locations, bin codes, document status, quantities.|
|**Inventory Picking List**|813|Displays a list of the sales orders in which an item is included. The following information is shown for each item: sales order line with customer's name, variant code, location code, bin code, shipment date, quantity to be shipped, and unit of measure. The quantity to be shipped is totaled for each item. The report can be used when items will be collected from the inventory.<br>NOTE: this functionality is not available for advanced warehouse functionality.|
|**Warehouse Adjustment Bin**|7320|This special report is meant only for an advanced warehouse and shows the remaining quantities that are still stored in the adjustment bin itself. Normally this specific bin should be empty. The only reason when this bin will be filled is as result of physical counting process or if quantities of items had been removed or added to the warehouse|