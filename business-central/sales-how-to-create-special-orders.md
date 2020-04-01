---
    title: How to Create Special Orders | Microsoft Docs
    description: You can create a special order for a specific catalog item to be shipped to a specific customer. Your vendor ships the item to your warehouse and you can then ship the item on to your customer either independently or together with other items on another order.
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
# Create Special Orders
You can create a special order for a specific catalog item to be shipped to a specific customer. Your vendor ships the item to your warehouse and you can then ship the item on to your customer either independently or together with other items on another order.  

Special orders imply that the purchase and sales order are linked to ensure that the specific catalog item is picked and delivered to the customer.  

Before you can use this feature, you must first set up the customer, vendor, and item cards necessary for the order.  

## To create a special order  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Order**, and then choose the related link.  
2. Choose the **New** action. Create and fill in a  sales order for the item. For more information, see [Sell Products](sales-how-sell-products.md).
3.  On the **Lines** FastTab, fill in the sales line. In the **Purchasing Code** field, select a purchasing code that has the **Special Order** field selected.

    You must now create a purchase order from a requisition worksheet.  
4. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Requisition Worksheet**, and then choose the related link.  
5. Choose the **Special Order** action, and then choose the **Get Sales Orders** action.  
6.  On the **Get Sales Orders** page, show results where the **Document No.** is the sales order number. Choose the **OK** button. A requisition worksheet line is created for the item.  
7.  On the requisition worksheet line, in the **Action Message** field, select **New**.  
8.  On the **Req. Worksheet** page, choose the **Carry Out Action Message** action. The **Carry Out Action Msg. - Req.** page opens. Choose the **OK** button.  

    A message appears telling you that the purchase orders have been created. Choost the **OK** button.  

A purchase order created as a special order for a sales order is respected by the planning system as it balances demand and supply. That is, the purchase order (supply) remains linked to the sales order (demand), even if that purchase order could supply another earlier demand. For more information, see [Design Details: Reordering Policies](design-details-reservation-order-tracking-and-action-messaging.md).  

> [!NOTE]  
>  You cannot use the special order functionality if the item is already reserved. Therefore, for items that are sold on special orders, make sure the **Reserve** field on the item card is not set to **Always**.  

## See Also  
[Work with Catalog Items](inventory-how-work-nonstock-items.md)  
[Sales](sales-manage-sales.md)  
[Make Drop Shipments](sales-how-drop-shipment.md)   
[Design Details: Reordering Policies](design-details-reservation-order-tracking-and-action-messaging.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
