---
title: Create Blanket Assembly Orders
description: Create blanket sales orders for customized assembly items before periodically making the actual sales orders according to the blanket order agreement.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: kit, kitting
ms.search.form: 900, 901, 902, 903, 904, 907, 910, 916, 920, 921, 922, 923, 940, 941, 942, 930, 931, 932, 914, 915, 905
ms.date: 04/01/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Create Blanket Assembly Orders

You can use assembly management to customize an assembly item to a customer's request during the sales process. For more information, see [Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md).  

 As with any other type of item, you can also create blanket sales orders for customized assembly items before periodically making the actual sales orders according to the blanket order agreement. This process involves several extra steps when you compare it to creating a regular blanket sales order, and it uses a variation of a linked assembly order, which is a blanket assembly order.

> [!NOTE]  
>  Like all blanket orders, quantities on assembly blanket orders are only forecasts and are not operational until they are converted to actual assembly orders. Therefore, order functionality, such as availability calculation, reservation, and item tracking, is not active on blanket assembly orders.  

## To create a blanket assembly order for an assemble\-to\-order item  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Blanket Sales Orders**, and then choose the related link.  
2. Create a new blanket sales order with one line for an assembly item. For more information, see [Create Blanket Sales Orders](sales-how-to-create-blanket-sales-orders.md).  
3. In the **Qty. to Assemble to Order** field on the blanket assembly order line, enter the full quantity.

    > [!NOTE]  
    >  You should not create blanket order agreements for a partial quantity. Therefore, you must enter the same quantity that you entered in the **Quantity** field on the blanket sales order line.  

4. Choose the **Assemble to Order** action, and then choose the **Assemble-to-Order Lines** action. Alternatively, choose the **Qty. to Assemble to Order)** field on the line.  
5. On the **Assemble-to-Order Lines** page, review or modify the assembly order lines according to the blanket order agreement that you have made with the customer. If you want to view more information, choose the **Show Document** action to open the complete blanket assembly order. You cannot change the contents of most fields, and you cannot post.  
6. When you have adjusted the assembly order lines according to the blanket order agreement, close the **Assemble-to-Order Lines** page to return to the **Blanket Sales Order** page.  
7. When the customer requests to create a sales order based on the agreed blanket sales order, create a sales order for the agreed assembly item or items. For more information, see [Create Blanket Sales Orders](sales-how-to-create-blanket-sales-orders.md).

The linked blanket assembly order and any customizations are linked to that new sales order to prepare for assembly of the item or items to be sold.  

## Related information

[Create Blanket Sales Orders](sales-how-to-create-blanket-sales-orders.md)  
[Assembly Management](assembly-assemble-items.md)  
[Work with Assembly BOMs](assembly-how-work-assembly-boms.md)  
[Inventory](inventory-manage-inventory.md)  
[Warehouse Management Overview](design-details-warehouse-management.md)
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
