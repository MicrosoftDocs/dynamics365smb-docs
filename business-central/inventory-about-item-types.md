---
title: Understanding Item Types
description: You can adjust the inventory valuation of an item using the FIFO or Average costing methods when item costs change for reasons other than transactions.
documentationcenter: ''
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.form: 9297, 5845, 30, 
ms.date: 06/16/2021
ms.author: bholtorf


---
# About Item Types
In the **Type** field on the **Item Card** page, you can select what the item is used for in your business, which affects the degree to which you can manage the item in inventory. The following table lists and describes the three types of items that are available.

|Option|Typical Purpose|
|------|-----------|
|Inventory|Physical things, such as bicycles, telephones, and desks, for which you want to be able to use all inventory processes. This can also include non-physical items, such as software licenses and subscriptions, if the items have identification numbers, such as serial numbers. You can fully track item values and availability in inventory.|
|Non-Inventory|Typically, non-inventory items are physical things, such as bolts or pens, that a business consumes but does not want to fully track in inventory. For example, because they're low-cost items and are only used internally.|
|Service|A labor time unit, such as a consultancy hour, for limited business support.|

> [!NOTE]
> The **Service** and **Non-Inventory** types do not support tracking of inventory quantities and values. Only selected item transaction types and features are supported.

The following table lists the features that the three item types support.

|Item Type|Sales|Purchasing|Job Consumption|Service Consumption|Assembly Consumption|Production Consumption|Assembly Output|Production Output|Location Transfer|Physical Counting|Inventory Revaluation|Inventory Costing|Item Tracking|Reservation|Warehousing|Planning|Order Planning|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|Inventory|Yes|Yes|Yes|Yes|Yes|Yes|Yes|Yes|Yes|Yes|Yes|Yes|Yes|Yes|Yes|Yes|Yes|
|Non-Inventory|Yes|Yes|Yes|Yes|Yes|Yes|No|No|No|No|No|No|No|No|No|No|Yes|
|Service|Yes|Yes|Yes|No|No|No|No|No|No|No|No|No|No|No|No|No|Yes|

## Costing Methods for Types of Items
When you post inventory transactions, the quantity and value changes to the inventory are recorded in the item ledger entries and the value entries, respectively. 

For inventory items, the cost is recorded in the **Cost Amount (Actual)** field on the **Value Entries** page, and when it is reconciled to the general ledger the cost will be shown in the **Cost Posted to G/L** field. For more information, see [Design Details: Inventory Costing](design-details-inventory-costing.md).

For non-inventory and service items the cost is recorded in the **Cost Amount (Non-Invtbl.)** field on the **Value Entries** page. For non-inventory and service items the cost is specified on the sales, assembly, and production documents and journals. The default cost can be specified in the **Unit Cost** field on the **Item Card** and **Stockkeeping Unit** pages. Costs for these types of items are not reconciled to the general ledger. 

## Catalog and Service Items
Items that you offer to your customers but you do not want manage in your system until you start selling them can be set up as catalog items. Catalog items are not to be mistaken with regular items of type Non-Inventory. For more information, see [Work with Catalog Items](inventory-how-work-nonstock-items.md).

Customers' items that you perform service on, such as a printer, are called service items. Service items have nothing to do with regular or catalog items. However, service components can be regular items. For more information, see [Set Up Service Items and Service Item Components](service-how-setup-service-items.md).

## See Also
[Register New Items](inventory-how-register-new-items.md)  
[Setting Up Inventory](inventory-setup-inventory.md)  
[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
