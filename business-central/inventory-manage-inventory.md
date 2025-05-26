---
title: Managing inventory
description: This article describes how to manage the physical products you trade in by creating an inventory item card.
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: warehouse, stock
ms.search.forms: 5804, 2106, 5823, 5751, 5750, 772, 5829, 5828, 513, 304, 40, 38, 167, 117, 5827, 9223, 158, 354, 9152, 286, 5754, 5402, 209, 297, 298, 99000782, Report_704, Report_707, Report_708, Report_709, Report_711, Report_713, Report_714, Report_716, Report_813, Report_1001, Report_5806, Report_5807, Report_5808, Report_5809, Report_7150, Report_7151, Report_7313, Report_7319, Report_7320
ms.date: 11/11/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Manage inventory

For each physical product you trade in, you must create an item card of the **Inventory** type. Items you offer to customers but don't keep in inventory you can register as catalog items, which you can convert to inventory items when necessary. You can increase or decrease the quantity of an item in inventory by posting directly to the item ledger entries, such as after a physical count or if you don't record purchases.

Inventory increases and decreases are naturally also recorded when you post purchase and sales documents, respectively. To learn more, go to [Record Purchases](purchasing-how-record-purchases.md), [Sell Products](sales-how-sell-products.md), and [Invoice Sales](sales-how-invoice-sales.md). Transfers between locations change inventory quantities across your company's warehouses.

To enhance your overview of items and to help you find them, you can categorize items and give them attributes to search and sort by.

> [!NOTE]
> The physical handling of items is referred to as warehouse activities. Learn more at [Warehouse Management Overview](design-details-warehouse-management.md).

Planning for items to fulfill demand is covered as part of supply planning functionality. Learn more at [Planning](production-planning.md).  

## Inventory analytics

This section describes the analytical tools you can use to get insights into your inventory data.

| To... | Go to... |
| --- | --- |
| Get an overview of capabilities for analyzing inventory data. | [Sales analytics overview](inventory-analytics-overview.md) |
| Analyze and monitor your inventory KPIs with the Power BI Inventory apps. | [Power BI Inventory app](inventory-powerbi-app.md) <br> [Power BI Inventory Valuation app](inventory-valuation-powerbi-app.md) |
| Do ad-hoc analysis of inventory data directly on list pages and queries. | [Ad-hoc analysis of inventory data](ad-hoc-analysis-inventory.md) |
| Explore built-in inventory reports. | [Built-in inventory and warehouse reports](inventory-WMS-reports.md) |

## Inventory reconciliation

When you post inventory transactions, such as sales shipments, purchase invoices, or inventory adjustments, the changed item costs are recorded in item value entries. To reflect this change in inventory value in your financial books, the inventory costs are automatically posted to the related inventory accounts in the general ledger. For each inventory transaction you post, the appropriate values are posted to the inventory account, adjustment account, and COGS account in the general ledger. To learn more, go to [Reconcile Inventory Costs with the General Ledger](finance-how-to-post-inventory-costs-to-the-general-ledger.md).

Even though inventory costs are automatically posted to the general ledger, it's still necessary to ensure that the costs of goods are forwarded to the related outbound sales transaction, especially in situations where you sell goods before you invoice the purchase of those goods. This is referred to as cost adjustment. Item costs are automatically adjusted when you post item transactions, but you can also adjust item costs manually. To learn more, go to [Adjust Item Costs](inventory-how-adjust-item-costs.md).  

## Related tasks

The following table outlines related tasks.

|To... |Go to... |
|---|----|
|Create item cards for inventory items that you trade in.|[Register New Items](inventory-how-register-new-items.md)|
|Structure parent items you sell as kits consisting of the parent's components or that you assemble to order or to stock.|[Work with Bills of Material](inventory-how-work-BOMs.md)|
|Maintain an overview of items and help you find and sort items by organizing them in categories.|[Categorize Items](inventory-how-categorize-items.md)|
|Assign item attributes of different value types to your items to help you sort and find items.|[Work with Item Attributes](inventory-how-work-item-attributes.md)|
|Create special item cards for items you offer to customers but don't maintain in inventory.|[Work with Catalog Items](inventory-how-work-nonstock-items.md)|
|Perform physical counting of your inventory with the **Physical Inventory Order** and **Physical Inventory Recording** pages.|[Count Inventory Using Documents](inventory-how-count-inventory-with-documents.md)|
|Perform physical counting, make negative or positive adjustments, and change information, such as location or lot number, on item ledger entries.|[Count, Adjust, and Reclassify Inventory Using Journals](inventory-how-count-adjust-reclassify.md)|
|View the availability of items per location, by period, by sales or purchase event, or by their use on assembly or production bills of material (BOMs).|[View the Availability of Items](inventory-how-availability-overview.md)|
|Transfer inventory items between locations using transfer orders, to manage warehouse activities, or with the item reclassification journal.|[Transfer Inventory Between Locations](inventory-how-transfer-between-locations.md)|
|Reserve inventory or inbound items for sales orders, purchase orders, service orders, assembly orders, transfer orders, or production orders.|[Reserve Items](inventory-how-to-reserve-items.md)|
|Set up item tracking so you can track item serial numbers, such as when you need to track items because of recalls.|[Set Up Item Tracking with Serial, Lot, and Package Numbers](inventory-how-setup-item-tracking.md)|
|Assign serial numbers or lot numbers to any outbound or inbound document or journal line.|[Work with Serial and Lot Numbers](inventory-how-work-item-tracking.md)|
|Find where any serial or lot number was used in its supply chain, such as in recall situations.|[Trace Item-Tracked Items](inventory-how-to-trace-item-tracked-items.md)|
|Set up a vendor's or customer's own item description on your item card so you can quickly insert their item description on trade documents.|[Use Item References](inventory-how-use-item-cross-refs.md)|
|Block items from being entered on sales or purchase lines or from being posted in any transaction.|[Block Items](inventory-how-block-items.md)|
|Manage business operations in sales offices, purchasing departments, or plant planning offices across multiple locations.|[Work with Responsibility Centers](inventory-responsibility-centers.md)|

## Related information

[Warehouse Management Overview](design-details-warehouse-management.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[General Business Functionality](ui-across-business-areas.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
