---
title: Replan or refresh production orders directly
description: This article outlines the procedures for how to replan production orders and refresh production orders directly.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.form: 99000842, 99000843, 99000861, 99000862, 99000863
ms.date: 03/18/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Replan or refresh production orders directly

The **Replan** action on production orders is typically used after you add or change components that constitute underlying production orders. The action calculates changes made to components and routings lines, and includes items on lower production BOM levels for which it might generate new production orders.  

Based on the changes to the components and routing lines, the **Replan** action calculates and plans for any new demand for the production order.  

The **Refresh** action on production orders is typically used after you:

- Create a production order header manually to calculate and create line data for the first time.
- Change the production order header to recalculate all the line data.

The **Refresh** action calculates changes to a production order header and doesn't involve production BOM levels. The action calculates and initiates the values of the component lines and routing lines based on the production BOM and routing. The calculation is according to the order quantity and due date on the production order’s header.

You can either insert the production order lines manually or use the action that calculates the production order lines from the header.  

> [!NOTE]
> If you use the **Refresh** action to recalculate production order lines, [!INCLUDE [prod_short](includes/prod_short.md)] deletes the existing production order lines and calculates new lines.
> Even if the **Lines** option is disabled, non-top-level lines in a Make-to-order environment are deleted. Use the **Replan** action to restore them.

## To replan a production order

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Firm Planned Prod. Orders**, and then choose the related link.  
2. Open the production order you want to replan.  
3. On the **Lines** FastTab, choose the **Lines** action, and then choose the **Components** action.  
4. Add a component that is a produced item or subassembly.  
5. From the production order, choose the **Replan** action.  

    On the **Replan Production Order** page, define how and what to replan.  
6. In the **Scheduling Direction** field, select one of the options in the following table.  

    | Option | Description |
    |--|--|
    | **Back** | Calculates the operation sequence backwards from the earliest possible ending date, defined by due date and/or other scheduled orders, to the latest possible starting date. **Note:**  This default option is relevant in most situations. |
    | **Forward** | Calculates the operation sequence forward from the earliest latest possible starting date, defined by due date and/or other scheduled orders, to the earliest possible ending date. **Note:**  This option is only relevant for expedite orders. |

7. In the **Plan** field, select whether to calculate production requirements for produced items on the production BOM. The following table describes the options.  

    |Option|Description|  
    |----------------------------------|---------------------------------------|  
    |**No Levels**|Don't consider lower level production. This setting only updates the item’s schedule, like refresh.|  
    |**One Level**|Plan for first-level production demand. First-level production orders might be created.|  
    |**All Levels**|Plan for all-level production demand. All-level production orders might be created.|  

8. Select **One Level**, and choose the **OK** button to replan the production order and calculate and create a new underlying production order for the introduced subassembly if it isn't fully available.  

> [!NOTE]  
> Changes implemented with the **Replan** action probably change the capacity need of the production order. You might have to reschedule operations afterwards.  

## To refresh a production order

If you change production order lines, components, or routing lines, you must also refresh the information on the production order. In the following procedure, the components are calculated for a firm planned production order. The steps are similar for routing lines.

1. Choose the ![Lightbulb that opens the Tell Me feature 2.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Firm Planned Prod. Order**, and then choose the related link.  
2. Choose the **New** action. To learn more, go to [Create Production orders](production-how-to-create-production-orders.md).  
3. Choose the **Refresh** action.
4. On the **Refresh Production Order** page, select one of the options in the following table.

    |Field|Option|Description|  
    |----------------------------------|---------------|---------------------------------------|  
    |**Scheduling Direction**|**Forward**|Scheduling starts from the starting date and proceeds forward to the finishing date. You must fill in the starting date to use this option.|  
    ||**Backward**|Scheduling starts from the ending date and proceeds backward to the starting date.|  
    |**Calculate**|**Lines**|Select this field to calculate the production order lines.|  
    ||**Routings**|This field doesn't affect the calculations on production lines.|  
    ||**Component Need**|This field doesn't affect the calculations on production lines.|  
    |**Warehouse**|**Create Inbound Request**|This field doesn't affect the calculations on production lines.|  

5. Choose the **OK** button to confirm your selection. The production order lines are calculated.

> [!NOTE]  
> Calculating production order components deletes previous changes in the components.

## Reschedule production orders within a safety lead time

If you discover that you need the supply before the due date that planning set, you can manually reschedule the production order. To do that, you must turn on the **Manual Scheduling** toggle on the **Manufacturing Setup** page. If needed, in the **Safety Lead Time for Manual Scheduling** field, you can also specify an amount of buffer time to add to the end date when you manually reschedule a production order. You can move the due date to the current date or a future date, or change the end date directly by changing the starting date.

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
