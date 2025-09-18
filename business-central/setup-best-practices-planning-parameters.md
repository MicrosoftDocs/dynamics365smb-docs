---
title: Setup best practices - planning parameters
description: This topic outlines best practices on how to set up selected planning parameter fields with the Planning FastTab on the item card.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: best-practice
ms.search.keywords:
ms.date: 03/11/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---
# Setup best practices: planning parameters

The **Planning** FastTab on the **Item Card** page is the center of a company’s supply chain. Setting the correct planning parameters is very important for cost-effective inventory control and quality customer service.  

This article provides best practices on how to set up selected planning parameter fields.

|Setup field|Best practice|Comment|  
|-----------------|-------------------|-------------|  
|Reordering Policy||To learn more, go to [Setup Best Practices: Reordering Policies](setup-best-practices-reordering-policies.md).|  
|Reserve|Select **Never** when the item is planned using a reorder point.<br /><br /> In manufacturing, select **Never** to allow the planning system to cover all demands.<br /><br /> Select **Optional** for items that you may want to reserve for top-priority customers.<br /><br /> Select **Always** for unique items (Non-Standard type of Items), such as items of type miscellaneous that are inbound for specific demands.|Reservations generally counteract the purpose of planning, which is to balance demand and supply. Therefore, items that are set up for planning should generally not be reserved.<br /><br /> If the user reserves an inventory quantity for future demand, then the planning foundation will be disturbed, and the reorder point may not work correctly. Even if the projected inventory level is acceptable with regard to the reorder point, the quantities may not be available because of the reservation.|  
|Dampener Period|Set with regard to the supplier’s flexibility.<br /><br /> A shorter period enables you to reduce working capital by avoiding excessive stock, but will also cause more rescheduling actions.|If the supplier accepts last-minute changes to orders, then use a shorter period, but be prepared for more rescheduling actions. If the supplier requires firm planning, then extend the period as much as possible.<br /><br /> To learn more about this field, go to [Design Details: Planning Parameters](design-details-planning-parameters.md).|  
|Include Inventory|Always select when you are using the **Lot-for-Lot** reordering policy.|Do not select only in special situations, such as when inventory items are not sellable.|  
|Safety Lead Time|Set between 1D and 6D. Set a safety lead time of at least one day to make sure that supplies are available on the day before they are needed. If you're using a new supplier, define a longer time until their delivery performance is known.<br /><br />In manufacturing, define longer safety lead times for critical components. Use longer safety lead times for produced components to have a buffer that allows for fluctuations in production times.|Supply that is planned by the system to avoid a stock-out will arrive on the same day that the stock-out occurs. The supply might be several hours too late if, for example, the demand is needed in the morning and the supply arrives in the afternoon. **Note:** The Safety Lead Time field uses the base calendar. Therefore, 14D is not necessarily two weeks.|  
|Safety Stock Quantity|Use for items with large demand fluctuations.<br /><br /> In manufacturing, use for critical components.<br /><br /> Use for items that are subject to service agreements.|If the **Reorder Point** field is not filled in, the safety stock quantity also acts as a reorder point.|  
|Lot Accumulation Period|If you want only a few big orders and it's ok to carry inventory, specify a long period for lot accumulation.<br /><br /> If you want multiple small orders and minimal inventory, set a short lot accumulation period.|The lot accumulation period is generally the longest period that you carry inventory.|  
|Reorder Point|Base the reorder point on the item’s demand profile.|If historical data shows that the item’s average demand is 100 units during a lead time of seven days, the reorder point can be set to 100 as a minimum.<br /><br /> When the inventory level falls below 100 units, the planning system suggests that you replenish because it takes seven days to supply the item, and there must be enough to cover the demand within those seven days.|  
|Time Bucket|Leave blank, meaning that the inventory level is checked every day.|Checking the inventory level every day ensures optimal reorder point planning. **Note:** A time bucket of 1W means that the inventory level can be below the reorder point for one week before a supply order is suggested.|  
|Rounding Precision|In expensive manufacturing, set to 0.00001.|Large rounding quantities of scrap or material consumption can amount to very large inventory costs. It might be relevant to set the smallest rounding precision to minimize this potential cost.|  

> [!NOTE]  
> The best practices for planning parameters on item cards also apply to the same fields on SKU cards.  
>
> If you plan for demand at different locations, we recommend that you define SKUs for each location and that all demand is created by using a value in the **Location Code** field. To learn more, go to [Design Details: Planning With or Without Locations](production-planning-with-without-locations.md).  

## Related information
  
[Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md)  
[Design Details: Supply Planning](design-details-supply-planning.md)  
[Set Up Complex Application Areas Using Best Practices](set-up-complex-application-areas-using-best-practices.md)  
[Design Details: Planning With or Without Locations](production-planning-with-without-locations.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
