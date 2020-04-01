---
    title: How to Use the Manufacturing Batch Unit of Measure | Microsoft Docs
    description: If an item is stocked in one unit of measure but produced in another, then the production order must be use a manufacturing batch unit of measure to calculate the correct quantity of components. An example of a manufacturing batch unit of measure calculation is when a manufactured item is stocked in pieces but produced in tons.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Work with Manufacturing Batch Units of Measure
If an item is stocked in one unit of measure but produced in another, a production order is created that uses a manufacturing batch unit of measure to calculate the correct quantity of the components during the **Refresh Production Order** batch job. An example of a manufacturing batch unit of measure calculation is when a manufactured item is stocked in pieces but produced in tons.  

## To create a production BOM using a batch unit of measure  
1.  The manufacturing batch unit of measure is set up as an alternative unit of measure on the **Item Units of Measure** page on the item to be produced. The batch unit of measure will not replace the base unit of measure on the item.  
2.  Create a production BOM for the item set up with the manufacturing batch unit of measure. For more information, see [Create Production BOMs](production-how-to-create-production-boms.md).  
3.  In the **Unit of Measure Code** field, select the manufacturing batch unit of measure.  
4.  For each production BOM line, in the **Quantity Per** field, enter the quantity of this component item that is required to create this batch unit of measure.  
5.  Open the **Item Card** for the related item.  

    On the **Replenishment** FastTab, in the **Production BOM No.** field, select the production BOM created above.  
6.  Create a production order header using the item set up with the manufacturing batch unit of measure. For more information, see [Create Production Orders](production-how-to-create-production-orders.md).  
7.  Choose the **Refresh** action, and then choose  the **OK** button.  

On the **Lines** FastTab, choose the **Line** action, and then choose the **Components** action to view the result. The application calculates the correct quantity of the components needed to satisfy the production BOM based on the manufacturing batch unit of measure.  

## To calculate a manufacturing batch unit of measure on a production order  
1.  Create a production order header using the item set up with the manufacturing batch unit of measure.  
2.  In the **Item No.** field in the Production Order line, type the same item number used in the header.  
3.  In the **Quantity** field, enter the same quantity used in the header.  
4.  In the **Unit of Measure Code** field, select the manufacturing batch unit of measure code.  
5.  Choose the **Refresh** action.
6.  On the **Calculate** FastTab, clear the **Lines** check box.  
7.  Choose the **OK** button.  
8.  On the **Lines** FastTab, choose the **Line** action, and then choose the **Components** action to view the result. The correct quantity of the components needed to satisfy the production BOM is calculated based on the manufacturing batch unit of measure.  

## See Also  
[Create Routings](production-how-to-create-routings.md)  
[Create Production BOMs](production-how-to-create-production-boms.md)     
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)    
[Planning](production-planning.md)   
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
