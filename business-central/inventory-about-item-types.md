---
title: Understand item types
description: Learn about the types of items you can manage in inventory, and how the types affectYou can adjust the inventory valuation of an item using the FIFO or Average costing methods when item costs change for reasons other than transactions.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords:
ms.search.form: 9297, 5845, 30, 
ms.date: 08/12/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# About item types

In the **Type** field on the **Item Card** page, you can select what the item is used for in your business, which affects the degree to which you can manage the item in inventory. The following table lists and describes the three types of items that are available.

|Option|Typical Purpose|
|------|-----------|
|Inventory|Physical things, such as bicycles, telephones, and desks, for which you want to be able to use all inventory processes. Inventory items can also include nonphysical items, such as software licenses and subscriptions, if the items have identification numbers, such as serial numbers. You can fully track item values and availability in inventory.|
|Non-Inventory|Typically, noninventory items are physical things, such as bolts or pens, that your business consumes but doesn't fully track in inventory. For example, because they're low-cost items and only used internally.|
|Service|A labor time unit, such as a consultancy hour, for limited business support.|

> [!NOTE]
> The **Service** and **Non-Inventory** types don't let you track inventory quantities and values. Only selected item transaction types and features are supported. The following table lists the features that the three item types support.

|Item Type|Sales|Purchasing|Job Consumption|Service Consumption|Assembly Consumption|Production Consumption|Assembly Output|Production Output|Location Transfer|Physical Counting|Inventory Revaluation|Inventory Costing|Item Tracking|Reservation|Warehousing|Planning|Order Planning|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|Inventory|Yes|Yes|Yes|Yes|Yes|Yes|Yes|Yes|Yes|Yes|Yes|Yes|Yes|Yes|Yes|Yes|Yes|
|Non-Inventory|Yes|Yes|Yes|Yes|Yes|Yes|No|No|No|No|No|No|No|No|No|No|Yes|
|Service|Yes|Yes|Yes|Yes|No|No|No|No|No|No|No|No|No|No|No|No|Yes|

## Costing methods for types of items

When you post inventory transactions, the quantity and value changes to the inventory are recorded in the item ledger entries and the value entries, respectively.

You record the cost of inventory items in the **Cost Amount (Actual)** field on the **Value Entries** page. When you reconcile the entry to the general ledger, the cost shows in the **Cost Posted to G/L** field. To learn more about inventory costing, go to [Design Details: Inventory Costing](design-details-inventory-costing.md).

For noninventory and service items, cost is recorded in the **Cost Amount (Non-Invtbl.)** field on the **Value Entries** page. For noninventory and service items, specify cost on sales, assembly, and production documents and journals. Specify the default cost in the **Unit Cost** field on the **Item Card** and **Stockkeeping Unit** pages. Costs for these types of items aren't reconciled to the general ledger.

## Catalog and service items

You can set up items that you offer to your customers but you don't manage in until you sell them as catalog items. Although catalog items are similar to regular items of the type **Non-Inventory** in this respect, don't confuse the two because there are differences. To learn more, go to [Work with Catalog Items](inventory-how-work-nonstock-items.md).

Customer items that you service, such as a printer, are called service items. Service items have nothing to do with regular or catalog items. However, service components can be regular items. To learn more, go to [Set Up Service Items and Service Item Components](service-how-setup-service-items.md).

## Resources

In addition to the item type *Item*, sales and purchase documents also allow you to use the item type *Resource*. Like items, resources support dimensions, price lists, and units of measure. <!--With introduction of types *Service* and *Non-Inventory* we do not have any intention to add any extra capabilities for type Resource in purchase and sales processes. We recommend using items of applicable type instead. Resources will continue get new functionality to track the time and effort that is involved with performing and providing services and will stay important part of project and service management. Because many partner solutions use resources, we do not plan to deprecate them in the sales or purchase documents.-->

## Related information

[Register New Items](inventory-how-register-new-items.md)  
[Setting Up Inventory](inventory-setup-inventory.md)  
[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
