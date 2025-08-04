---
title: Design Details - Changing Costing Methods for Items
description: Learn how to assign a different costing method to an item although you have already used the item in transactions.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: costing methods, costing, item cost
ms.search.form: 8645
ms.date: 06/08/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Design Details: Change the Costing Method for Items

In [!INCLUDE[prod_short](includes/prod_short.md)], you cannot change a costing method for an item after you have included the item in a transaction. For example, after you have bought or sold the item. If an incorrect costing method was assigned to the item or items, you might not discover the issue until you do your financial reporting.

This topic describes how to resolve this situation. The recommended approach is to replace the item that has the incorrect costing method with a new item, and use an assembly order to transfer the inventory from the old item to the new.

> [!NOTE]
> Using assembly orders allows the costs to still flow although there are outstanding purchase invoices or shipping charges to post. Additionally, it allows you to undo the conversion and get the quantities of the original items back, if needed.

> [!TIP]
> To become familiar with the process, we recommend that you start the conversion process with a single item or a small set of items.

## About Costing Methods

Costing methods control cost calculations when goods are purchased, received in inventory, and sold. Costing methods affect the timing of amounts recorded in COGS that affect gross profit. It is this flow that calculates COGS. The cost of goods sold (COGS) and revenue are used to determine gross profit, as follows:

*gross profit* = *revenue - COGS*

When you set up inventory items, you must assign a costing method. The method can vary from business to business, and from item to item, so it's important to choose the right one. [!INCLUDE[prod_short](includes/prod_short.md)] supports the following costing methods:

* Average
* FIFO
* LIFO
* Standard
* Specific

For more information, see [Design Details: Costing Methods](design-details-costing-methods.md).

## Use Assembly Orders to Change Costing Method Assignments

This section describes the following steps for changing the costing method assigned to an item:

1. Define a default costing method.
2. Identify the items that to change the costing method for and renumber them.
3. Create new items with the old numbering scheme and copy the master data in a batch.
4. Manually copy related master data from the existing item to the new item.
5. Determine the inventory quantity to convert from the original item to the new item.
6. Transfer the inventory to the new item.
7. Handle inventory quantities that are allocated to demand.
8. Block the original item from further use.  

### Define a default costing method

To help avoid future mistakes you can specify a default costing method for new items. Whenever someone creates a new item, [!INCLUDE[prod_short](includes/prod_short.md)] will suggest the default costing method. You specify the default method in the **Default Costing Method** field on the **Inventory Setup** page. 

### Identify the items to change the costing method for and renumber them

You may want to give your new items the same numbers as those they are replacing. To do that, change the numbers of the existing items. For example, if the existing item number is "P1000," you might change it to "X-P1000." This is a manual change that you must make for each item.

### Create new items with the old numbering scheme and copy the master data in a batch

Create the new items using the current number scheme. With the exception of the **Costing Method** field, the new items should contain the same master data as the existing items. To transfer the master data for the item, and related data from other features, use the **Copy Item** action on the **Item Card** page. For more information, see [Copy Existing Items to Create New Items](inventory-how-copy-items.md).

After you create the new items and transfer the master data, assign the correct costing method.

### Manually copy related master data from the original item to the new item

To make the new items fully useful you must manually copy some master data from other areas, as described in the following table.

|Area  |What to copy  |How to copy it  |
|---------|---------|---------|
|Inventory |Stock-keeping units (SKUs) |Check whether a SKU is specified for the original item. If planning parameters have been entered for each SKU card, then you must manually create the SKU for the new item. If the parameters are not specified, you can use the **Create Stockkeeping Unit** batch job from the **Item Card** page to create the data.|
| |Item substitutions |Check whether any item substitutions are defined for the original item. If there are, transfer that data to the new item. To view substitute items, use the **Substitutions** action on the **Item Card** page. |
| |Analysis reports |Review the Item Analysis, Sales Analysis, and Purchase Analysis reports. For those that reference the original items you can either create a new analysis report with a reference to the new item (keeping the original analysis report to use as history) or adjust the reports so that they reference the new item. |
| |Standard journals |Check whether standard journals reference the original item and transfer that data to the new item when necessary. This information is found on the standard journals, which are available on the item journal.  |
|Sales |Sales prepayment percentage | Check whether any sales prepayment percentages are defined for the original item and transfer that data to the new item. To view prepayment percentages, on the **Item Card** page, choose **Sales**, and then **Prepayment Percentages**.|
|Purchase |Purchase prepayment percentage |Check whether any purchase prepayment percentages are defined for the original item and transfer that data to the new item. To view prepayment percentages, on the **Item Card** page, choose **Purchases**, and then **Prepayment Percentages**. |
|Warehouse |Bin contents |Review the bin content defined for the original item. If columns such as Min. Qty., Max. Qty., Default, and Dedicated have been individually entered then you must manually create bin content for the new item. If they are not, no action is required. [!INCLUDE[prod_short](includes/prod_short.md)] will maintain the records when you register warehouse documents and journals.|
|Job |Job Prices |Check whether project prices are defined for the original item and transfer that data to the new item. This information is available on the **Project Card** page in the **Project Details – No. of Prices** part on the **FactBox pane**. |
|Service |Service resource skill |Check whether service resource skills are defined for the original item and transfer that data to the new item. To view resource skills, use the **Resource Skills** action on the **Item Card** page.  |
| |Service item components |Check whether components are defined for the original service item and transfer that data to the new item. To view service item components, on the **Item Card** page use the **Service Item** action to open the list of related service items, and then choose the **Components** action.  |
|Production |Production BOMs |Check whether any production BOMs contain the original item and replace it with the new item. To replace the original item, on the **Production BOMs** page, choose the **Exchange Production BOM Item** action. |
|Assembly |Assembly BOMs |Check whether any assembly BOMs contain the original item and manually replace it with the new item. |

> [!IMPORTANT]
> If the new costing method is Standard you should enter a value in the **Standard Cost** field on the **Item Card** page. You can use the **Standard Cost Worksheet** page to set the cost shares accordingly. For more information, see [Update Standard Costs](finance-how-to-update-standard-costs.md).

### Determine the inventory quantity to convert from the original item to the new item

> [!NOTE]
> This step does not consider quantities that are included in unshipped orders. For more information, see [Handle inventory quantities that are allocated to demand](design-details-changing-costing-methods.md#handle-inventory-quantities-that-are-allocated-to-demand). 

Use a physical inventory journal to produce a list of the quantities in inventory. Depending on the warehouse location setup, use one of the following:

* Physical Invt. Journals
* Whse. Phys. Invt. Journals

Both journals can calculate the inventory quantity of the item, including the location, variant, bin, and storage location. For more information, see [Count, Adjust, and Reclassify Inventory Using Journals](inventory-how-count-adjust-reclassify.md).

### Transfer the inventory to the new item

Create and post assembly orders to transfer the cost and inventory quantity from the original item to the new item. Assembly orders can convert one item to another while preserving the costs. This helps ensure that the net totals for the inventory account and COGS are not affected (except when the new costing method is Standard, in which case costs may be distributed to variance accounts). For more information, see [Assembly Management](assembly-assemble-items.md).

When creating assembly orders, use the information from the Physical Invt. journal or Whse. Phys. Invt. journal. The following tables describe the information in the reports to enter in the header and lines on the assembly order.

#### Header

|Field  |Value to enter  |
|---------|---------|
|Item No. |The number of the new item. |
|Quantity |The quantity in physical inventory journal.<br> **NOTE:** The quantities calculated by the physical inventory journals does not include the quantities that are on orders that have not yet shipped.  |
|Variant Code |The same as in physical inventory journal.  |
|Location Code |The same as in physical inventory journal. |
|Unit of Measure Code |The same as in physical inventory journal. |
|Bin Code |The same as in physical inventory journal. |

#### Lines

|Field  |Value to enter  |
|---------|---------|
|Type |Item |
|No. |The number of the original item. |
|Quantity per |1 |
|Variant Code |The same as in physical inventory journal. |
|Location Code |The same as in physical inventory journal. |
|Unit of Measure Code |The same as in physical inventory journal. |

> [!NOTE]
> An assembly order can handle only one SKU of an item at a time. You must create an assembly order for each combination of SKU that has a quantity in inventory.

> [!NOTE]
> For a warehouse location, you might have to create picks before you can post the assembly order. To investigate that, review the setup for picking on the **Location Card** page. For more information, see [Set Up Items and Locations for Directed Put-away and Pick](warehouse-how-to-set-up-items-for-directed-put-away-and-pick.md).

### Handle inventory quantities that are allocated to demand

Ideally, the inventory for the original item should go to zero after you transfer the inventory quantities. However, there can be outstanding orders, worksheets, and journals (see the table below) that still require a quantity of the original item. The quantity could also be blocked by a reservation or item tracking.

**Example**
There are 1000 pcs. in inventory, and 20 pcs. are reserved for a sales order that has not yet shipped. In that case, you might decide to keep the 20 pcs. in the old item so that you can fulfill the outstanding order.

> [!NOTE]
> There are functional areas that can affect the quantity, as listed in the table below, so it can be tricky to find the correct amount. To be safe, using the example above, you can choose to keep 100 pcs. and transfer the remaining 900 pcs. instead. Another way to do it would be to process the documents and journals so that only a manageable few remain. Yet another alternative is to transfer the entire quantity to the new item and then transfer some of it back to the original item using the assembly order.

The following table lists functional areas where there might be outstanding quantities.

|Area  |Where to look for outstanding quantities  |
|---------|---------|
|Sales |Sales documents, including orders, return orders, invoices, quotes, blanket orders, and credit memos |
|Inventory |Item journals, reservations, item tracking, and standard cost worksheet |
|Purchase |Purchase documents, including orders, return orders, invoices, quotes, blanket orders, and credit memos |
|Planning |Requisition worksheet, planning worksheet, and order planning |
|Warehouse |Transfer orders, warehouse shipments, warehouse journals, and warehouse picks, put-aways, and movements, internal picks and put-aways, and bin creation worksheets |
|Assembly |Assembly documents, including orders, return orders, and blanket orders |
|Jobs |project planning lines and project journal lines |
|Service |Service documents and service contracts |
|Production |Production orders (planned, firm planned, and released) |

### Block the original item from further use

When the inventory for the original item is zero, you can block the item to prevent it fom being used in new transactions. To block the item, on the **Item Card** page, turn on the **Blocked** toggle. For more information, see [Block Items from Sales or Purchasing](inventory-how-block-items.md).

## Summary

Changing the costing method on items that have been used in transactions is a process, and not a standard action in [!INCLUDE[prod_short](includes/prod_short.md)]. You can use the steps described in this topic as a template for the process.

The process can be time consuming because there are several manual steps. However, taking the time to complete it will minimize the impact of mistakes on your general ledger.

We recommend the following:

1. Assess the feasibility of the process by taking one, or maybe a few, representative items through the entire process.
2. Consider contacting an experienced partner who can help you with the process.

## Related information

[Design Details: Costing Methods](design-details-costing-methods.md)  
[Overview](design-details-inventory-costing.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
