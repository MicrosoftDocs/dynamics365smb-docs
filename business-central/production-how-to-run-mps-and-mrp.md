---
title: Run Full Planning, MPS, or MRP
description: The planning system can calculate either Master Production Schedule (MPS) or Material Requirements Planning (MRP) on request, or both at the same time.
author: brentholtorf
ms.topic: how-to
ms.search.form: 99000852, 99000860
ms.date: 01/24/2024
ms.author: bholtorf
ms.reviewer: bholtorf
ms.custom: bap-template 

ms.service: dynamics-365-business-central
---
# Run Full Planning, MPS, or MRP

The terms "running the planning worksheet" or "running MRP" refer to calculating the master production schedule and material requirements. The calculation is based on actual and forecasted demand. The planning system can calculate either Master Production Schedule (MPS) or Material Requirements Planning (MRP) on request, or both at the same time.  

- MPS is the calculation of a master production schedule based on actual demand and the demand forecast. The MPS calculation is used for end items that have a forecast or a sales order line. These items are called MPS items and are identified dynamically when the calculation starts.  
- MRP is the calculation of material requirements based on actual demand for components and the demand forecast on the component level. MRP is calculated only for items that are not MPS items. The purpose of MRP is to provide time-phased formal plans, by item, to supply the appropriate item, at the appropriate time, in the appropriate location, and in the appropriate quantity.  

The planning algorithms for MPS and MRP are the same. The algorithms pertain to netting, reusing existing replenishment orders, and action messages. The planning system process examines what is, or will be, needed (demand) and what's on-hand or expected (supply). When you net these quantities against each other, [!INCLUDE[prod_short](includes/prod_short.md)] provides action messages. Action messages are suggestions to create a new order, change an order (quantity or date), or cancel an order. The term "order" includes purchase orders, assembly orders, production orders, and transfer orders.

You can track the links that the planning creates between demand and supply on the **Order Tracking** page. For more information, see [Track Relations Between Demand and Supply](production-how-track-demand-supply.md).

Proper planning results depend on the set up done on item cards, assembly BOMs, production BOMs, and routings.  

## Methods for generating a plan  

- **Calculate Regenerative Plan:** Process or regenerate the material plan. This process starts by deleting all planned supply orders that are currently loaded. All items in the database are replanned.  
- **Calculate Net Change Plan**: Process a net change plan. Items are considered in net change planning from two types of changes:  
   - **Demand/supply changes:** These changes include modifications to quantities on sales orders, demand forecasts, assembly orders, production orders, or purchase orders. An unplanned inventory level change is also considered a quantity change.  
   - **Planning parameter changes:** These changes include changes in safety stock, reorder point, routing, bill of material, and changes to the time bucket or lead time calculation.  
- **Get Action Messages:** Serves as a short-term planning tool by issuing action messages to alert the user of modifications made since the last time you calculated a regenerative or net change plan.  

With each planned method, [!INCLUDE[prod_short](includes/prod_short.md)] generates worksheet entries assuming infinite capacity. Work center and machine center capacity isn't considered when you develop schedules.  

> [!IMPORTANT]  
> The Calculate Regenerative Plan is the most common process. The Calculate Plan and Carry out Action Messages, however, can be used to run the Calculate Net Change Plan process.  
>
> You can run the Get Action Messages Plan between regenerative and net change planning runs to obtain an immediate view of the effect of schedule changes. However, it isn't meant to replace the full regenerative or net change planning processes.  

## To calculate the planning worksheet
  
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Planning Worksheets**, and then choose the related link.  
2. Choose the **Calculate Regenerative Plan** action to open the **Calculate Plan** page.  
3. On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**MPS**|Calculate a master production schedule. Items with open sales orders or demand forecasts are considered in this run. <br/>If other demands, for example safety stock, reorder point, or open production component lines, also exist for such items these demands are included in the MPS calculation to ensure that the planning system deals with the complete inventory profile.  |  
    |**MRP**|Calculate material requirements planning. Items with dependent requirements are considered in this run. Typically, MPS and MRP are run at the same time. To run MPS and MRP at the same time, on the **Manufacturing Setup** page, on the **Planning** FastTab, select the **Combined MPS/MRP Calculation** field.|  
    |**Starting Date**|Evaluate inventory availability. If an item's on-hand quantity is below the reorder point, the system forward-schedules a replenishment order from this date. If an item is below its safety stock (as of the starting date), the system back-schedules a replenishment order due on the planning starting date.|  
    |**Ending Date**|The ending date of the planning horizon. Neither demand nor supply are considered after this date. If the reorder cycle for an item extends beyond the ending date, the effective planning horizon for that item is equal to the order date plus the reorder cycle.<br/><br/> The planning horizon is the time that the plan is extended to. If the horizon is too short, items with a longer lead time aren't ordered on time. If the horizon is too long, too much time is spent reviewing and processing information that likely changes before it's needed. You can set one planning horizon for production and a longer one for purchases, although it isn't required. A planning horizon for purchases and production should be set to cover the total lead time for components.|  
    |**Stop and Show First Error**|Select this option if you want the planning run to stop as soon as it encounters an error. A message displays with information about the error. If an error exists, only the successful planning lines made before the error was encountered are presented in the planning worksheet. If you don't select this field, the **Calculate Plan** batch job continues until it completes. Errors won't interrupt the batch job. If one or more errors exist, a message displays after completion with information about how many items are affected. The **Planning Error Log** page will then open to provide more details about the error and links to the affected item cards.|  
    |**Use Forecast**|Select a forecast to include as demand when you run the planning batch job. The default forecast is set up on the **Planning** FastTab on the **Manufacturing Setup** page.|  
    |**Exclude Forecast Before**|Define how much of the selected forecast to include in the planning run by entering a date before which forecast demand is not included.|  
    |**Respect Planning Parameters for Exception Warnings**|By default, this field is selected.<br/><br/> Supply on planning lines with warnings is normally not modified according to planning parameters. Instead, the planning system only suggests a supply to cover the exact demand quantity. However, you can define certain planning parameters for planning lines to be respected with certain warnings.<br/><br/>|  

4. On the **Item** FastTab, set filters to run the planning based on the item, item description, or location.  
5. Choose the **OK** button. The batch job runs and planning lines are added to the planning worksheet.  

## To perform action messages
  
1. On the **Planning Worksheet** page, choose the **Carry Out Action Message** action.  
2. On the **Options** FastTab, specify how to create the supplies. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Production Order**|Specify how to create production orders. You can do this directly from the planning line proposals. You can create either planned or firm planned production orders.|  
    |**Assembly Order**|Specify how to create assembly orders. You can do this directly from the planning line proposals.|  
    |**Purchase Order**|Specify how to create purchase orders. You can do this directly from the planning line proposals.<br/><br/> If you chose to copy the planning line proposals for purchase orders to the requisition worksheet, select the template and worksheet name.|  
    |**Transfer Order**|Specify how to create transfer orders. You can do this directly from the planning line proposals.<br/><br/> If you chose to copy the planning line proposals for transfer orders to the requisition worksheet, select the template and worksheet name.|  
    |**Combine Transfer Orders**|Select whether to combine transfer orders.|  
    |**Stop and Show First Error**|Select this option if you want the **Carry Out Action Msg. - Plan.** batch job to stop as soon as it finds an error. Aa message displays information about the error. If an error exists, only the planning lines processed before the error was found will create supply orders.|  

3. On the **Planning Line** FastTab, you can set filters to limit the perform action messages.  
4. Choose the **OK** button.  

The batch job deletes the lines in the planning worksheet after it has performed the action message. The other lines remain in the planning worksheet until they are either accepted at a later date or else deleted. You can also delete the lines manually.  

## Action messages
  
Action messages are issued by the order tracking system when balance is unattainable in the existing order network. The messages can be viewed as a suggestion for you to process changes that reestablish balance between supply and demand.  

The generation of action messages occurs one level at a time, for each item's low-level code. This makes sure that all items that experience or will experience changes in supply or demand are considered.  

To avoid small, unneeded, or unimportant action messages, you can set dampeners, which serve to restrict the generation of action messages to only those changes that exceed the defined quantity or number of days.  

After you review the action messages and determine whether to accept some or all of the suggested changes, select the **Accept Action Message** field. Next, update the schedules accordingly.  

> [!NOTE]  
> An action message is a suggestion to create a new order, cancel an order, or change the quantity or date of an order. An order is a purchase order, transfer order, or production order.  

In response to any supply/demand imbalances, the following action messages are generated.  

|Action Message|Description|  
|--------------------|---------------------------------------|  
|**New**|If a demand can't be fulfilled by suggesting action messages to **Change Qty.**, **Reschedule**, or **Reschedule & Change Qty.** on existing orders, the action message **New** is generated to suggest a new order. The message **New** is also generated if there aren't supply orders in the reorder cycle of the item. This option determines the number of periods forward and backward in the availability profile when it searches for an order to reschedule.|  
|**Change Quantity**|When the quantity changes for a demand that's tracked to a supply order, the action message **Change Qty.** is generated. The message indicates that the related supply should be changed relative to the change in demand. If a new demand emerges, [!INCLUDE[prod_short](includes/prod_short.md)] searches for the nearest existing unreserved supply order in the reorder cycle, and issues a change of action message for that order.|  
|**Reschedule**|When a date change for a supply or demand order causes an imbalance in the order network, the action message **Reschedule** is generated. If there is a one-to-one relationship between demand and supply, an action message is generated to suggest that you move the supply order. If the supply-order covers demand from more than one sales order, the supply order is re-scheduled equal to the date of the first demand.|  
|**Resch. & Chg. Qty.**|If both the dates and quantities of an order change, you must change plans with regard to both. Action messaging gathers both actions in one message, **Resched. and Chg. Qty.**, to ensure that the order network returns to balance.|  
|**Cancel**|If a demand that has been covered on an order-to-order basis is deleted, an action message is generated to cancel the related supply order. If the relationship isn't order-to-order, an action message is generated to change in order to reduce the supply. If through other factors, such as inventory adjustments, a supply order isn't required at the time you generate the action messages, [!INCLUDE[prod_short](includes/prod_short.md)] suggests an action message of **Cancel** in the worksheet.|  

## Related information  

[Planning](production-planning.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)    
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Design Details: Supply Planning](design-details-supply-planning.md)   
[Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
