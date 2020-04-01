---
    title: How to Plan Picks in Worksheets | Microsoft Docs
    description: If your warehouse is set up to require both pick and shipment processing, the warehouse can choose to operate so that the lines on shipment documents are not automatically transformed into pick instructions, but are made available instead to the pick worksheet.
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
# Plan Picks in Worksheets
If your warehouse is set up to require both pick and shipment processing, the warehouse can choose to operate so that the lines on shipment documents are not automatically transformed into pick instructions, but are made available instead to the pick worksheet.  

> [!NOTE]  
>  If warehouse pick instructions have already been created, and you would like to combine them into one efficient pick instruction, then you must delete the individual warehouse picks. The lines to be picked can now be listed in the worksheet.  

In the pick worksheet, you can set up pick lists for employees that minimize the time the employee has to move about the warehouse picking items. There are fields that contain information about the quantities of items available in the cross-dock bins. This is useful in cross docking situations to plan your work assignments, because application will always propose a pick from a cross-dock bin before any other bin, regardless of the unit of measure. The lines in the worksheet can come from a number of source documents and be sorted by item, shelf number, source document, due date, or ship-to address.  

If you sort by due date, you can choose to delete from the worksheet all lines except those that need immediate attention. The less urgent lines are not deleted as such, but just sent back to the **Pick Selection** worksheet. When you create the pick, the lines have already been sorted by due date, and you can choose to assign the pick to a particular employee.  

> [!NOTE]  
>  Picking for warehouse shipment of items that are assembled to the sales order being shipped follows the same steps as for regular warehouse picks for shipment, as described in this topic. However, the number of pick lines per quantity to ship may be many to one because you pick the components, not the assembly item.  
>   
>  The warehouse pick lines are created for the value in the **Remaining Quantity** field on the lines of the assembly order that is linked to the sales order line that is being shipped. This ensures that all components are picked in one action.  
>   
>  For more information, see “Handling Assemble-to-Order Items in Warehouse Shipments” in Warehouse Shipment.  
>   
>  For information about picking components for assembly orders generally, including situations where the assembly item is not due on a sales shipment, see [Pick for Assembly or Production in Advanced Warehouse Configurations](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md).  

## To plan picks in the worksheet  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Pick Worksheet**, and then choose the related link.  
2.  Choose the **Get Whse. Documents** action.  
3.  Select the shipments for which you want to prepare a pick. You can now sort the lines to some degree, but the sorting you do here will not be carried through to the pick instruction. You can also delete some of the lines to make a more effective pick. For instance, if there are a number of lines with items in cross-dock bins, you might want to create a pick for all the lines associated with these lines. The cross-docked items will be shipped, along with the other items on the shipments, and the cross-dock bins will have space for more incoming items.  
4.  Choose the **Create Pick** action, and fill in the **Create Pick** request page. The sorting you request here will order the pick lines you create. For example, you can create one pick for each zone and sort the lines by bin ranking within each pick.  
5.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Picks**, and then choose the related link. The **Picks** page opens.  
6.  You can now find the pick assignment you just created by selecting the pick with the highest number.  
7.  In the pick, you can still alter, if necessary, the assigned user ID and the way the lines are sorted.  
8.  Choose the **Print** action to print the pick instructions.  
9. After you have performed the pick, choose the **Register** action.  

If the bins have been numbered in a way that mirrors the physical layout of the warehouse, the lines sorted by bin code allow the picker to pick for a number of shipments in one round of the warehouse. The worker takes the required number of items for each shipment line out of each bin and places them along with the other items for the particular shipment. A picker can save a great deal of time by picking for several shipments in one visit to a bin.  

Another effective sorting option is bin ranking, if the physical layout of the warehouse is more according to bin ranking than bin code.  

In the pick worksheet, you can also sort by ship-to address, enabling you to assemble and ship the orders to far-away customers first.  

## See Also
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
