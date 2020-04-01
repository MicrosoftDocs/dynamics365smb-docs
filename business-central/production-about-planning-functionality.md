---
    title: About Planning Functionality | Microsoft Docs
    description: The planning system takes all demand and supply data into account, nets the results, and creates suggestions for balancing the supply to meet the demand.
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
# About Planning Functionality
The planning system takes all demand and supply data into account, nets the results, and creates suggestions for balancing the supply to meet the demand.  

For detailed information, see [Design Details: Supply Planning](design-details-supply-planning.md).  

> [!NOTE]  
> For all the fields that are mentioned in this topic, read the tooltip to understand their function. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## Demand and Supply  
Planning has two elements: demand and supply. These must be held in balance to ensure that the demand is met in a timely and cost-efficient manner.  

- Demand is the common term used for any kind of gross requirement such as a sales order, service order, component need from assembly or production orders, outbound transfer, blanket order or forecast. In addition to these, application allows some other technical types of demand - such as a negative production or purchase order, negative inventory, and purchase return.  
- Supply is the common word used for any kind of replenishment such as inventory, a purchase order, assembly order, production order, or inbound transfer. Correspondingly, there can be a negative sales or service order, negative component need or sales return – all of which in some way also represent supply.  

Another goal of the planning system is to ensure that the inventory does not grow unnecessarily. In the case of decreasing demand, the planning system will suggest that you postpone, decrease in quantity, or cancel existing replenishment orders.  

## Planning Calculation  
The planning system is driven by anticipated and actual customer demand, as well as inventory reordering parameters. Running the planning calculation will result in application suggesting specific actions (Action Messages) to take concerning possible replenishment from vendors, transfers between warehouses, or production. If replenishment orders already exist, the suggested actions could be to increase or expedite the orders to meet the changes in demand.  

The basis of the planning routine is in the gross-to-net calculation. Net requirements drive planned order releases, which are scheduled based on the routing information (manufactured items) or the item card lead time (purchased items). Planned order release quantities are based on the planning calculation, and are affected by the parameters set on the individual item cards.  

## Planning with Manual Transfer Orders
As you can see from the **Replenishment System** field on a SKU card, the planning system can be set up to create transfer orders to balance supply and demand across locations.  

In addition to such automatic transfer orders, you may sometimes need to perform a general move of inventory quantities to another location, irrespective of existing demand. For this purpose you would manually create a transfer order for the quantity to move. To ensure that the planning system does not try to manipulate this manual transfer order, you must set the **Planning Flexibility** on the transfer line(s) to None.  

Contrarily, if you do want the planning system to adjust the transfer order quantities and dates to existing demand, you must set the **Planning Flexibility** field to the default value, Unlimited.

## Planning Parameters  
The planning parameters control when, how much, and how to replenish based on the various settings on the item card (or stockkeeping unit - SKU), and the manufacturing setup.  

The following planning parameters exist on the item or SKU card:  

-   Dampener Period  
-   Dampener Quantity  
-   Reordering Policy  
-   Reorder Point
-   Maximum Inventory  
-   Overflow Level  
-   Time Bucket  
-   Lot Accumulation Period  
-   Rescheduling Period  
-   Reorder Quantity  
-   Safety Lead Time  
-   Safety Stock Quantity  
-   Assembly Policy  
-   Manufacturing Policy  

The following order modifiers exist on the item or SKU card:  

-   Minimum Order Quantity  
-   Maximum Order Quantity  
-   Order Multiple  

Global planning setup fields on the **Manufacturing Setup** page include:  

-   Dynamic Low-Level Code  
-   Current Demand Forecast  
-   Use Forecast on Locations  
-   Default Safety Lead Time  
-   Blank Overflow Level  
-   Combined MPS/MRP Calculation   
-   Components at Location  
-   Default Dampener Period  
-   Default Dampener Quantity  

For more information, see [Design Details: Planning Parameters](design-details-planning-parameters.md)  

## Other Important Planning Fields
### Planning Flexibility
On most supply orders, such as production orders, you can select **Unlimited** or **None** in the **Planning Flexibility** field on the lines.

This specifies whether the supply represented by the production order line is considered by the planning system when calculating action messages.
If the field contains **Unlimited**, then the planning system includes the line when calculating action messages. If the field contains **None**, then the line is firm and unchangeable, and the planning system does not include the line when calculating action messages.

### Warning
The **Warning** information field on the **Planning Worksheet** page informs you of any planning line created for an unusual situation with a text, which the user can choose to read additional information. The following warning types exist:

- Emergency
- Exception
- Attention
- Emergency

The emergency warning is displayed in two situations:

- The inventory is negative on the planning starting date.
- Back-dated supply or demand events exist.

If an item’s inventory is negative on the planning starting date, the planning system suggests an emergency supply order for the negative quantity to arrive on the planning starting date. The warning text states the starting date and the quantity of the emergency order.

Any document lines with due dates before the planning starting date are consolidated into one emergency supply order for the item to arrive on the planning starting date.

### Exception
The exception warning is displayed if the projected available inventory drops below the safety stock quantity.

The planning system will suggest a supply order to meet the demand on its due date. The warning text states the item’s safety stock quantity and the date on which it is violated.

Violating the safety stock level is considered an exception because it should not occur if the reorder point has been set correctly.

> [!NOTE]
> Supply on planning lines with Exception warnings is normally not modified according to planning parameters. Instead, the planning system only suggests a supply to cover the exact demand quantity. However, you can set the planning run up to respect certain planning parameters for planning lines with certain warnings. For more information, see “Respect Planning Parameters for Exception Warnings” in Calculate Plan - Plan. Wksh.

### Attention
The attention warning is displayed in two situations:

- The planning starting date is earlier than the work date.
- The planning line suggests to change a released purchase or production order.

> [!NOTE]
> In planning lines with warnings, the **Accept Action Message** field is not selected, because the planner is expected to further investigate these lines before carrying out the plan.

## See Also  
[Design Details: Supply Planning](design-details-supply-planning.md)  
[Planning](production-planning.md)   
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)    
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
