---
    title: How to Plan Warehouse Movements in Worksheets | Microsoft Docs
    description: Plan movements in the worksheet using a bin replenishment function or manually planning the lines that you want to create as movement instructions.
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
# Plan Warehouse Movements in Worksheets
Plan movements in the worksheet using a bin replenishment function or manually planning the lines that you want to create as movement instructions.  

## To calculate a replenishment movement  
As the warehouse ships items out to customers, the bins with the highest bin rankings contain fewer and fewer items. To fill up these high-ranking pick bins with items from other bins, run the **Calculate Bin Replenishment** function on the **Movement Worksheet** page

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Movement Worksheet**, and then choose the related link.  
2.  Choose the **Calculate Bin Replenishment** action.  

    [!INCLUDE[d365fin](includes/d365fin_md.md)] creates lines that indicate precisely how you should move items from the low-ranking bins to the higher-ranking bins.  

    > [!NOTE]  
    >  A movement is suggested according to FEFO when you activate the **Create Movement** function if the following conditions are met for an item:  
    >   
    >  -   The item has an expiration date.  
    > -   The **Pick According to FEFO** check box on the location card is selected.  
    > -   The **Bin Mandatory** check box on the location card is selected.  
    > -   The **From Zone** and **From Bin** fields are blank.  

    For more information, see [Picking by FEFO](warehouse-picking-by-fefo.md).  

3.  Look through the lines and change them if necessary, or delete some of them if there is not enough time to perform them all.  
4.  Choose the **Create Movement** action to make a warehouse instruction for action by warehouse employees.  

## To move the entire contents of one or more bins by using the Get Bin Content function  
You can also use the movement worksheet to plan other movement of inventory within the warehouse. For example, when you want to place items in a bin for quality control, you can use the movement worksheet to plan this action and then create a movement to make instructions for an employee.  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Movement Worksheet**, and then choose the related link.  
2.  Choose the **Get Bin Content** action. Use the request page to filter which bins and items you want to appear on the movement worksheet lines.  
3.  Fill in the relevant fields in the batch job request page. For example, if you want to see the bin content of all the bins in a certain zone at the location, fill in the **Zone Code** field. If you want to retrieve lines for each bin that contains a particular item, fill in the **Item No.** field.  

    > [!NOTE]  
    >  You cannot manually move items in or out of a bin of bin type RECEIVE, because items that are in a RECEIVE-type bin must be registered as being put away before they are part of available inventory.  

4.  If you are retrieving many lines, choose **Sort** to select a sorting method to determine the order the lines will appear in the worksheet, and then choose the **OK** button.  

    > [!NOTE]  
    >  Movement lines are retrieved according to FEFO when you activate the **Get Bin Content** function if the following conditions are met for an item:  
    >   
    >  -   The item has an expiration date.  
    > -   The **Pick According to FEFO** check box on the location card is selected.  
    > -   The **Bin Mandatory** check box on the location card is selected.  
    > -   The **From Zone** and **From Bin** fields are blank.  

5.  Complete some of the retrieved lines to reflect the changes you want to make. For each item that you want to move, you must fill in the **Item No.**, **From Bin Code**, **To Bin Code**, and **Quantity** fields.  
6.  Delete the incomplete lines that you used for information.  
7.  Once the movement worksheet lines accurately reflect how the movement action should be carried out by the warehouse employee, choose the **Create Movement** action to create the instructions for the employee.  

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
