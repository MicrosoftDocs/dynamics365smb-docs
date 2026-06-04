---
title: Plan for New Demand Order by Order
description: This planning task can be performed on the Order Planning page, which displays all new demand along with availability information and suggestions for supply, including item substitution.
author: brentholtorf
ms.topic: how-to
ms.search.form: 5522, 5524, 5526
ms.date: 06/04/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---
# Plan for new demand order by order

You can plan for new demand on an order by order basis on the **Order Planning** page. The page displays all new demand along with availability information and suggestions for supply. It provides the visibility and tools you need to effectively plan demand from sales lines and component lines, and then create different types of supply orders.  

> [!NOTE]
> The **Order Planning** page shows demand from sales orders, production order components, assembly order lines, service orders, and job planning lines. It doesn't include demand from transfer orders. To plan for transfer order demand, use the **Planning Worksheet** page with the **Regenerative Plan** or **Net Change Plan** action instead. Learn more at [Run Full Planning, MPS, or MRP](production-how-to-run-mps-and-mrp.md).

You can access the **Order Planning** page in two ways depending on your focus: 

- From an order that you want to plan for specifically.
- In batch mode, because you want to plan for all new demand.  

## Plan for new production order demand

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Planned Production Orders**, and then choose the related link. (You can do these steps for planned, firm planned, or released production orders).
2. Open the production order you want to plan for, and then choose the **Planning** action.  
3. On the **Order Planning** page, choose the **Calculate Plan** action.  

The page displays planning lines according to the view filter **Production Demand**, meaning unfulfilled component lines of all existing production orders. Demand for only the one production order doesn't show because you must plan with an overview of potential demand for earlier component lines. Planning lines for the production order in context are expanded.  

## Plan for any new demand

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Order Planning**, and then choose the related link.  
2. On the **Order Planning** page, choose the **Calculate Plan** action.
3. Choose the **Expand (+)** button in front of the date in the **Demand Date** field to see the underlying planning lines that represent demand lines with insufficient availability.  
4. For each expanded planning line, that is, demand line, fields at the bottom of the page display information.  

    |Option|Description|  
    |----------------------------------|---------------------------------------|  
    |**Qty. on Other Locations**|Shows whether the item exists at another location. You can look up and select the item.|  
    |**Substitutes Exist**|Shows whether a substitute item is created for the item. You can look up and select the item. This feature only applies to components, that is, from demand lines of type **Production**.|  
    |**Quantity Available**|Shows the total availability of the item, that is, the projected available balance.|  
    |**Earliest Date Available**|Shows the arrival date of an inbound supply order that can cover the needed quantity on a date later than the demand date.|  

5. In the **Replenishment System** field, select the type of supply order to create.  

    The default value is that of the item or SKU, but you can change it to one of three options:  

    |Option|Description|  
    |--------------|------------------------|  
    |**Purchase**|Creates a purchase order.|  
    |**Transfer**|Creates a transfer order.|  
    |**Prod. Order**|Creates a production order.|  

    > [!NOTE]  
    > If the field isn't filled in, [!INCLUDE [prod_short](includes/prod_short.md)] displays an error message when you use the **Make Supply Order** action, and no supply order is created for the planning line. However, the exception is when the replenishment system is **Prod. Order**.  

6. From the **Supply From** field, you can look up in the relevant list and select where the supply should come from. You must select a value according to the selected replenishment system.  

    - If replenishment system is **Purchase**, the look-up button in this field looks up on the **Item Vendor Catalog** page.  
    - If replenishment system is **Transfer**, the look-up button in this field looks up on the **Location List** page.  

    If the item exists in another location, the **Qty. on Other Location** field at the bottom shows a value, and you can then look up and select the supply location when you make the transfer order.  

    If a substitute exists for the item, the **Substitute Exists** field is set to **Yes**, and you can then look up to the **Item Substitution Entries** page and select the substitute.  

    > [!NOTE]  
    > Item substitutions don't automatically cause an item to replace another item, for example when creating a sales order or in a BOM. Instead, you're alerted to the fact that a substitution is available to you.

7. Select the **Reserve** checkbox if you want to make a reservation between the supply order you're creating and the demand line that it's for. It's empty by default.  

    > [!NOTE]  
    > You can only select this check box if the item has **Optional** or **Always** in the **Reserve** field on its item card.  

8. In the **Qty. to Order** field, you can enter the quantity that goes on the supply order you're creating.

   The default value is the same as the quantity in the **Needed Quantity** field. But you can decide to order more or less than this quantity based on your knowledge of the demand situation. If, for example, the **Order Planning** page shows that several unrelated demand lines are for the same purchased item, and they're due around the same date, you can consolidate these lines by entering the total needed quantity in the **Qty. to Order** field of one line, and then delete the others planning lines for that item.  

9. In the **Due Date** and **Order Date** fields, you can enter the dates that should apply to the created supply orders.  

    These fields are interrelated according to the **Default Safety Lead Time** field on the **Manufacturing Setup** page. By default, the due date is the same as the demand date, but you can change the date.  

> [!NOTE]  
> If you enter a date later than the demand date, you receive a warning message.  

## Create supply orders

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Planned Production Orders**, and then choose the related link. You can perform these steps for a planned, firm planned, or released production order.  
2. Open the production order you want to plan for, and then choose the **Planning** action.  
3. Choose a relevant planning line, and then choose the **Make Orders** action.  
4. On the **Make Supply Orders** page, on the **Order Planning** FastTab, in the **Make Orders for** field, select one of the following options.  

    |Option|Description|  
    |----------------------------------|---------------------------------------|  
    |**The Active Line**|Make a supply order only for the selected line.|  
    |**The Active Order**|Make supply orders for all lines in the selected order.|  
    |**All Lines**|Make supply orders for all lines on the **Order Planning** page.|  

5. On the **Options** FastTab, define what kind of supply orders, or requisition worksheet lines, should be made.  

    > [!NOTE]  
    > The settings you last made on the **Make Supply Orders** page are saved under your user ID so that they're the same the next time you use the page.  

6. Choose the **OK** button to create the suggested supply orders or requisition worksheet lines.  

You have a plan for the unfulfilled demand by making respective supply orders. Details about specific work flows when using the **Order Planning** page would depend on a company’s internal policies.  

When you finish your planning work on the **Order Planning** page, for example you defined an alternative way to supply the quantity, you can proceed to create supply orders for one or more of the planning lines.  

> [!NOTE]  
> The supply orders you create might introduce new dependent demand, for example for underlying production orders, and you should therefore choose **Calculate Plan** again to find and resolve the demand before moving down the list.  

## Related information

<!-- [Walkthrough: Planning Supplies Manually](walkthrough-planning-supplies-manually.md)   -->
[Planning](production-planning.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Design Details: Supply Planning](design-details-supply-planning.md)  
[Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Register New Items](inventory-how-register-new-items.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
