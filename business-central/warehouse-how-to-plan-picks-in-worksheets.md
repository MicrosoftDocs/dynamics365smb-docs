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

If your warehouse is set up to require both pick and shipment processing, you can choose make lines on shipment documents available on pick worksheets instead of pick instructions..  

> [!NOTE]  
> If warehouse pick instructions have already been created, and you would like to combine them into one efficient pick instruction, then you must delete the individual warehouse picks. The lines to be picked can now be listed in the worksheet.  

On the **Pick Worksheets** page, you can set up pick lists for employees to make it easier for them to gather items in the warehouse. There are fields that contain information about the quantities of items available in the cross-dock bins. This information is useful in cross-docking situations for planning work assignments because [!INCLUDE[prod_short](includes/prod_short.md)] will always propose a pick from a cross-dock bin first, regardless of the unit of measure. The lines in the worksheet can come several source documents. 

You can sort lines by item, shelf number, source document, due date, or ship-to address. If you sort by due date, you can choose to delete all lines except those that need immediate attention. The less urgent lines are not deleted as such, but just sent back to the **Pick Selection** worksheet. When you create the pick, the lines have already been sorted by due date, and you can choose to assign the pick to an employee.  

> [!NOTE]  
> Picking for the shipment of items that are assembled for the sales order being shipped follows the same steps as for regular warehouse picks for shipments. However, the number of pick lines per quantity to ship may be many-to-one because you pick the components, not the assembly item.  
>
> The warehouse pick lines are created for the value in the **Remaining Quantity** field on the lines of the assembly order that is linked to the sales order line that is being shipped. This ensures that all components are picked in one action. For more information, see [Selling Inventory Items in Assemble-to-Order Flows](assembly-how-to-sell-inventory-items-in-assemble-to-order-flows.md).  
>
> For information about picking components for assembly orders generally, including situations where the assembly item is not due on a sales shipment, see [Pick for Assembly or Production in Advanced Warehouse Configurations](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md).  

## To plan picks in the worksheet

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Pick Worksheet**, and then choose the related link.  
2. Choose the **Get Warehouse Documents** action.  
3. Select the shipments for which you want to prepare a pick. You can sort the lines, but the sorting will not be applied to the pick instruction. You can also delete some of the lines to make a more effective pick. For instance, if there are multiple lines with items that are in cross-dock bins, you might create a pick for all of the lines. The cross-docked items will be shipped, along with the other items on the shipments, and the cross-dock bins will have space for more incoming items.  
4. Choose the **Create Pick** action, and fill in the **Create Pick** page. The sorting you request here will order the pick lines you create. For example, you can create one pick for each zone and sort the lines by bin ranking within each pick.  
5. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Picks**, and then choose the related link. The **Warehouse Picks** page opens.  
6. You can now find the pick assignment by selecting the pick with the highest number.  
7. If needed, you can assign a different user, or sort the lines differently.  
8. Choose the **Print** action to print the pick instructions.  
9. After the pick is completed, choose the **Register** action.  

> [!TIP]
> If your bins are numbered to match the physical layout of your warehouse, sorting lines by bin number can make it easier to pick for several shipments at the same time. If you use bin ranking, sorting by rank can also save you time.  

In the pick worksheet, you can also sort by destination, enabling you to assemble and ship the orders per customer.  

## See Also

[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Assembly Management](assembly-assemble-items.md)  
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]