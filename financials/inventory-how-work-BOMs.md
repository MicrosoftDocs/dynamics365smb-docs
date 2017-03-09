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
ms.date: 02/18/2017
ms.author: sgroespe

---
# How to: Work with Bills of Materials
You use bills of materials (BOMs) to structure parent items that you sell as kits consisting of the parent's components or that you assemble to order or to stock.

In [!INCLUDE[d365fin](includes/d365fin_md.md)], a bill of materials is referred to as an "assembly BOM". Assembly BOMs specify which components are contained in parent items. In this documentation, a parent item is referred to as an "assembly item".

Assembly BOMs usually contain items but can also contain one or more resources that are required to put the assembly item together.

Assembly BOMs can have multiple levels, which means that a component on the assembly BOM can be an assembly item itself. In that case, the **Assembly BOM** field on the assembly BOM line contains **Yes**.

Special requirements apply to items on assembly BOMs with regards to availability. For more information, see the "To see the availability of an item by its use in assembly BOMs" section in [How to: Get an Availability Overview](inventory-how-availability-overview.md).

**Note**: This functionality requires that your experience is set to **Suite**. For more information, see [Customizing Your Financials Experience](ui-experiences.md).

## To create an assembly BOM
To define a parent item that consists of other items, and potentially of resources required to put the parent together, you must create an assembly BOM.  

There are two parts to creating an assembly BOM:
- Setting up a new item
- Defining the BOM structure of the assembly item.

1. Set up a new item. For more information, see [How to: Register New Items](inventory-how-register-new-items.md).

    Proceed to enter components or resources on the assembly BOM.  
2. In the **Item Card** window for an assembly item, choose the **Assembly** action, and then choose the **Assembly BOM** action.
3. In the **Assembly BOM** window, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To view the components of an assembly item indented according to the BOM structure
From the **Assembly BOM** window, you can open a separate window that shows the components and any resources indented according to their BOM position under the assembly item.

1. In the top right corner, choose the **Search for Page or Report** icon, enter **Items**, and then choose the related link.
2. Open the card for an assembly item. (The **Assembly BOM** field in the **Items** window contains **Yes**.)
3. In the **Item Card** window, choose the **Assembly** action, and then choose the **Assembly BOM** action.
4. In the **Assembly BOM** window, choose the **Show BOM** action.

## See Also
[How to: Register New Items](inventory-how-register-new-items.md)  
[How to: Get an Availability Overview](inventory-how-availability-overview.md)     
[Inventory](inventory-manage-inventory.md)  
[Working With [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](ui-work-product.md)
