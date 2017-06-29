---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# How to: Create Special Orders
You can create a special order for a specific nonstock item to be shipped to a specific customer. Your vendor ships the item to your warehouse and you can then ship the item on to your customer either independently or together with other items on another order.  
  
 Special orders imply that the purchase and sales order are linked to ensure that the specific nonstock item is picked and delivered to the customer.  
  
 Before you can use this feature, you must first set up the customer, vendor, and item cards necessary for the order.  
  
### To create a special order  
  
1.  In the **Search** box, enter **Sales Order**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** groups, choose **New**. Create and fill in a  sales order for the item.  
  
3.  On the **Lines** FastTab, fill in the sales line. In the **Purchasing Code** field, select a purchasing code that has the **Special Order** field selected. FIX INCLUDE HERE<!--[!INCLUDE[bp_choose_columns](../DesignAndEngineering/includes/bp_choose_columns_md.md)] -->  
  
     You must now create a purchase order from a requisition worksheet.  
  
4.  In the **Search** box, enter **Requisition Worksheet**, and then choose the related link.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Special Order**, and then choose **Get Sales Orders**.  
  
6.  In the **Get Sales Orders** window, show results where the **Document No.** is the sales order number. Choose the **OK** button. A requisition worksheet line is created for the item.  
  
7.  On the requisition worksheet line, in the **Action Message** field, select **New**.  
  
8.  In the **Req. Worksheet** window, on the **Actions** tab, in the **Functions** group, choose **Carry Out Action Message**. The **Carry Out Action Msg. \- Req.** window opens. Choose the **OK** button.  
  
     A message appears telling you that the purchase orders have been created. Choost the **OK** button.  
  
 A purchase order created as a special order for a sales order is respected by the planning system as it balances demand and supply. That is, the purchase order \(supply\) remains linked to the sales order \(demand\), even if that purchase order could supply another earlier demand. For more information, see [Design Details: Reservation, Order Tracking, and Action Messaging](../ApplicationDesign/design-details-reservation-order-tracking-and-action-messaging.md).  
  
> [!NOTE]  
>  You cannot use the special order functionality if the item is already reserved. Therefore, for items that are sold on special orders, make sure the **Reserve** field on the item card is not set to **Always**.  
  
## See Also  
 Purchasing Code   
 Reserve   
 [How to: Create Drop Shipments](../Purchasing/how-to-create-drop-shipments.md)   
 Calculate Plan \- Req. Wksh.   
 [Design Details: Reservation, Order Tracking, and Action Messaging](../ApplicationDesign/design-details-reservation-order-tracking-and-action-messaging.md)