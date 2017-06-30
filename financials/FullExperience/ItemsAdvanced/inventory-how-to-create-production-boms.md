---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# How to: Create Production BOMs
A production BOM holds master data that describes the components and subassemblies used in the production of a parent item. Once a production order is created for that parent item, its production BOM will govern the calculation of material requirements as represented in the **Prod. Order Components** window.  
  
 **Prerequisites**  
  
-   Item cards are created for parent items and their components. For more information, see [How to: Register New Products](../how-to-register-new-products.md).  
  
-   Gather all data about item structures: Top-level items, subassemblies, components, and their interrelation.  
  
### To fill in the production BOM header  
  
1.  In the **Search** box, enter **Production BOM**, and then choose the related link.  
  
2.  Create a new production BOM.  
  
3.  In the **No.** field, number the production BOM, for example, the same as the parent item.  
  
4.  In the **Description** field, name the production BOM, for example, the same as the parent item.  
  
5.  In the **Unit of Measure Code** field, select the parent item’s unit of measure code.  
  
6.  To edit the BOM, set the **Status** field to **New** or **Under Development**. To activate it, set the **Status** field to **Certified**.  
  
### To fill in the production BOM lines  
  
1.  In the **Type** field, select whether the item on this BOM line is an ordinary item or a production BOM. If the item on the line is a production BOM, then it must already exist as a certified production BOM.  
  
2.  In the **No.** field, look up and select the item or production BOM in question, or type it in the field.  
  
3.  In the **Quantity Per** field, enter how many units of the item go into the parent item, for example, 4 wheels for 1 car.  
  
4.  In the **Scrap %** field you can enter a fixed percentage of components that are scrapped during production. When the components are ready to be consumed in a released production order, this percentage will be added to the expected quantity in the **Consumption Quantity** field in a production journal. For more information, see [How to: Register Consumption and Output](../how-to-register-consumption-and-output.md).  
  
    > [!NOTE]  
    >  This scrap percentage represents components that are scrapped during production when picking from inventory, whereas the scrap percentage on routing lines represents scrapped output before putting on inventory.  
  
5.  In the **Routing Link Code** field, enter a code to connect the component to a specific operation. ADD INCLUDE<!--[!INCLUDE[bp_choose_columns](../../includes/bp_choose_columns_md.md)]-->  
  
     Routing links between operations and components ensure that material consumption is not posted until it has actually been consumed. In addition, routing links provide a process view in the **Production Journal** window where components are listed under the linked operation. For more information, see [How to: Create Routing Links](../how-to-create-routing-links.md).  
  
6.  To copy lines from an existing production BOM, on the **Actions** tab, in the **Functions** group, choose **Copy BOM** to select existing lines.  
  
7.  Certify the production BOM.  
  
8.  You can now attach the new production BOM to the card of the parent item in question. For more information, see [How to: Register New Products](../how-to-register-new-products.md).  
  
> [!NOTE]  
>  To recalculate the item’s standard cost from the item card, on the **Navigate** tab, in the **Bill of Material** group, choose **Manufacturing**, and then choose **Calc. Standard Cost**.  
  
## See Also  
 [Define Material and Process Structure](../define-material-and-process-structure.md)   
 [Assembly BOMs or Production BOMs](../assembly-boms-or-production-boms.md)