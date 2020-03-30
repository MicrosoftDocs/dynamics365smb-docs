---
    title: How to Modify Planning Suggestions in a Graphical View | Microsoft Docs
    description: A typical planning activity is to change or add planning worksheet lines to modify the suggested supply orders before you commit them by running the **Carry out Action Message** function. An alternative to doing this in the planning worksheet is to use a graphical view.
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
# Modify Planning Suggestions in a Graphical View
A typical planning activity is to change or add planning worksheet lines to modify the suggested supply orders before you commit them by running the **Carry out Action Message** function. An alternative to doing this in the planning worksheet is to use a graphical view.

On the **Item Availability by Timeline** page, you can modify certain supply orders and suggestions by dragging elements on the x-axis to change quantity or dragging elements on the y-axis to change due date.  

 On the **Item Availability by Timeline** page and the **Planning Worksheet** page you can make the following changes:  

-   Modify a suggested supply order that only exists as a planning line.  
-   Modify an existing supply order that the planning system suggests to change.  
-   Create a new suggested supply order and modify it.  

For more information about the planning line types that are shown, see the Description field on the **Event Changes** FastTab.  

When you choose **Save Changes** on the **Item Availability by Timeline** page, the modifications that you have made are copied to the planning or requisition worksheet. You can now implement them using the **Carry Out Action Msg.-Plan.** function.  

The following procedure shows how to modify supply suggestions by drag and drop. As an alternative, you can change the **Due Date** and **Quantity** fields on the **Event Changes** FastTab and immediately see the changes graphically on the **Timeline** FastTab on the **Planning Worksheet** page.  

## To modify suggested supply orders in the graphical view  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Availability by Timeline**, and then choose the related link.  

    The **Item Availability by Timeline** page opens with the item number, location, and variant of the item on the selected planning line prefilled in the **Options** FastTab. The **Timeline** FastTab shows a graphical representation of the item’s projected inventory, including planning suggestions.  

2.  Make sure that the **Include Planning Suggestions** field is selected.  
3.  Find the suggested supply order that you want to modify. You can identify modifiable elements by the green circle and the disk icon. For more information about the different symbols, see [Symbols and Icons on the Timeline FastTab](production-how-to-modify-planning-suggestions-in-a-graphical-view.md#symbols-and-icons-on-the-timeline-fasttab).  
4.  Place the pointer over the green circle until it enlarges and the pointer changes to Move shape (four arrows).  
5.  Press and hold the mouse button while you drag the pointer up or down to modify the quantity. Press and hold the mouse button while you drag the pointer left or right to modify the due date.  
6.  In addition to moving elements by drag and drop, you can modify planning suggestions by using a number of drop-down menu functions. Access the drop-down menu for the green circle of a suggested supply element and select one the following functions  

    |Function|Description|  
    |--------------|---------------------------------------|  
    |**Create New Supply**|Creates a new element point where you access the drop-down menu, which represents a new suggested supply order. It becomes a new line in the planning worksheet when you choose **Save Changes**.<br /><br /> **NOTE:** If the **Location Filter** or **Variant Filter** fields on the **Options** FastTab are empty or have more than one filter value, then the new supply is created and later saved to the planning or requisition worksheet with the following codes:<br /><br /> * If the filter field is empty, then the new supply is created without a location or variant code.<br /><br /> * If more than one filter value is defined, then the new supply is created for the first filter value according to the sorting method.<br /><br /> If you want another variant or location code, then you must manually change it on the new planning line.|  
    |**Auto-Adjust Supply**|Optimizes a new supply that you have created in the graph by making sure that it results in zero inventory before the next supply.|  
    |**Delete Supply**|Deletes the element in the **Timeline** FastTab and deletes the planning line when you choose **Save Changes**. The icon changes to a disk that has a red cross when the supply has been deleted.<br /><br /> **NOTE:** You can only delete a supply of action message type **New**. After you choose **Save Changes**, you must manually delete the planning line in question in the planning or requisition worksheet.|  

7.  Choose the **Reload** action if you want to reset all the changes that you have made after you last opened the **Item Availability by Timeline** page or selected **Reload**.  
8. When the elements are placed where you want them in the diagram, choose **Save Changes** to copy modified quantity and date changes to the planning or requisition lines that represent the graphical elements.  

To implement the supply plan changes, you must follow the resulting action messages from the planning or requisition worksheet. For more information, see Carry Out Action Msg.-Plan..

## Symbols and Icons on the Timeline FastTab
 |Symbol/Icon|Description|  
 |------------------|---------------------------------------|  
 |Black cross|Orders (both supply and demand).<br /><br /> -   Cannot be modified.<br />-   Visible when the **Show Projected Inventory** field is selected (orange graph).|  
 |Red circle|Existing supply orders that are not in planning suggestions.<br /><br /> -   Cannot be modified.<br />-   Visible when the **Show Projected Inventory** field is selected (orange graph).|  
 |Yellow star|Forecast demand.<br /><br /> -   Cannot be modified.<br />-   Visible when the **Forecast Name** field has a value.<br /><br /> When both the **Show Projected Inventory** and the **Include Planning Suggestions** fields are selected, then each yellow star has a linked counterpart in the opposite graph. This illustrates how a suggested supply fulfills the forecasted demand.|  
 |Green circle with an icon shaped as a disk that has a red cross|Suggested supply order with action message *Cancel*.<br /><br /> -   Cannot be modified.<br />-   Visible when the **Include Planning Suggestions** field is selected (green graph).|  
 |Green circle with an icon shaped as a disk that has a star|Suggested supply orders with action message *New*.<br /><br /> -   Can be modified.<br />-   Visible when the **Include Planning Suggestions** field is selected (green graph).|  
 |Green circle with an icon shaped as a disk that has one or two arrows|Suggested supply orders with action message *Reschedule*, *Change Qty.*, or *Resched. and Chg. Qty.*<br /><br /> -   Can be modified.<br />-   Visible when the **Include Planning Suggestions** field is selected (green graph).<br /><br /> The arrows reflect the direction of the planning suggestion. For example, a left arrow together with an up arrow reflects a *Resched. and Chg. Qty.* action message that consists of a backward rescheduling and a quantity increase.|  

When you access the drop-down menu for the **Timeline** FastTab, the following functions appear depending what you choose  

 |Function|Description|  
 |--------------|---------------------------------------|  
 |**Create New Supply**|Creates a new element on the point where you access the drop-down menu, which represents a new suggested supply order. It becomes a new line in the planning worksheet when you choose **Save Changes** on the **Process** tab.<br /><br /> Any filter values that are defined in the **Location Filter** or **Variant Filter** fields on the **Options** FastTab will be applied to the new supply order. **Note:**  If the filter fields are empty or have more than one filter value, then the new supply order is created by using the following codes: <ul><li>If the filter field is empty, then the new supply is created without a location or variant code.</li><li>If more than one filter value is defined, then the new supply is created by using the first filter value according to the sorting order.</li></ul> If you want another variant or location code in the new supply order, then you must manually change it on the new planning line.|  
 |**Auto-Adjust Supply**|Optimizes a new supply that you have created in the graph by making sure that it creates zero inventory before the next supply.|  
 |**Delete Supply**|Deletes the element in the **Timeline** FastTab and deletes the planning line when you choose **Save Changes** on the **Process** tab. The icon changes to a disk that has a red cross when the supply has been deleted. **Note:**  You can only delete a supply of action message type *New*. After you choose **Save Changes** on the **Process** tab, you must manually delete the planning line in question in the planning or requisition worksheet.|  
 |**Show Document**|Opens the order, planning line, or forecast that the element represents.|  
 |**Zoom Out (Ctrl++)**|Makes the scale of the x-axis larger, so that fewer days are shown. **Note:**  You can also do this by pressing Ctrl + scroll mouse wheel.|  
 |**Zoom In (Ctrl+-)**|Makes the scale of the x-axis smaller, so that more days are shown. **Note:**  You can also do this by pressing Ctrl + scroll mouse wheel.|  
 |**Reset Zoom (Ctrl+0)**|Reverts the scale of the x-axis to what was used before you zoomed.|  

In addition to the keyboard actions that were mentioned earlier, you can also use the following keyboard actions in the **TimeLine** FastTab.  

 |Keyboard Action|Description|  
 |---------------------|---------------------------------------|  
 |Ctrl + scroll mouse wheel|Changes the scale of the x-axis.|  
 |Select an element, then press Shift+Arrow|Moves the element in the direction of the arrow stroke.|  
 |Tab|Moves to the next element.|  
 |Shift+Tab|Moves to the previous element.|  
 |While moving an element, press Esc.|Cancels the move. **Note:**  Does not work if you have released the mouse button.|

## See Also  
[Planning](production-planning.md)   
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)    
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Design Details: Supply Planning](design-details-supply-planning.md)   
[Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
