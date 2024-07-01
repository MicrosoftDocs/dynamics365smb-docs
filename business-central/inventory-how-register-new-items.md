---
title: Create item cards for goods or services
description: You create item cards for services that you sell as hours and for physical products. Examples include assembly items and finished goods that you sell from your inventory.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: item, finished good, component, raw material, assembly item, item substitution
ms.search.form: 30, 5717, 31, 32, 346, 9091, 5718, 5716, 5720, 1384, 1383, 35, 5404, 1378, 5719
ms.date: 05/24/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Register new items

Items are the goods or services that you buy, store, sell, deliver, and account for. Use the **Item Card** page to register information about the following types of items:

* **Inventory** specifies that the item is a physical unit that you manage and track in inventory.
* **Non-Inventory** are physical units that you don't manage or track in inventory.
* **Service** items are a labor time unit, typically used in service management.

To learn more about these types of items, go to [About Item Types](inventory-about-item-types.md).

> [!TIP]
> There are also catalog items, which are similar to non-inventory items in that they're items that you offer to customers but don't manage until you sell them. To learn more, go to [Work with Catalog Items](inventory-how-work-nonstock-items.md).  

## Primary and alternate vendors

If you purchase the same item from more than one vendor, you can connect those vendors to the item. Use the **Vendors** action on the **Item Card** page to open the **Item Vendor Catalog** page. The page displays the vendors you buy the item from, so you can easily create or select an alternate vendor when you create a purchase order.

## Use item templates

To reuse settings for different types of items when you create new items, you can save items as item templates. Item templates help speed-up the process of adding new items, and increase consistency in your item data. When you register a new item, a page appears that lets you choose a template. After you choose a template, its settings are filled in for you on the item you're creating. If you only have one item template, new items always use that template. To learn how to set up an item template, go to [Save an item card as an item template](#save-an-item-card-as-an-item-template).

## Include items in bills of materials

You can structure hierarchies that have a main item with underlying component items in assembly and production bills of materials (BOM). To learn more about BOMs, go to [Work with Bills of Material](inventory-how-work-BOMs.md).

## To create a new item card

The following video shows how to set up an item on the Item Card page. However, you can also set up new items by copying existing ones. To learn more, go to [Copy Existing Items to Create New Items](inventory-how-copy-items.md).  

> [!Video https://www.microsoft.com/videoplayer/embed/RE47eLx?rel=0]

[!INCLUDE[create_new_item](includes/create_new_item.md)]

> [!NOTE]
> In the **Costing Method** field, you set up how the item's unit cost is calculated by making assumptions about the flow of physical items through your company. Five costing methods are available, depending on the type of item. To learn more about costing, go to [Design Details: Costing Methods](design-details-costing-methods.md).
>
> If you select **Average**, the item's unit cost is calculated as the average unit cost at each point in time after a purchase. Inventory is valuated with the assumption that all inventories are sold simultaneously. With this setting, you can choose the **Unit Cost** field on the **Average Cost Calc. Overview** page to view the transactions that were used to calculate the average cost.

You can use special prices or discounts that you or your vendor grant for the item based on certain criteria. For example, criteria include the customer, minimum order quantity, or ending date. You set up special prices by choosing the **Set Special Prices** or **Set Special Discounts** actions. Each row on, for example, the **Sales Prices** page represents a special price. Each column represents a criterion that must apply to grant a customer the special price that you enter in the **Unit Price** field on the **Sales Prices** page. To learn more about pricing, go to [Record Sales Price, Discount, and Payment Agreements](sales-how-record-sales-price-discount-payment-agreements.md) or [Record Special Purchase Prices and Discounts](purchasing-how-record-purchase-price-discount-payment-agreements.md).

### Save an item card as an item template

1. On the **Item Card** page, choose the **Save as Template** action. The **Item Template** page shows the item card as a template.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!TIP]
> You can also reuse dimensions for items. To reuse dimensions in templates, choose the **Dimensions** action. The **Dimension Templates** page shows the dimensions that are set up for the item. Edit or add dimensions that apply to new items you create from the template.

The item template is added to the list of item templates, so that you can use it to create new item cards.

### Items used in production orders

If you want to register items that are used in production orders, you specify the replenishment system as *Prod. order* on the **Replenishment** FastTab. For more information, see [About Production Orders](production-about-production-orders.md).  

## To set up multiple vendors for an item

If you purchase the same item from more than one vendor, you must enter information about each vendor of the item, such as prices, lead time, discounts, and so on.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
2. Select the relevant item, and then choose the **Edit** action.  
3. Choose the **Vendors** action.  
4. Choose the **Vendor No.** field, and then select the vendor that you want to set up for the item.  
5. Optionally, fill in the remaining fields.  
6. Repeat steps 2 through 5 for each vendor that you want to buy the item from.

The vendors appear on the **Item Vendor Catalog** page, which you open from the item card, so that you can easily select an alternate vendor.

## Set up item substitutions

You can set up items to have replacements, such as other items that can be used in place of the original item.

### To make an item substitution

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
2. Find the relevant item, and then choose the **Item No.** to open the Item Card.  
3. Choose the **Related** action, then choose **Item**, and then **Substitutions** to open the **Item Substitution Entry** page.  
4. Choose the **Substitute No.** field, and then select the replacement item from the list.
5. Fill in or change other fields on the page as necessary.

When the requested quantity exceeds the quantity that is available in inventory, then a message appears to inform you that substitute items exist.

> [!NOTE]  
> Be aware that item substitutions will not automatically cause an item to be replaced by another item, for example when creating a sales order or in a BOM. Instead, you will be alerted to the fact that a substitution is available to you.

## Categories, attributes, and variants

[!INCLUDE[inventory_variant](includes/inventory_variant.md)]

Learn more about variants at [Manage Product Variants](inventory-item-variants.md).  

## Delete item cards

If you post a transaction for an item, you can't delete the card because the ledger entries might be needed for inventory valuation or auditing. To delete item cards with ledger entries, contact to Microsoft partner to do so through code.  

## Manage inventory in warehouses

When you register a new item, you see fields that are related to warehouse management, especially on the **Warehouse** FastTab. If your organization doesn't use the warehouse management capabilities in [!INCLUDE [prod_short](includes/prod_short.md)], then you can ignore those fields.  

If your organization later sets up warehouse management, we recommend that you make sure that each existing item has the right information in the various fields. This way, the warehouse processes can run as expected. The information can includes fields such as **Warehouse Class Code** or **Put-away Template Code**. For more information, see [Setting Up Warehouse Management](warehouse-setup-warehouse.md).  

## Planning

When your company uses the supply planning processes in [!INCLUDE [prod_short](includes/prod_short.md)], you must fill in the relevant fields on the **Planning** FastTab. For an introduction to the planning area, see [Design Details: Central Concepts of the Planning System](design-details-central-concepts-of-the-planning-system.md).  

For examples of how you can use the fields on the **Planning** FastTab, see [Setup Best Practices: Planning Parameters](setup-best-practices-planning-parameters.md).  

## See also

[Inventory](inventory-manage-inventory.md)  
[Set Up Units of Measure](inventory-how-setup-units-of-measure.md)  
[Manage Product Variants](inventory-item-variants.md)  
[Set Up Intrastat Reporting](finance-how-setup-report-intrastat.md#other-intrastat-configurations)  
[Reconcile Inventory Costs with the General Ledger](finance-how-to-post-inventory-costs-to-the-general-ledger.md)  
[Create Number Series](ui-create-number-series.md)  
[Setting Up Posting Groups](finance-posting-groups.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[About Planning Functionality](production-about-planning-functionality.md)  
[Setup Best Practices: Planning Parameters](setup-best-practices-planning-parameters.md)  
[Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md)  
[Design Details: Central Concepts of the Planning System](design-details-central-concepts-of-the-planning-system.md)  
[Design Details: Balancing Demand and Supply](design-details-balancing-demand-and-supply.md)  
[Design Details: Planning Parameters](design-details-planning-parameters.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
