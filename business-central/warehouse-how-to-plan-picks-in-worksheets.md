---
    title: How to Plan Picks in Worksheets
    description: Learn how lines on shipment documents can be made available on picking worksheets for warehouse workers.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 10/13/2021
    ms.author: edupont

---
# Plan Picks in Worksheets

If your warehouse is set up to require both pick and shipment processing, you can choose to make lines on shipment documents available on pick worksheets instead of pick instructions.  

> [!NOTE]  
> If warehouse pick instructions have already been created, and you want to combine them into one pick instruction, you must delete the individual warehouse picks. The lines to be picked can now be listed on a pick worksheet.  

On the **Pick Worksheets** page, you can set up pick lists that help employees gather items in the warehouse. The page shows the quantities available in cross-dock bins, which is useful for planning work assignments in cross-docking situations. [!INCLUDE[prod_short](includes/prod_short.md)] will always propose a pick from a cross-dock bin first. The lines in the worksheet can come from several source documents. For example, they might come from more than one sales orders. 

> [!NOTE]  
> Picking items that are assembled for a sales order being shipped follows the same steps as for regular warehouse picks for shipments. However, the number of pick lines per quantity to ship may be many-to-one because you pick the components, not the assembly item.  
>
> The warehouse pick lines are created for the value in the **Remaining Quantity** field on the lines of the assembly order that is linked to the sales order line that is being shipped. This ensures that all components are picked in one action. For more information, see [Selling Inventory Items in Assemble-to-Order Flows](assembly-how-to-sell-inventory-items-in-assemble-to-order-flows.md).  
>
> For information about picking components for assembly orders generally, including situations where the assembly item is not due on a sales shipment, see [Pick for Assembly or Production in Advanced Warehouse Configurations](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md).  

## Sorting Lines on a Pick Worksheet
You can sort lines by item, shelf number, source document, due date, or destination. Here are some examples of how sorting can be useful.

* If you sort by due date, you can choose to delete all lines except those that need immediate attention. The less urgent lines are not deleted as such, but just sent back to the **Pick Selection** worksheet. When you create the pick, the lines have already been sorted by due date, and you can choose to assign the pick to an employee.
* If your bins are numbered to match the physical layout of your warehouse, sorting lines by bin number can make it easier to pick for several shipments at the same time. 
* If you use bin ranking, sorting by rank can save some time. 
* You can sort by destination, enabling you to assemble and ship orders per customer.

## To plan picks in the worksheet

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Pick Worksheet**, and then choose the related link.  
2. Choose the **Get Warehouse Documents** action.  
3. Select the shipments for which you want to prepare a pick. You can sort the lines, but the sorting won't be applied to the pick instruction. You can also delete some of the lines to make a more effective pick. For example, if there are multiple lines with items that are in cross-dock bins, you might create a pick for all of the lines. The cross-docked items will be shipped, along with the other items on the shipments, and the cross-dock bins will have space for more incoming items.  
4. Choose the **Create Pick** action, and fill in the **Create Pick** page. The sorting you request here will order the pick lines you create. For example, you can create one pick for each zone and sort the lines by bin ranking within each pick.  
5. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Picks**, and then choose the related link. The **Warehouse Picks** page opens.  
6. You can now find the pick assignment by selecting the pick with the highest number.  
7. If needed, you can assign a different user, or sort the lines differently.  
8. Choose the **Print** action to print the pick instructions.  
9. After the pick is completed, choose the **Register** action.  

## See Also

[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Assembly Management](assembly-assemble-items.md)  
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]