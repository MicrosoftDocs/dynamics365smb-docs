---
title: Work with assembly BOMs
description: You create an assembly BOM to specify the components required to put together the item that the BOM represents.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: assembly bom, bills of material, 
ms.search.form: 36, 5870, 5872, 5874
ms.date: 06/13/2024
ms.service: dynamics-365-business-central

---
# Work with assembly BOMs

You use assembly bills of materials (BOMs) to structure parent items that must be assembled from components with little to no resource use. An assembly BOM can be used, for example, to sell a parent item as a kit consisting of component items.

Use assembly orders to make finished items from components in a process that one or more basic resources can perform, which aren't machine or work centers, or without any resources. For example, an assembly process could be to pick two wine bottles and one coffee sack and pack them as a gift item.  

An assembly BOM is the master data that defines which component items go into an assembled end item and which resources are used to assemble the assembly item. When you enter an assembly item and a quantity on an assembly order, the assembly order lines are filled in according to the assembly BOM. The order has one assembly order line per component or resource. Learn more at [Assembly Management](assembly-assemble-items.md).

[!INCLUDE[prod_short](includes/prod_short.md)] also supports production BOMs. Production BOMs differ from assembly BOMs because they involve more complex procedures, such as resource usage, production routing, and work or machine centers. Learn more about the differences at [Work with Bills of Material](inventory-how-work-BOMs.md) and [Create Production BOMs](production-how-to-create-production-boms.md).

## To create an assembly BOM

To define an item that consists of other items, and perhaps the resources that assemble the item, you must create an assembly BOM.  

Assembly BOMs can have multiple levels, which means that a component on the assembly BOM can be an assembly item itself. In that case, the **Assembly BOM** field on the assembly BOM line contains **Yes**.

Special requirements apply to items on assembly BOMs regarding availability. Learn more at [To see the availability of an item by its use in assembly BOMs](inventory-how-availability-overview.md#to-view-the-availability-of-an-item-by-its-use-in-assembly-or-production-boms).

There are two parts to creating an assembly BOM:

- Setting up a new item.
- Defining the BOM structure of the assembly item.

1. Set up a new item. Learn more at [Register New Items](inventory-how-register-new-items.md).

   Proceed to enter components or resources on the assembly BOM.  
2. On the **Item Card** page for an assembly item, choose the **Assembly** action, then choose the **Assembly BOM** action.
3. On the **Assembly BOM** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!TIP]
> Assembly items can have variants, just like any other item, which helps you keep your list of products shorter. Learn more about the feature at [Manage Product Variants](inventory-item-variants.md).

## To edit assembly BOMs

You can edit the lines on an assembly BOM at any time. However, the BOM might be in use by ongoing sales or assemblies of the parent. Changing the BOM might affect those activities. Choose the **Where-Used** action to explore the items that use it and whether sales or assembly orders might be affected.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Items**, then choose the related link.
2. Choose the **Yes** value in the **Assembly BOM** column.
3. On the **Assembly BOM** page, choose the **Edit List** action, then change any field as needed.

## To view components and resources indented according to the BOM structure

From the **Assembly BOM** page, you can open a separate page that shows the components and any resources indented according to their BOM position under the assembly item.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Items**, then choose the related link.
2. Open the card for an assembly item. (The **Assembly BOM** field on the **Items** page contains **Yes**.)
3. On the **Item Card** page, choose the **Assembly** action, then choose the **Assembly BOM** action.
4. On the **Assembly BOM** page, choose the **Show BOM** action.

## To replace the assembly item with its components on document lines

From any sales and purchase document that contains an assembly item, you can use a special action to replace the line for the assembly item with new lines for its components. This action is useful, for example, if you want to sell the components as a kit that represents the assembly item.

The **Explode BOM** action is also available on the **Assembly BOM** page as a way to view subassembly items on an assembly BOM.

> [!CAUTION]  
> When you have used the **Explode BOM** action, you can't easily undo it. You must delete the sales order lines for the components and then reenter a sales order line for the assembly item.

The following procedure is based on a sales invoice. The same steps apply to other sales documents and all purchase documents.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Invoices**, then choose the related link.
2. Open a sales invoice that contains a line for an assembly item.
3. Choose the line for an assembly item, then **Explode BOM** line action.

All fields on the sales invoice line for the assembly item are cleared except for the **Item** and **Description** fields. Complete sales invoice lines are inserted for the components and possible resources that comprise the assembly item.

> [!NOTE]
> The **Picking List by Order** report is also changed to show the components only. This means that a warehouse worker picking the parent item, the assembly item, will not see it in the picking list. Learn more at [Print the Picking List](sales-how-print-picking-list.md).

## To calculate the standard cost of an assembly item

You calculate the unit cost of an assembly item by rolling up the unit cost of each component and resource in the item's assembly BOM.

The unit cost of an assembly BOM always equals the total of the unit costs of its components, including other assembly BOMs, and any resources.  

> [!NOTE]
> [!INCLUDE [bom-standard-cost](includes/bom-standard-cost.md)]

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Items**, then choose the related link.
2. Open the card for an assembly item. (The **Assembly BOM** field on the **Items** page contains **Yes**.)
3. On the **Item Card** page, choose the **Assembly BOM** action.
4. On the **Assembly BOM** page, choose the **Calc. Standard Cost** action.
5. Select one of the following options, then choose the **OK** button.

|Option |Description |
|-------|------------|
|**Top Level**|Calculates the assembly item's standard cost as the total cost of all purchased or assembled items on that assembly BOM regardless of any underlying assembly BOMs.|
|**All Levels**|Calculates the assembly's item standard cost as the sum of:</br></br>* The calculated cost of all underlying assembly BOMs on the assembly BOM.</br>* The cost of all purchased items on the assembly BOM.|

The costs of the items that make up the assembly BOM are copied from the component item cards. The cost of each item is multiplied by the quantity, and the total cost is shown in the **Unit Cost** field on the item card.

You can also calculate and update the standard cost for one or many items on the **Standard Cost Worksheet** page. Learn more at [Updating standard costs with the Standard Cost Worksheet](finance-about-calculating-standard-cost.md#updating-standard-costs-with-the-standard-cost-worksheet).

## Related information

[Register New Items](inventory-how-register-new-items.md)  
[Manage Product Variants](inventory-item-variants.md)  
[View the Availability of Items](inventory-how-availability-overview.md)  
[Inventory](inventory-manage-inventory.md)  
[Work with Bills of Material](inventory-how-work-BOMs.md)  
[Create Production BOMs](production-how-to-create-production-boms.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
