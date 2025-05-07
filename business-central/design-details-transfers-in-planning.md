---
title: Design Details - Transfers in Planning
description: Learn how to use transfer orders as a source of supply when planning inventory levels.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.date: 02/22/2023
ms.custom: bap-template
ms.search.keywords: design, transfer, sku, locations, warehouse
ms.service: dynamics-365-business-central
---
# Design Details: Transfers in Planning

Transfer orders are also a source of supply when working at the SKU level. When using multiple locations (warehouses), the SKU replenishment system can be set to Transfer, implying that the location is replenished by transferring goods from another location. In a situation with more warehouses, you might have a chain of transfers. Supply to GREEN location is transferred from YELLOW, supply to YELLOW is transferred from RED, and so on. In the beginning of the chain, there's a replenishment system of **Prod. Order** or **Purchase**.  

![Example of transfer flow.](media/nav_app_supply_planning_7_transfers1.png "Example of transfer flow")  

> [!NOTE]
> [!INCLUDE [locations-cronus](includes/locations-cronus.md)]

If you compare the following situations, it's clear that the planning task in the latter can become complex:

* A supply order is directly facing a demand order
* A sales order is supplied through a chain of SKU transfers

If demand changes, it might cause a ripple effect through the chain. All transfer orders, plus the purchase and production order in the opposite end of the chain, will have to be updated to re-balance demand and supply.  

![Example of supply/demand balance in transfers.](media/nav_app_supply_planning_7_transfers2.png "Example of supply/demand balance in transfers")  

## Why is a transfer a special case?  

Transfer orders are similar to other orders, such as purchase and production orders. However, behind the scene they're different.  

One difference is that a transfer line represents both demand and supply. The outbound part that's shipped is demand. The inbound part that's received at the new location is supply at that location.  

![Content of the Transfer Order page.](media/nav_app_supply_planning_7_transfers3.png "Content of the Transfer Order page")  

When [!INCLUDE [prod_short](includes/prod_short.md)] changes the supply side of the transfer, it must make a similar change on the demand side.  

## Transfers are dependent demand  

The demand and supply relationship is similar to components on production order lines. The difference is that components on production order lines are on the next planning level, and have a different item. The two parts of the transfer are on the same level for the same item.  

An important similarity is that components and transfers are dependent demand. Demand from a transfer line is dictated by the supply side of the transfer. If the supply changes, the demand is directly affected.

Unless the planning flexibility is None, a transfer line shouldn't be treated as independent demand in planning.  

In the planning procedure, the transfer demand should only be taken into account after the planning system has processed the supply side. Before that processing happens, the actual demand isn't known. The sequence of changes is important for transfer orders.  

## Planning sequence  

The following image shows an example of a string of transfers.  

![Example of simple transfer flow.](media/nav_app_supply_planning_7_transfers4.png "Example of simple transfer flow")  

In this example, a customer orders the item at location GREEN. Location GREEN is supplied through transfer from the central warehouse RED. The central warehouse RED is supplied by transfer from production on location BLUE.  

In this example, the planning system starts at the customer demand and works its way back through the chain. The demands and supplies are processed for one location at a time.  

![Supply planning with transfers.](media/nav_app_supply_planning_7_transfers5.png "Supply planning with transfers")  

## Transfer level code  

The transfer level code of the SKU determines the sequence in which the planning system processes locations.  

The transfer level code is an internal field. The field is calculated and stored on the SKU when you create or modify the SKU. The calculation runs across all SKUs for a given combination of item and item variant. The calculation uses the location code and the transfer-from code to determine the route to use for the SKUs. The calculation ensures that all demands are processed.  

The transfer level code will be 0 for SKUs with Purchase or Prod. Order replenishment system, and will be -1 for the first transfer level, -2 for the second, and so on. In the example described in the previous section, the levels would be -1 for RED and -2 for GREEN, as shown in the following illustration.  

![Content of SKU Card page.](media/nav_app_supply_planning_7_transfers6.gif "Content of SKU Card page")  

When updating a SKU, the planning system detects whether replenishment systems for SKUs have circular references.  

## Planning transfers without SKU  

For less advanced warehouse setups, you can use locations and make manual transfers between locations, even if you don't use SKUs. For example, the transfer might cover a sales order at that location. The planning system reacts to changes in the demand.  

For manual transfers, the planning system analyzes transfer orders and then plans the order in which to process the locations. Internally, the planning system uses temporary SKUs that have transfer level codes.  

![Transfer level code.](media/nav_app_supply_planning_7_transfers7.png "Transfer level code")  

If there are several transfers to a location, the first transfer order defines the planning direction. Transfers in the opposite direction are canceled.  

## Changing quantity with reservations  

When changing quantities on a supply, the planning system takes reservations into account. The reserved quantity represents the lower limit for how much to reduce the supply.  

When you change the quantity on a transfer order line, keep the lower limit in mind. The lower limit is the highest reserved quantity of the outbound and inbound transfer lines.

For example, a transfer order line of 117 pieces is reserved for the following lines:

* A sales line of 46
* A purchase line of 24

Even though the inbound side might have excess supply, you can't reduce the transfer line below 46.  

![Reservations in transfer planning.](media/nav_app_supply_planning_7_transfers8.png "Reservations in transfer planning")  

## Changing quantity in a transfer chain  

Here's an example of what happens when you change a quantity in a transfer change.

The starting point is a balanced situation with a transfer chain supplying a sales order of 27 at location RED. There's a corresponding purchase order at location BLUE. Both transfers go through location PINK. There are two transfer orders, BLUE-PINK and PINK-RED.  

![Changing the quantity in transfer planning 1.](media/nav_app_supply_planning_7_transfers9.png "Changing the quantity in transfer planning 1")  

Now, the planner at the PINK location chooses to reserve for the purchase.  

![Changing the quantity in transfer planning 2.](media/nav_app_supply_planning_7_transfers10.png "Changing the quantity in transfer planning 2")  

The reservation usually means that the planning system ignores the purchase order and transfer demand. There isn't a problem long as there's balance. But what happens when the RED location changes the order from 27 to 22?  

![Changing the quantity in transfer planning 3.](media/nav_app_supply_planning_7_transfers11.png "Changing the quantity in transfer planning 3")  

When the planning system runs again, it should get rid of excess supply. However, the reservation locks the purchase and the transfer to a quantity of 27.  

![Changing the quantity in transfer planning 4.](media/nav_app_supply_planning_7_transfers12.png "Changing the quantity in transfer planning 4")  

The PINK-RED transfer has been reduced to 22. The inbound part of the BLUE-PINK transfer isn't reserved, but the outbound part is. The reservation means that you can't reduce the quantity below 27.  

## Lead time calculation  

When calculating the due date of a transfer order, different kinds of lead time are taken into account.  

The following lead times are active when planning a transfer order:  

* Outbound warehouse handling time  
* Shipping time  
* Inbound warehouse handling time  

On the planning line, the following fields are used to provide information about the calculation:  

* Transfer shipment date  
* Starting date  
* Ending date  
* Due date  

The shipment date of the transfer line is shown in the **Transfer Shipment Date** field. The receipt date of the transfer line is shown in the **Due Date** field.  

The starting and ending dates describe the actual transportation period.  

The following image shows the interpretation of the starting date-time and ending date-time on planning lines for transfer orders.  

![Central date-times in transfer planning.](media/nav_app_supply_planning_7_transfers13.png "Central date-times in transfer planning")  

The example shows the following calculations:  

* Shipment date + Outbound handling = Starting Date  
* Starting Date + Shipping time = Ending Date  
* Ending Date + Inbound Handling = Receipt Date  

## Safety lead time  

The **Default Safety Lead Time** field on the **Manufacturing Setup** page and the related **Safety Lead Time** field on the **Item Card** page aren't included in transfer order calculations. However, the safety lead time does influence the total plan. The safety lead time affects the replenishment order (purchase or production) at the beginning of the transfer chain. That's the point where the items were put in the location from which they'll be transferred.  

![Elements of the transfer due date.](media/nav_app_supply_planning_7_transfers14.png "Elements of the transfer due date")  

On the production order line, the Ending Date + Safety Lead Time + Inbound Warehouse Handling Time = Due Date.  

On the purchase order line, the Planned Receipt Date + Safety Lead Time + Inbound Warehouse Handling Time = Expected Receipt Date.  

## Reschedule  

When you reschedule a transfer line, the planning system finds the outbound part and changes the date-time.

> [!NOTE]
> If a lead time is defined, there'll be a gap between the shipment and the receipt. The lead time can consist of more elements, such as transportation time and warehouse handling time. On a time line, the planning system moves back in time while it balances the elements.  

![Changing the due date in transfer planning.](media/nav_app_supply_planning_7_transfers15.png "Changing the due date in transfer planning")  

When you change the due date on a transfer line, the lead time must be calculated to update the outbound side of the transfer.  

## Serial and lot numbers in transfer chains  

If the demand uses serial or lot numbers, and you run the planning engine, it will create transfer orders. For more information about this concept, see Item Attributes. However, if serial or lot numbers are removed from the demand, the transfer orders still use the serial or lot numbers and planning will ignore them (not deleted).  

## Order-to-order links  

In this example, the BLUE SKU is set up with an **Order** reordering policy. The PINK and RED SKUs have the **Lot-for-Lot** reordering policy. Creating a sales order for 27 at location RED leads to a chain of transfers. The last transfer is at location BLUE, and it's reserved with binding. In this example, the reservations aren't hard reservations created by the planner at PINK location. The planning system creates the bindings. The important difference is that the planning system can change the latter.  

![Order-to-order links in transfer planning.](media/nav_app_supply_planning_7_transfers16.png "Order-to-order links in transfer planning")  

If the demand is changed from 27 to 22, the planning system will lower the quantity through the chain. The binding reservation is also reduced.  

## Related information  

[Design Details: Planning Parameters](design-details-planning-parameters.md)   
[Design Details: Planning Assignment Table](design-details-planning-assignment-table.md)   
[Design Details: Handling Reordering Policies](design-details-handling-reordering-policies.md)   
[Design Details: Planning With or Without Locations](production-planning-with-without-locations.md)   
[Design Details: Central Concepts of the Planning System](design-details-central-concepts-of-the-planning-system.md)   
[Design Details: Balancing Demand and Supply](design-details-balancing-demand-and-supply.md)   
[Design Details: Supply Planning](design-details-supply-planning.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
