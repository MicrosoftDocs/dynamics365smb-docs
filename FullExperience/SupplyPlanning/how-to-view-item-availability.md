---
title: "How to: View Item Availability"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "planning, item availability"
  - "items, availability"
  - "worksheets, viewing items"
  - "planning, worksheets"
  - "items, viewing"
ms.assetid: 9baf5593-2ce3-482e-937a-0d18182bc90d
caps.latest.revision: 20
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: View Item Availability
The follow table shows the various ways you can view an item’s availability.  
  
|Organized by|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
|------------------|---------------------------------------|  
|Event|To view summarized or detailed availability figures on dates when supply or demand events change the item’s actual, projected, forecasted, or suggested inventory. **Note:**  You can choose **Calculate** to include any availability changes that occurred since you last opened or calculated the window.|  
|Period|To view actual and projected availability figures in a calendar format that you can filter by different periods.|  
|Variant|To view actual and projected availability figures grouped according to variant code.|  
|Location|To view actual and projected availability figures grouped according to location code.|  
|BOM Level|To see how many parent items you are able to make, by assembly or production, based on the availability of components and lower\-level parents.|  
|Timeline|To see a graphical view of an item’s projected inventory based on future supply and demand events, with or without planning suggestions. The result is a graphical representation of the inventory profile. **Note:**  You can change planning suggestions by dragging elements across the timeline and then save them back to the planning worksheet. For more information, see [How to: Modify Planning Suggestions in a Graphical View](../DesignAndEngineering/how-to-modify-planning-suggestions-in-a-graphical-view.md).|  
  
 You can open five of these different views as separate windows from all application areas where items are handled, such as item cards, planning or requisition lines, and any kind of order line or component line. The **\($ N\_5540 Item Availability Timeline $\)** window can only be opened from item cards and planning or requisition lines.  
  
 When the window opens, it shows availability figures that are filtered on the dataset that the window is opened from, which includes the item number, location code, variant code, and date of the document line, journal line, or item card.  
  
 You can copy the date, location code, or variant code from a selected line in the window to the document line that you opened the window from. For more information, see [To insert a different date, location, or variant from the availability view](../OperationsPlanning/how-to-view-item-availability.md#BKMK_Toinsertadifferentdatelocationorvariantfromtheavailabilityview).  
  
 The first five of the following procedures show how to view item availability from a sales order line. The last procedure shows how to open the **Item Availability by Timeline** window from a planning line. The steps are similar when you open the availability views from other item document lines, such as a sales order line.  
  
### To view item availability by event  
  
1.  In the **Search** box, enter **\($ N\_42 Sales Order $\)**, and then choose the related link.  
  
2.  Open the sales order you want to view. On the **Lines** FastTab, select the line that contains the item that you want to see availability for.  
  
     The item availability information that is shown in the window varies depending on where you open it from. If you open the window from an item card, then it shows the item’s complete availability over time for all locations and variants. If you open the window from a document line, then it shows the item’s availability over time and filtered on any location or variant that is used on the document line.  
  
3.  On the **Lines** FastTab, choose **Actions**, choose **Line**, choose **Item Availability by**, and then choose **Event**.  
  
     The window shows one expandable line for each period in which a supply or demand event changes the item’s availability. The **Period Start** field on expandable lines holds the date of the first day of the event.  
  
4.  View the availability figures in the different quantity fields for each line.  
  
5.  On the **Home** tab, in the **Process** group, choose **Recalculate** regularly to make sure that you are viewing the latest information that includes any updates from other users.  
  
6.  To see details about the event for a given line, select the line, and then on the **Home** tab, in the **Process** group, choose **Show Document**.  
  
    > [!NOTE]  
    >  If you choose **Show Document** for an availability line that has a value in the **Suggested Projected Inventory** field, then the uncommitted supply order that is suggested in the planning worksheet opens.  
  
### To view item availability by period  
  
1.  In the **Search** box, enter **\($ N\_42 Sales Order $\)**, and then choose the related link.  
  
2.  Open the sales order you want, and then on the **Lines** FastTab, select the line that contains the item that you want to see availability for.  
  
3.  Choose **Actions**, choose **Line**, choose **Item Availability by**, and then choose **Period**.  
  
     The window shows availability in a calendar\-like format where each row represents a period. Unlike the **Availability by Events** window, this window shows all periods even if they have no availability figures. You may have to filter and browse in the window to find the availability figures that you want to see.  
  
4.  In the **View by** field, select the length of the time period that you want to view.  
  
5.  In the **View as** field, select one of the following options for how you want availability figures to be displayed.  
  
    |[!INCLUDE[bp_tableoption](../ApplicationDesign/includes/bp_tableoption_md.md)]|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |----------------------------------|---------------------------------------|  
    |**Net Change**|Displays the net change in availability in the selected time interval.|  
    |**Balance at Date**|Displays the availability on the last day of the selected time interval.|  
  
6.  View the availability figures in the different quantity fields for each line.  
  
### To view item availability by variant  
  
1.  In the **Search** box, enter **\($ N\_42 Sales Order $\)**, and then choose the related link.  
  
2.  Open the sales order you want, and then on the **Lines** FastTab, select the line that contains the item that you want to see availability for.  
  
3.  On the **Lines** FastTab, choose **Actions**, choose **Line**, choose **Item Availability By**, and then choose **Variant**.  
  
     The window shows availability for every variant that exists for the item. The window is empty if no variants exist for the item.  
  
4.  In the **View by** field, select the length of the time period that you want to view.  
  
5.  View the availability figures in the different quantity fields for each line.  
  
### To view item availability by location  
  
1.  In the **Search** box, enter **\($ N\_42 Sales Order $\)**, and then choose the related link.  
  
2.  Open the sales order you want, and then on the **Lines** FastTab, select the line that contains the item that you want to see availability for.  
  
3.  On the **Lines** FastTab, choose **Actions**, choose **Line**, choose **Item Availability By**, and then choose **Location**.  
  
     The window shows availability in for each location that is set up.  
  
4.  In the **View by** field, select the length of the time period that you want to view.  
  
5.  In the **View as** field, select one of the following options for how you want availability figures to be displayed.  
  
    |[!INCLUDE[bp_tableoption](../ApplicationDesign/includes/bp_tableoption_md.md)]|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |----------------------------------|---------------------------------------|  
    |**Net Change**|Displays the net change in availability in the selected time interval.|  
    |**Balance at Date**|Displays the availability on the last day of the selected time interval.|  
  
6.  View the availability figures in the different quantity fields for each line.  
  
 You may want to change a date, location, or variant according to the availability view. In the following procedure, you change the date on a sales order line by choosing the **OK** button in the **Item Availability by Periods** window.  
  
##  <a name="BKMK_Toinsertadifferentdatelocationorvariantfromtheavailabilityview"></a> To insert a different date, location, or variant from the availability view  
  
1.  In the **Search** box, enter **\($ N\_42 Sales Order $\)**, and then choose the related link.  
  
2.  Open the sales order you want, and then on the **Lines** FastTab, select the line that has a shipment date that you want to change according to availability.  
  
3.  Choose **Actions**, choose **Line**, choose **Item Availability by**, and then choose **Period**.  
  
4.  Select the line with the date that you want to insert, and then choose the **OK** button. The **Item Availability by Periods** window closes, and a dialog box that asks if you want to change the shipment date opens.  
  
    -   If you want to insert the date, then choose the **Yes** button to insert the new date into the **Shipment Date** field on the sales line.  
  
    -   If you only want to use the window to view availability and do not want to insert a different date, then close the window, and do not choose **OK**.  
  
### To view item availability by BOM level  
  
1.  In the **Search** box, enter **\($ N\_42 Sales Order $\)**, and then choose the related link.  
  
2.  Open the sales order you want, and then on the **Lines** FastTab, select the line that contains the item that you want to see availability for.  
  
3.  On the **Lines** FastTab, choose **Actions**, choose **Line**, choose **Item Availability By**, and then choose **BOM Level**.  
  
     If the item is a bill of material, then the window shows one collapsed line for the item.  
  
4.  Choose the **Expand \(\+\)** button to expand the line and view the components, children, or other parents, that exist in the item’s BOM structure.  
  
5.  Study the **\($ T\_5870\_33 Able to Make Parent $\)** and **\($ T\_5870\_32 Able to Make Top Item $\)** fields to find out how many of each parent you are able to make if you started the assembly or production process in question.  
  
> [!NOTE]  
>  The **\($ N\_5871\_26 Show Total Availability $\)** field in the **Options** FastTab is critical to the values that you see on the lines. For more information, see [\($ N\_5871\_26 Show Total Availability $\)](../Topic/\($%20N_5871_26%20Show%20Total%20Availability%20$\).md).  
  
### To view item availability by timeline  
  
1.  In the **Search** box, enter **\($ N\_99000852 Planning Worksheet $\)**, and then choose the related link.  
  
2.  Open the planning worksheet you want.  
  
3.  Select a planning line with the item that you want to view availability for, or that you want to modify suggested supply orders for.  
  
4.  On the **Navigate** tab, in the **Availability** group, choose **Item Availability By**, and then choose select **Timeline**.  
  
     The **\($ N\_5540 Item Availability Timeline $\)** window opens with the item number, location, and variant of the item on the selected planning line prefilled in the fields on the **Options** FastTab. The **Timeline** FastTab shows a graphical representation of the item’s projected inventory based on actual supply and demand events and the suggested supply orders. Clear the **Include Planning Suggestions** field if you only want to see actual inventory figures.  
  
 You can modify the suggested supply orders by dragging the related icons up and down on the **Timeline** FastTab. For more information, see [How to: Modify Planning Suggestions in a Graphical View](../DesignAndEngineering/how-to-modify-planning-suggestions-in-a-graphical-view.md).  
  
## See Also  
 [\($ N\_5530 Item Availability by Event $\)](../Topic/\($%20N_5530%20Item%20Availability%20by%20Event%20$\).md)   
 [\($ N\_492 Item Availability by Location $\)](../Topic/\($%20N_492%20Item%20Availability%20by%20Location%20$\).md)   
 [\($ N\_157 Item Availability by Periods $\)](../Topic/\($%20N_157%20Item%20Availability%20by%20Periods%20$\).md)   
 [\($ N\_5414 Item Availability by Variant $\)](../Topic/\($%20N_5414%20Item%20Availability%20by%20Variant%20$\).md)   
 [\($ N\_5871 Item Availability by BOM Level $\)](../Topic/\($%20N_5871%20Item%20Availability%20by%20BOM%20Level%20$\).md)   
 [\($ N\_5540 Item Availability by Timeline $\)](../Topic/\($%20N_5540%20Item%20Availability%20by%20Timeline%20$\).md)   
 [\($ T\_5870\_32 Able to Make Top Item $\)](../Topic/\($%20T_5870_32%20Able%20to%20Make%20Top%20Item%20$\).md)   
 [\($ T\_5870\_33 Able to Make Parent $\)](../Topic/\($%20T_5870_33%20Able%20to%20Make%20Parent%20$\).md)   
 [\($ T\_5531\_38 Suggested Projected Inventory $\)](../Topic/\($%20T_5531_38%20Suggested%20Projected%20Inventory%20$\).md)   
 [\($ N\_5703 Location Card $\)](../WarehouseActivities/-$-n_5703-location-card-$-.md)   
 [\($ T\_5401 Item Variant $\)](../DesignAndEngineering/-$-t_5401-item-variant-$-.md)   
 [\($ N\_99000852 Planning Worksheet $\)](../Topic/\($%20N_99000852%20Planning%20Worksheet%20$\).md)   
 [How to: Modify Planning Suggestions in a Graphical View](../DesignAndEngineering/how-to-modify-planning-suggestions-in-a-graphical-view.md)