---
title: Create Item Cards for Goods or Services (contains video)
description: You create item cards for services that you sell as hours and for physical products. Examples include assembly items and finished goods that you sell from your inventory.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: item, finished good, component, raw material, assembly item, item substitution
ms.search.form: 30, 5717, 31, 32, 346, 9091, 5718, 5716, 5720, 1384, 1383, 35, 5404, 1378, 5719
ms.date: 11/02/2022
ms.author: bholtorf
---
# Register New Items

Items, among other products, are the basis of your business, the goods or services that you trade in. Each item must be registered as an item card.

Item cards hold the information that is required to buy, store, sell, deliver, and account for items.

The item card can be of type **Inventory**, **Service**, or **Non-Inventory** to specify if the item is a physical inventory unit, a labor time unit, or a physical unit that isn't tracked in inventory. For more information, see [About Item Types](inventory-about-item-types.md).

An item can be structured as a parent item with underlying child items in a bill of materials (BOM). Learn more about assembly BOMs and production BOMs at [Work with Bills of Material](inventory-how-work-BOMs.md).

If you purchase the same item from more than one vendor, you can connect those vendors to the item card. The **Item Vendor Catalog** page displays the vendors, so that you can easily select an alternate vendor.

*Catalog items* are items that you offer to your customers but you don't want to manage them in your system until you start selling them. Catalog items aren't regular items of type **Non-Inventory**. Learn more at [Work with Catalog Items](inventory-how-work-nonstock-items.md).  

> [!NOTE]  
> If item templates exist for different item types, then a page appears when you create a new item card from where you can select an appropriate template. If only one item template exists, then new item cards always use that template.

The following procedure explains how to create an item card from scratch. You can also create new item cards by copying existing ones. For more information, see [Copy Existing Items to Create New Items](inventory-how-copy-items.md).  

<br />

> [!Video https://www.microsoft.com/videoplayer/embed/RE47eLx?rel=0]

## To create a new item card

[!INCLUDE[create_new_item](includes/create_new_item.md)]

> [!NOTE]
> In the **Costing Method** field, you set up how the item's unit cost is calculated by making assumptions about the flow of physical items through your company. Five costing methods are available, depending on the type of item. For more information, see [Design Details: Costing Methods](design-details-costing-methods.md).
>
> If you select **Average**, then the item's unit cost is calculated as the average unit cost at each point in time after a purchase. Inventory is valuated with the assumption that all inventories are sold simultaneously. With this setting, you can choose the **Unit Cost** field to view, on the **Average Cost Calc. Overview** page, the history of transactions that the average cost is calculated from.

You can view or edit special prices or discounts that you grant, or that your vendor grants you, for the item if certain criteria are met, such as customer, minimum order quantity, or ending date. You do this by choosing the **Set Special Prices** or **Set Special Discounts** actions. Each row on, for example, the **Sales Prices** page represents a special price. Each column represents a criterion that must apply to grant a customer the special price that you enter in the **Unit Price** field on the **Sales Prices** page. For more information, see [Record Sales Price, Discount, and Payment Agreements](sales-how-record-sales-price-discount-payment-agreements.md) or [Record Special Purchase Prices and Discounts](purchasing-how-record-purchase-price-discount-payment-agreements.md).

The item is now registered, and the item card is ready to be used on purchase and sales documents.

If you want to use this item card as a template when you create new item cards, you can save it as a template. For more information, see the following section.  

### To save the item card as a template

1. On the **Item Card** page, choose the **Save as Template** action. The **Item Template** page opens showing the item card as a template.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. To reuse dimensions in templates, choose the **Dimensions** action. The **Dimension Templates** page opens showing any dimension codes that are set up for the item.
4. Edit or enter dimension codes that apply to new item cards created by using the template.
5. When you complete the new item template, choose the **OK** button.

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
