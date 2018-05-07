---
    title: Design Details - Handling Projected Negative Inventory | Microsoft Docs
    description: The reorder point expresses the anticipated demand during the lead time of the item. When the reorder point is passed, it is time to order more. But the projected inventory must be large enough to cover the demand until the new order is received. Meanwhile, the safety stock should take care of fluctuations in demand up to a targeted service level.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Design Details: Handling Projected Negative Inventory
The reorder point expresses the anticipated demand during the lead time of the item. When the reorder point is passed, it is time to order more. But the projected inventory must be large enough to cover the demand until the new order is received. Meanwhile, the safety stock should take care of fluctuations in demand up to a targeted service level.  

 Consequently, the planning system considers it an emergency if a future demand cannot be served from the projected inventory, or expressed in another way, that the projected inventory goes negative. The system deals with such an exception by suggesting a new supply order to meet the part of the demand that cannot be met by inventory or other supply. The order size of the new supply order will not take the maximum inventory or the reorder quantity into consideration, nor will it take into consideration the order modifiers Maximum Order Quantity, Minimum Order Quantity, and Order Multiple. Instead, it will reflect the exact deficiency.  

 The planning line for this type of supply order will display an Emergency warning icon, and additional information will be provided upon lookup to inform the user of the situation.  

 In the following illustration, supply D represents an emergency order to adjust for negative inventory.  

 ![](media/nav_app_supply_planning_2_negative_inventory.png "NAV_APP_supply_planning_2_negative_inventory")  

1.  Supply **A**, initial projected inventory, is below reorder point.  

2.  A new forward-scheduled supply is created (**C**).  

     (Quantity = Maximum Inventory – Projected Inventory Level)  

3.  Supply **A** is closed by demand **B**, which is not fully covered.  

     (Demand **B** could try to schedule Supply C in but that will not happen according to the time-bucket concept.)  

4.  New supply (**D**) is created to cover the remaining quantity on Demand **B**.  

5.  Demand **B** is closed (creating a reminder to the projected inventory).  

6.  The new supply **D** is closed.  

7.  Projected Inventory is checked; reorder point has not been crossed.  

8.  Supply **C** is closed (no more demand exists).  

9. Final check: No outstanding inventory level reminders exist.  

> [!NOTE]  
>  Step 4 reflects how the system reacts in versions earlier than Microsoft Dynamics NAV 2009 SP1.  

 This concludes the description of central principles relating to inventory planning based on reordering policies. The following section describes the characteristics of the four supported reordering policies.  

## See Also  
 [Design Details: Reordering Policies](design-details-reordering-policies.md)   
 [Design Details: Planning Parameters](design-details-planning-parameters.md)   
 [Design Details: Handling Reordering Policies](design-details-handling-reordering-policies.md)   
 [Design Details: Supply Planning](design-details-supply-planning.md)
