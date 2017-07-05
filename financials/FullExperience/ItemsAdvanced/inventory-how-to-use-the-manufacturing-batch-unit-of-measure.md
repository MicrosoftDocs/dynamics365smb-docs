---
    title: How to: Use the Manufacturing Batch Unit of Measure | Microsoft Docs
    description: If an item is stocked in one unit of measure but produced in another, a production order is created that uses a manufacturing batch unit of measure to calculate the correct quantity of the components during the **Refresh Production Order** batch job. An example of a manufacturing batch unit of measure calculation is when a manufactured item is stocked in pieces but produced in tons.
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
# How to: Use the Manufacturing Batch Unit of Measure
If an item is stocked in one unit of measure but produced in another, a production order is created that uses a manufacturing batch unit of measure to calculate the correct quantity of the components during the **Refresh Production Order** batch job. An example of a manufacturing batch unit of measure calculation is when a manufactured item is stocked in pieces but produced in tons.  
  
#### To create a production BOM using a batch unit of measure  
  
1.  The manufacturing batch unit of measure is set up as an alternative unit of measure in the **Item Units of Measure** window on the item to be produced. The batch unit of measure will not replace the base unit of measure on the item.  
  
    > [!NOTE]  
    >  If it doesn't already exist, you may need to add the manufacturing batch unit of measure code to the **Units of Measure** window. ADD INCLUDE<!--[!INCLUDE[bp_choose_columns](../../includes/bp_choose_columns_md.md)]-->  
  
2.  Create a production BOM for the item set up with the manufacturing batch unit of measure. For more information, see [How to: Create Production BOMs](../how-to-create-production-boms.md).  
  
    1.  In the **Unit of Measure Code** field, select the manufacturing batch unit of measure.  
  
    2.  For each production BOM line, in the **Quantity Per** field, enter the quantity of this component item that is required to create this batch unit of measure.  
  
3.  Open the **Item Card** for the related item.  
  
     On the **Replenishment** FastTab, in the **Production BOM No.** field, select the production BOM created above.  
  
4.  Create a production order header using the item set up with the manufacturing batch unit of measure. For more information, see [How to: Create Production Order Headers](../how-to-create-production-order-headers.md).  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Refresh**, and then choose  the **OK** button.  
  
 On the **Lines** FastTab, choose **Actions**![Action Menu icon](../media/actionmenuicon.png "actionMenuIcon"), choose **Line**, and then choose **Components** to view the result. The program calculates the correct quantity of the components needed to satisfy the production BOM based on the manufacturing batch unit of measure.  
  
#### To calculate a manufacturing batch unit of measure on a production order  
  
1.  Create a production order header using the item set up with the manufacturing batch unit of measure.  
  
2.  In the **Item No.** field in the Production Order line, type the same item number used in the header.  
  
3.  In the **Quantity** field, enter the same quantity used in the header.  
  
4.  In the **Unit of Measure Code** field, select the manufacturing batch unit of measure code.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Refresh**.  
  
    1.  On the **Calculate** FastTab, clear the **Lines** field.  
  
    2.  Choose the **OK** button.  
  
 On the **Lines** FastTab, choose **Actions**![Action Menu icon](../media/actionmenuicon.png "actionMenuIcon"), choose **Line**, and then choose **Components** to view the result. The correct quantity of the components needed to satisfy the production BOM is calculated based on the manufacturing batch unit of measure.  
  
## See Also  
 [How to: Calculate Lines from Production Order Headers](../how-to-calculate-lines-from-production-order-headers.md)   
 [How to: Calculate Production Order Components](../how-to-calculate-production-order-components.md)   
 [About Production Orders](../about-production-orders.md)   
 [How to: Refresh Production Orders](../how-to-refresh-production-orders.md)   
 [Units of Measure](../units-of-measure.md)