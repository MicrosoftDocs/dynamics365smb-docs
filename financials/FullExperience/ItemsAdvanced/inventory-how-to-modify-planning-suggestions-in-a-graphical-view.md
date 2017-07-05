---
    title: How to: Modify Planning Suggestions in a Graphical View | Microsoft Docs
    description: A typical planning activity is to change or add planning worksheet lines to modify the suggested supply orders before you commit them by running the **Carry out Action Message** function. An alternative to doing this in the planning worksheet is to use a graphical view. For more information, see Item Availability by Timeline.
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
# How to: Modify Planning Suggestions in a Graphical View
A typical planning activity is to change or add planning worksheet lines to modify the suggested supply orders before you commit them by running the **Carry out Action Message** function. An alternative to doing this in the planning worksheet is to use a graphical view. For more information, see Item Availability by Timeline.  
  
 In the **Item Availability by Timeline** window, you can modify certain supply orders and suggestions by dragging elements on the x-axis to change quantity or dragging elements on the y-axis to change due date.  
  
 In the **Item Availability by Timeline** window and the **Planning Worksheet** window you can make the following changes:  
  
-   Modify a suggested supply order that only exists as a planning line.  
  
-   Modify an existing supply order that the planning system suggests to change.  
  
-   Create a new suggested supply order and modify it.  
  
 For more information about the planning line types that are shown, see the Description field on the **Event Changes** FastTab.  
  
 When you choose **Save Changes** in the **Item Availability by Timeline** window, the modifications that you have made are copied to the planning or requisition worksheet. You can now implement them using the **Carry Out Action Msg.-Plan.** function.  
  
 The following procedure shows how to modify supply suggestions by drag and drop. As an alternative, you can change the **Due Date** and **Quantity** fields on the **Event Changes** FastTab and immediately see the changes graphically on the **Timeline** FastTab in the **Planning Worksheet** window.  
  
### To modify suggested supply orders in the graphical view  
  
1.  In the **Search** box, enter **Item Availability by Timeline**, and then choose the related link.  
  
2.  The **Item Availability by Timeline** window opens with the item number, location, and variant of the item on the selected planning line prefilled in the **Options** FastTab. The **Timeline** FastTab shows a graphical representation of the item’s projected inventory, including planning suggestions.  
  
3.  Make sure that the **Include Planning Suggestions** field is selected.  
  
4.  Find the suggested supply order that you want to modify. You can identify modifiable elements by the green circle and the disk icon. For more information about the different symbols, see Item Availability by Timeline.  
  
5.  Place the pointer over the green circle until it enlarges and the pointer changes to Move shape (four arrows).  
  
6.  Press and hold the mouse button while you drag the pointer up or down to modify the quantity. Press and hold the mouse button while you drag the pointer left or right to modify the due date.  
  
7.  In addition to moving elements by drag and drop, you can modify planning suggestions by using a number of right-click functions. Right-click on the green circle of a suggested supply element and select one the following functions  
  
    |Function|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../includes/bp_tabledescription_md.md)]-->|  
    |--------------|---------------------------------------|  
    |**Create New Supply**|Creates a new element point where you right-click, which represents a new suggested supply order. It becomes a new line in the planning worksheet when you choose **Save Changes**.<br /><br /> **NOTE:** If the **Location Filter** or **Variant Filter** fields on the **Options** FastTab are empty or have more than one filter value, then the new supply is created and later saved to the planning or requisition worksheet with the following codes:<br /><br /> * If the filter field is empty, then the new supply is created without a location or variant code.<br /><br /> * If more than one filter value is defined, then the new supply is created for the first filter value according to the sorting method.<br /><br /> If you want another variant or location code, then you must manually change it on the new planning line.|  
    |**Auto-Adjust Supply**|Optimizes a new supply that you have created in the graph by making sure that it results in zero inventory before the next supply.|  
    |**Delete Supply**|Deletes the element in the **Timeline** FastTab and deletes the planning line when you choose **Save Changes**. The icon changes to a disk that has a red cross when the supply has been deleted.<br /><br /> **NOTE:** You can only delete a supply of action message type **New**. After you choose **Save Changes**, you must manually delete the planning line in question in the planning or requisition worksheet.|  
  
8.  On the **Actions** tab, in the **General** group, choose **Reload** if you want to reset all the changes that you have made after you last opened the **Item Availability by Timeline** window or selected **Reload**.  
  
9. When the elements are placed where you want them in the diagram, choose **Save Changes** to copy modified quantity and date changes to the planning or requisition lines that represent the graphical elements.  
  
 To implement the supply plan changes, you must follow the resulting action messages from the planning or requisition worksheet. For more information, see Carry Out Action Msg.-Plan..  
  
## See Also  
 Item Availability by Timeline   
 Planning Worksheet   
 Carry Out Action Msg.-Plan.   
 [Design Details: Supply Planning](design-details-supply-planning.md)   
 Location Filter   
 Variant Filter   
 Last Updated   
 Include Blanket Sales Orders   
 Description