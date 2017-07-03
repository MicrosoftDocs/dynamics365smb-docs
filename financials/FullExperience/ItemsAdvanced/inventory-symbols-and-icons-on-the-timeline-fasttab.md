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
# Symbols and Icons on the Timeline FastTab
|Symbol/Icon|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../includes/bp_tabledescription_md.md)]-->|  
|------------------|---------------------------------------|  
|Black cross|Orders (both supply and demand).<br /><br /> -   Cannot be modified.<br />-   Visible when the **Show Projected Inventory** field is selected (orange graph).|  
|Red circle|Existing supply orders that are not in planning suggestions.<br /><br /> -   Cannot be modified.<br />-   Visible when the **Show Projected Inventory** field is selected (orange graph).|  
|Yellow star|Forecast demand.<br /><br /> -   Cannot be modified.<br />-   Visible when the **Forecast Name** field has a value.<br /><br /> When both the **Show Projected Inventory** and the **Include Planning Suggestions** fields are selected, then each yellow star has a linked counterpart in the opposite graph. This illustrates how a suggested supply fulfills the forecasted demand.|  
|Green circle with an icon shaped as a disk that has a red cross|Suggested supply order with action message *Cancel*.<br /><br /> -   Cannot be modified.<br />-   Visible when the **Include Planning Suggestions** field is selected (green graph).|  
|Green circle with an icon shaped as a disk that has a star|Suggested supply orders with action message *New*.<br /><br /> -   Can be modified.<br />-   Visible when the **Include Planning Suggestions** field is selected (green graph).|  
|Green circle with an icon shaped as a disk that has one or two arrows|Suggested supply orders with action message *Reschedule*, *Change Qty.*, or *Resched. and Chg. Qty.*<br /><br /> -   Can be modified.<br />-   Visible when the **Include Planning Suggestions** field is selected (green graph).<br /><br /> The arrows reflect the direction of the planning suggestion. For example, a left arrow together with an up arrow reflects a *Resched. and Chg. Qty.* action message that consists of a backward rescheduling and a quantity increase.|  
||  
  
 When you right-click the **Timeline** FastTab, the following functions appear depending where you click.  
  
|Function|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../includes/bp_tabledescription_md.md)]-->|  
|--------------|---------------------------------------|  
|**Create New Supply**|Creates a new element on the point where you right-click, which represents a new suggested supply order. It becomes a new line in the planning worksheet when you choose **Save Changes** on the **Process** tab.<br /><br /> Any filter values that are defined in the **Location Filter** or **Variant Filter** fields on the **Options** FastTab will be applied to the new supply order. **Note:**  If the filter fields are empty or have more than one filter value, then the new supply order is created by using the following codes: <ul><li>If the filter field is empty, then the new supply is created without a location or variant code.</li><li>If more than one filter value is defined, then the new supply is created by using the first filter value according to the sorting order.</li></ul> If you want another variant or location code in the new supply order, then you must manually change it on the new planning line.|  
|**Auto-Adjust Supply**|Optimizes a new supply that you have created in the graph by making sure that it creates zero inventory before the next supply.|  
|**Delete Supply**|Deletes the element in the **Timeline** FastTab and deletes the planning line when you choose **Save Changes** on the **Process** tab. The icon changes to a disk that has a red cross when the supply has been deleted. **Note:**  You can only delete a supply of action message type *New*. After you choose **Save Changes** on the **Process** tab, you must manually delete the planning line in question in the planning or requisition worksheet.|  
|**Show Document**|Opens the order, planning line, or forecast that the element represents.|  
|**Zoom Out (Ctrl++)**|Makes the scale of the x-axis larger, so that fewer days are shown. **Note:**  You can also do this by pressing Ctrl + scroll mouse wheel.|  
|**Zoom In (Ctrl+-)**|Makes the scale of the x-axis smaller, so that more days are shown. **Note:**  You can also do this by pressing Ctrl + scroll mouse wheel.|  
|**Reset Zoom (Ctrl+0)**|Reverts the scale of the x-axis to what was used before you zoomed.|  
  
 In addition to the keyboard actions that were mentioned earlier, you can also use the following keyboard actions in the **TimeLine** FastTab.  
  
|Keyboard action|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../includes/bp_tabledescription_md.md)]-->|  
|---------------------|---------------------------------------|  
|Ctrl + scroll mouse wheel|Changes the scale of the x-axis.|  
|Select an element, then press Shift+Arrow|Moves the element in the direction of the arrow stroke.|  
|Tab|Moves to the next element.|  
|Shift+Tab|Moves to the previous element.|  
|While moving an element, press Esc.|Cancels the move. **Note:**  Does not work if you have released the mouse button.|  
  
 To learn how to drag elements inside the **Timeline** FastTab, see [How to: Modify Planning Suggestions in a Graphical View](../how-to-modify-planning-suggestions-in-a-graphical-view.md).  
  
## See Also  
 Item Availability by Timeline