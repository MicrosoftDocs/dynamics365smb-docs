---
title: "Setup Best Practices: Planning Parameters"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "best practices, planning parameter setup"
  - "setup (best practices), planning parameters"
ms.assetid: d0982666-1dc5-4e52-901c-2cc4e0e4d711
caps.latest.revision: 17
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
# Setup Best Practices: Planning Parameters
The **Planning** FastTab on the item card is the center of a company’s supply chain. Setting the correct planning parameters is very important for cost\-effective inventory control and high customer service.  
  
 The following table provides best practices on how to set up selected planning parameter fields. For more information about a field, choose the link in the **Setup field** column.  
  
|Setup field|Best practice|Comment|  
|-----------------|-------------------|-------------|  
|[\($ T\_27\_5440 Reordering Policy $\)](../DesignAndEngineering/-$-t_27_5440-reordering-policy-$-.md)||For more information, see [Setup Best Practices: Reordering Policies](../SetupAndAdministration/setup-best-practices-reordering-policies.md).|  
|[\($ T\_27\_100 Reserve $\)](../Topic/\($%20T_27_100%20Reserve%20$\).md)|Select **Never** when the item is planned using a reorder point.<br /><br /> In manufacturing, select **Never** to allow the planning system to cover all demands.<br /><br /> Select **Optional** for items that you may want to reserve for top\-priority customers.<br /><br /> Select **Always** for non\-unique items, such as items of type miscellaneous that are inbound for specific demands.|Reservations generally counteract the purpose of planning, which is to balance demand and supply. Therefore, items that are set up for planning should generally not be reserved.<br /><br /> If the user reserves an inventory quantity for future demand, then the planning foundation will be disturbed, and the reorder point may not work correctly. Even if the projected inventory level is acceptable with regard to the reorder point, the quantities may not be available because of the reservation.|  
|[\($ T\_27\_5445 Dampener Period $\)](../Topic/\($%20T_27_5445%20Dampener%20Period%20$\).md)|Set with regard to the supplier’s flexibility.|If the supplier accepts last\-minute changes to orders, then use a longer period. If the supplier requires firm planning, then shorten your period as much as possible.<br /><br /> For information about the global setup, see [\($ T\_99000765\_40 Default Dampener Period $\)](../Topic/\($%20T_99000765_40%20Default%20Dampener%20Period%20$\).md).|  
|[\($ T\_27\_5446 Dampener Quantity $\)](../Topic/\($%20T_27_5446%20Dampener%20Quantity%20$\).md)||For information about the global setup, see [\($ T\_99000765\_41 Default Dampener Quantity $\)](../Topic/\($%20T_99000765_41%20Default%20Dampener%20Quantity%20$\).md).|  
|[\($ T\_27\_5441 Include Inventory $\)](../Topic/\($%20T_27_5441%20Include%20Inventory%20$\).md)|Always select when you are using the Lot\-for\-Lot reordering policy.|Do not select only in special situations, such as when inventory items are not sellable.|  
|[\($ T\_27\_5415 Safety Lead Time $\)](../Topic/\($%20T_27_5415%20Safety%20Lead%20Time%20$\).md)|Set between 1D and 6D.<br /><br /> Set a safety lead time of at least one day to make sure that supplies are available on the day before they are needed.<br /><br /> If using a new supplier, define a longer time until their delivery performance is known.<br /><br /> In manufacturing, define longer safety lead times for critical components.|Supply that is planned by the system to avoid a stock\-out will arrive on the same day that the stock\-out occurs. This may be several hours too late if, for example, the demand is needed in the morning and the supply arrives in the afternoon. **Note:**  The **\($ T\_27\_5415 Safety Lead Time $\)** field uses the base calendar. Therefore, 14D is not necessarily two weeks.|  
|[\($ T\_27\_5413 Safety Stock Quantity $\)](../Topic/\($%20T_27_5413%20Safety%20Stock%20Quantity%20$\).md)|Use for items with large demand fluctuations.<br /><br /> In manufacturing, use for critical components.<br /><br /> Use for items that are subject to service agreements.|If the **\($ T\_27\_34 Reorder Point $\)** field is not filled, then the safety stock quantity also functions as a reorder point.|  
|[\($ T\_27\_5444 Lot Accumulation Period $\)](../Topic/\($%20T_27_5444%20Lot%20Accumulation%20Period%20$\).md)|If you want only few big orders and you accept to carry inventory, then set a long lot accumulation period.<br /><br /> If you want multiple small orders and minimal inventory, then set a short lot accumulation period.|The lot accumulation period is generally the longest period that you will carry inventory.|  
|[\($ T\_27\_34 Reorder Point $\)](../Topic/\($%20T_27_34%20Reorder%20Point%20$\).md)|Base the reorder point on the item’s demand profile.|If historical data shows that the item’s average demand is 100 units during a lead time of seven days, then the reorder point can be set to 100 as a minimum.<br /><br /> This means that when the inventory level falls below 100 units, then the planning system will suggest to replenish because it takes seven days to supply the item, and there must be enough to cover the demand within those seven days.|  
|[\($ T\_27\_5428 Time Bucket $\)](../Topic/\($%20T_27_5428%20Time%20Bucket%20$\).md)|Leave blank, meaning that the inventory level is checked every day.|Checking the inventory level every day ensures optimal reorder point planning. **Note:**  A time bucket of 1W means that the inventory level may be below the reorder point for one week before a supply order is suggested.|  
|[\($ T\_27\_5422 Rounding Precision $\)](../Topic/\($%20T_27_5422%20Rounding%20Precision%20$\).md)|In expensive manufacturing, set to 0.00001.|Large rounding quantities of scrap or material consumption can amount to very large inventory costs. It may therefore be relevant to set the smallest rounding precision to minimize this potential cost.|  
  
> [!NOTE]  
>  The best practices for planning parameters on item cards also apply to the same fields on SKU cards.  
>   
>  If companies plan for demand at different locations, then it is strongly advised to define SKUs for each location and that all demand is created by using a value in the **Location Code** field. For more information, see [Design Details: Demand at Blank Location](../ApplicationDesign/design-details-demand-at-blank-location.md).  
  
## See Also  
 [Setup Best Practices: Supply Planning](../SetupAndAdministration/setup-best-practices-supply-planning.md)   
 [Design Details: Supply Planning](../ApplicationDesign/design-details-supply-planning.md)   
 [Set Up a Company With RapidStart Services for Microsoft Dynamics NAV](../SetupAndAdministration/set-up-a-company-with-rapidstart-services-for-microsoft-dynamics-nav.md)