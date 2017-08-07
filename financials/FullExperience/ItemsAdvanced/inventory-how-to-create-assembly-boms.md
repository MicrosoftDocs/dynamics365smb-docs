---
    title: How to: Create Assembly BOMs | Microsoft Docs
    description: Assembly BOMs specify which components or resources are required to assemble the item that the assembly BOM represents. Assembly BOMs usually contain items but can also contain one or more resources that perform the assembly work. For more information, see Resource Usage Type.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# How to: Create Assembly BOMs
Assembly BOMs specify which components or resources are required to assemble the item that the assembly BOM represents. Assembly BOMs usually contain items but can also contain one or more resources that perform the assembly work. For more information, see Resource Usage Type.  
  
 Assembly BOMs can be multilevel, which means that a component on the assembly BOM can be an assembly item itself. This is specified with the **Yes** value in the **Assembly BOM** field on the assembly BOM line. Multilevel assembly BOMs can have special requirements in certain cases, such as availability, planning, and standard cost calculation. For more information about how multilevel manufacturing or assembly items are handled in planning, see [How to: Run MPS and MRP](../how-to-calculate-the-standard-cost-of-assembly-boms.md).  
  
 When you enter the assembly item on an assembly order header, the assembly BOM components are automatically filled into the assembly order lines and are then ready to be consumed in the assembly process. For more information, see [How to: Assemble Items](../how-to-assemble-items.md).  
  
 There are two steps to creating an assembly BOM:  
  
-   Setting up a new item card.  
  
-   Defining the BOM structure.  
  
### To create an assembly BOM  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Items**, and then choose the related link.  
  
2.  Create a new item. On the **Home** tab, in the **New** group, choose **New**. Fill in the required fields on the item card. For more information, see [How to: Register New Products](../how-to-register-new-products.md).  
  
3.  On the **Navigate** tab, in the **Assembly/Production** group, choose the **Assembly** button, and then choose **Assembly BOM**.  
  
4.  To enter components in the assembly BOM, in the **Type** field, enter **Item**. In the **No.** field, select an item.  
  
    > [!NOTE]  
    >  If the component that you enter is an assembly item, then the **Assembly BOM** field contains **Yes**.  
  
5.  To enter a resource in the assembly BOM, in the **Type** field, enter **Resource**. In  the **No.** field, select a resource.  
  
6.  Leave the **Type** field blank if you want to enter a text on the assembly line, such as to describe an item or an assembly step.  
  
7.  In the **Quantity per** field, define how many units of the item or resource go into the assembly BOM.  
  
8.  Choose the **OK** button.  
  
## See Also  
 Assembly BOM   
 Assembly Order   
 Resource Usage Type   
 [How to: Assemble Items](../how-to-assemble-items.md)   
 [Assembly BOMs or Production BOMs](../assembly-boms-or-production-boms.md)   
 [How to: Calculate the Standard Cost of Assembly BOMs](../how-to-calculate-the-standard-cost-of-assembly-boms.md)   
 [How to: Explode Assembly BOMs](../how-to-explode-assembly-boms.md)   
 [How to: Run MPS and MRP](../how-to-run-mps-and-mrp.md)