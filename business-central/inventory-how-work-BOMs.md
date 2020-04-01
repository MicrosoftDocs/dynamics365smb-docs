---
title: Work with Bills of Material to Manage Components| Microsoft Docs
description: You create an assembly BOM or production BOM to specify the components or resources required to put together the item that the BOM represents.
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2020
ms.author: sgroespe

---
# Work with Bills of Material
You use bills of materials (BOMs) to structure parent items that must be assembled or produced by resources or machine centers from components. An assembly BOM can also be used to sell a parent item as a kit consisting of its components.

## Assembly BOMs or Production BOMs
You use assembly orders for making end items from components in a simple process that can be performed by one or more basic resources, which are not machine or work centers, or without any resources. For example, an assembly process could be to pick two wine bottles and one coffee sack and then pack them as a gift item.  

An assembly BOM is the master data that defines which component items go into an assembled end item and which resources are used to assemble the assembly item. When you enter an assembly item and a quantity in the header of a new assembly order, then the assembly order lines are automatically filled according to the assembly BOM with one assembly order line per component or resource. For more information, see [Assembly Management](assembly-assemble-items.md).

Assembly BOMs are described in this topic.

You use production orders for making end items from components in a complex process that requires a production routing and work or machine centers, which represent production capacities. For example, a production process could be to cut steel plates in one operation, weld them in the next operation, and paint the end item in the last operation. For more information, see [Manufacturing](production-manage-manufacturing.md).  

A production BOM is the master data that defines a production item and the components that go into it. for assembly items, the production BOM must be certified and assigned to the production item before it can be used in a production order. When you enter the production item on a production order line, either manually or by refreshing the order, then the production BOM content becomes the production order components. For more information, see [Create Production BOMs](production-how-to-create-production-boms.md).  

The concept of resources in production is much more advanced than in assembly management. Work centers and machine centers function as resources, and production steps are represented by operations that are assigned to resources in production routings. For more information, see [Create Routings](production-how-to-create-routings.md).

Both assembly orders and production orders may be linked directly to sales orders. However, you can only use assembly orders to customize the end item directly for a customer request with the sales order.

## To create an assembly BOM
To define a parent item that consists of other items, and potentially of resources required to put the parent together, you must create an assembly BOM.  

Assembly BOMs usually contain items but can also contain one or more resources that are required to put the assembly item together.

Assembly BOMs can have multiple levels, which means that a component on the assembly BOM can be an assembly item itself. In that case, the **Assembly BOM** field on the assembly BOM line contains **Yes**.

Special requirements apply to items on assembly BOMs with regards to availability. For more information, see [To see the availability of an item by its use in assembly BOMs](inventory-how-availability-overview.md#to-view-the-availability-of-an-item-by-its-use-in-assembly-or-production-boms).

There are two parts to creating an assembly BOM:
- Setting up a new item
- Defining the BOM structure of the assembly item.

1. Set up a new item. For more information, see [Register New Items](inventory-how-register-new-items.md).

    Proceed to enter components or resources on the assembly BOM.  
2. On the **Item Card** page for an assembly item, choose the **Assembly** action, and then choose the **Assembly BOM** action.
3. On the **Assembly BOM** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To edit assembly BOMs
You can edit the lines on an assembly BOM at any time. But be aware that the BOM may be in use on ongoing sales or assemblies of the parent, which may be affected by the change. Choose the **Where-Used** action to see in which items it is being used and then whether sales or assembly orders may be affected.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
2. Choose the **Yes** value in the **Assembly BOM** column.
3. On the **Assembly BOM** page, choose the **Edit List** action, and then change any field as needed.

## To view components and resources indented according to the BOM structure
From the **Assembly BOM** page, you can open a separate page that shows the components and any resources indented according to their BOM position under the assembly item.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
2. Open the card for an assembly item. (The **Assembly BOM** field on the **Items** page contains **Yes**.)
3. On the **Item Card** page, choose the **Assembly** action, and then choose the **Assembly BOM** action.
4. On the **Assembly BOM** page, choose the **Show BOM** action.

## To replace the assembly item with its components on document lines
From any sales and purchase document that contains an assembly item, you can use a special function to replace the line for the assembly item with new lines for its components. This function is useful, for example, if you want to sell the components as a kit that represents the assembly item.

**Caution**: When you have used the **Explode BOM** function, you cannot easily undo it. You must delete the sales order lines representing the components and then reenter a sales order line for the assembly item.

The following procedure is based on a sales invoice. The same steps apply to other sales documents and to all purchase documents.

1. In the top right corner, choose the **Search for Page or Report** icon, enter **Sales Invoices**, and then choose the related link.
2. Open a sales invoice that contains a line for an assembly item.
3. Choose the line for an assembly item, and then **Explode BOM** line action.

All fields on the sales invoice line for the assembly item are cleared except for the **Item** and **Description** fields. Complete sales invoice lines are inserted for the components and possible resources that comprise the assembly item.

**Note**: The Explode BOM function is also available on the **Assembly BOM** page.

## To calculate the standard cost of an assembly item
You calculate the unit cost of an assembly item by rolling up the unit cost of each component and resource in the item’s assembly BOM.

You can also calculate and update the standard cost for one or many items on the **Standard Cost Worksheet** page. For more information, see [Update Standard Costs](finance-how-to-update-standard-costs.md).  

The unit cost of an assembly BOM always equals the total of the unit costs of its components, including other assembly BOMs, and any resources.

1. In the top right corner, choose the **Search for Page or Report** icon, enter **Items**, and then choose the related link.
2. Open the card for an assembly item. (The **Assembly BOM** field on the **Items** page contains **Yes**.)
3. On the **Item Card** page, choose the **Assembly** action, and then choose the **Assembly BOM** action.
4. On the **Assembly BOM** page, choose the **Calc. Standard Cost** action.
5. Select one of the following options, and then choose the **OK** button.

|Option |Description |
|-------|------------|
|**Top Level**|Calculates the assembly item's standard cost as the total cost of all purchased or assembled items on that assembly BOM regardless of any underlying assembly BOMs.|
|**All Levels**|Calculates the assembly's item standard cost as the sum of: 1) The calculated cost of all underlying assembly BOMs on the assembly BOM. 2) The cost of all purchased items on the assembly BOM.|



The costs of the items that make up the assembly BOM are copied from the component item cards. The cost of each item is multiplied by the quantity, and the total cost is shown in the **Unit Cost** field on the item card.

## See Also
[Register New Items](inventory-how-register-new-items.md)  
[View the Availability of Items](inventory-how-availability-overview.md)     
[Inventory](inventory-manage-inventory.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
