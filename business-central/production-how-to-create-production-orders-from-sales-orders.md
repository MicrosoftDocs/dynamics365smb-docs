---
title: Create Production Orders from Sales Orders
description: Learn different ways to create production orders for produced items directly from sales orders.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 02/27/2023
ms.custom: bap-template
ms.search.form: 99000883, 99000884,
ms.service: dynamics-365-business-central
---
# Create Production Orders from Sales Orders

You can create production orders for produced items directly from sales orders.  

## To create a production order from a sales order  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
2. Select the sales order you want to create a production order for.  
3. Choose the **Planning** action. The **Sales Order Planning** page shows the availability of the item.  
4. Choose the **Create Prod. Order** action.  
5. Select the status and order type.  
6. Choose the **Yes** button to create one or more production orders for the lines that have **Prod. Order** in their **Replenishment System** field.

    > [!NOTE]  
    > Demand lines that have **Prod. Order** in the **Replenishment System** field represent underlying production orders. After you generate these production orders, remember to identify any unfulfilled component demand for them. Use the **Order Planning** page or the **Replan** action to identify unfulfilled demand.
    >
    > When you create production orders for sales orders with the Sales Order Planning page, order-to-order links are applied between demand and supply. When order-to-order links exist, the planning system doesn't include linked supply or inventory in the balancing procedure. To learn more about balancing, go to [Order-to-order links](design-details-central-concepts-of-the-planning-system.md#order-to-order-links).

## Order type  

The following table describes two ways to create production orders.

|Option|Description|
|------|-----------|
|Item Order|One production order is created for each item represented by a line in the **Sales Order Planning** page.|
|Project Order|One multiline production order is created for all items represented by lines on the **Sales Order Planning** page. When you use project orders, the **Source Type** field of the production order contains **Sales Header**. The order has one line for each sales line item that must be produced.|

## Related information  

[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Design Details: Supply Planning](design-details-supply-planning.md)  
[Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
