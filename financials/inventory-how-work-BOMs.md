---
title: 'How to: Work with Bills of Materials| Microsoft Docs'
description: 'Assembly BOMs specify which components or resources are required to assemble the item that the assembly BOM represents. Assembly BOMs usually contain items but can also contain one or more resources that perform the assembly work.'
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: project-madeira
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/10/2017
ms.author: sgroespe

---
# How to: Work with Bills of Materials
You use bills of materials (BOMs) to structure parent items that you sell as kits consisting of the parent's components or that you assemble to order or to stock.

In [!INCLUDE[d365fin](includes/d365fin_md.md)], a bill of materials is referred to as an assembly BOM. Assembly BOMs specify which components are contained in a parent item. In this documentation, a parent item is referred to as an assembly item.

Assembly BOMs usually contain items but can also contain one or more resources that are required to put the assembly item together.

Assembly BOMs can have multiple levels, which means that a component on the assembly BOM can be an assembly item itself. In that case, the **Assembly BOM** field on the assembly BOM line contains **Yes**.

Special requirements apply to items on assembly BOMs with regards to availability and standard cost calculation. For more information, see the "To see the availability of an item by its use in assembly BOMs" section in [How to: Get an Availability Overview](inventory-how-availability-overview.md) and the "To calculate the standard cost of assembly BOMs" section in this topic.

**Note**: This functionality requires that your experience is set to **Suite**. For more information, see [Customizing Your Financials Experience](ui-experiences.md).

## To create an assembly BOM
To define a parent item that consists of other items, and potentially of resources required to put the parent together, you must create an assembly BOM.  

There are two parts to creating an assembly BOM:
- Setting up a new item
- Defining the BOM structure of the assembly item.

1. Set up a new item. For more information, see [How to: Register New Products](inventory-how-register-new-products.md).

    Proceed to enter components or resources on the assembly BOM.  
2. In the **Item Card** window for an assembly item, choose the **Assembly** action, and then choose the **Assembly BOM** action.
3. In the **Assembly BOM** window, fill in the fields as necessary. Choose a field to read a short description of the field or link to more information.

## To view the components of an assembly item indented according to the BOM structure
From the **Assembly BOM** window, you can open a separate window that shows the components and any resources indented according to their BOM position under the assembly item.

1. In the top right corner, choose the **Search for Page or Report** icon, enter **Items**, and then choose the related link.
2. Open the card for an assembly item. (The **Assembly BOM** field in the **Items** window contains **Yes**.)
3. In the **Item Card** window, choose the **Assembly** action, and then choose the **Assembly BOM** action.
4. In the **Assembly BOM** window, choose the **Show BOM** action.

## To replace the assembly item with its components on document lines
From any sales and purchase document that contains an assembly item, you can use a special function to replace the line for the assembly item with new lines for its components. This function is useful, for example, if you want to sell the components as a kit that represents the assembly item.

**Caution**: When you have used the **Explode BOM** function, you cannot easily undo it. You must delete the sales order lines representing the components and then reenter a sales order line for the assembly item.

The following procedure is based on a sales invoice. The same steps apply to other sales documents and to all purchase documents.

1. In the top right corner, choose the **Search for Page or Report** icon, enter **Sales Invoices**, and then choose the related link.
2. Open a sales invoice that contains a line for an assembly item.
3. Choose the line for an assembly item, and then **Explode BOM** line action.

All fields on the sales invoice line for the assembly item are cleared except for the **Item** and **Description** fields. Complete sales invoice lines are inserted for the components and possible resources that comprise the assembly item.

**Note**: The Explode BOM function is also available in the **Assembly BOM** window.

## To calculate the standard cost of an assembly item
You calculate the unit cost of an assembly item by rolling up the unit cost of each component and resource in the item’s assembly BOM.

The unit cost of an assembly BOM always equals the total of the unit costs of its components, including other assembly BOMs, and any resources.

1. In the top right corner, choose the **Search for Page or Report** icon, enter **Items**, and then choose the related link.
2. Open the card for an assembly item. (The **Assembly BOM** field in the **Items** window contains **Yes**.)
3. In the **Item Card** window, choose the **Assembly** action, and then choose the **Assembly BOM** action.
4. In the **Assembly BOM** window, choose the **Calc. Standard Cost** action.
5. Select one of the following options.


|Option |Description |
|-------|------------|
|**Top Level**|Calculates the assembly item's standard cost as the total cost of all purchased or assembled items on that assembly BOM regardless of any underlying assembly BOMs.|
|**All Levels**|Calculates the assembly's item standard cost as the sum of: 1) The calculated cost of all underlying assembly BOMs on the assembly BOM. 2) The cost of all purchased items on the assembly BOM.|

6. Choose the **OK** button.

The costs of the items that make up the assembly BOM are copied from the component item cards. The cost of each item is multiplied by the quantity, and the total cost is shown in the **Unit Cost** field on the item card. **NB: MAY NOT BE TRUE IN FINANCIALS**.

## See Also
[How to: Register New Products](inventory-how-register-new-products.md)  
[How to: Get an Availability Overview](inventory-how-availability-overview.md)   
[Inventory](inventory-manage-inventory.md)  
[Working With [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](ui-work-product.md)
