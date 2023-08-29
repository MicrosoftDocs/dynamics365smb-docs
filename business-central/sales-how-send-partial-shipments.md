---
title: Process Partial Shipments
description: Sales orders' shipments can be processed in Business Central with partial shipments using the Shipping Advice and Qty. to Ship fields.
author: brentholtorf
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: shipping advice, partial shipments, partial deliveries, trade, customer sales order 
ms.date: 08/12/2022
ms.author: bholtorf
---
# Process Partial Shipments

In a partial shipment, an order isn't all shipped at once. For example, from an order for 100 units, you ship 40 units immediately and 60 units later. There are no limits on the number of shipments that can be made for an order.

However, before you can use partial shipments in [!INCLUDE [prod_short](includes/prod_short.md)], you must specify that the customer accepts partial shipments by setting the **Shipping Advice** field on the **Customer Card** page. Alternatively, if the customer usually only accepts complete shipments but then requests or agrees with a partial shipment for a specific sales order, you can change the **Shipping Advice** field before posting.

By default, [!INCLUDE [prod_short](includes/prod_short.md)] sets the field in the **Customer Card** page as **Partial**, which allows partial shipments. If, however, the field has been adjusted to specify **Complete**, then the **Qty. to Ship** field is blocked in sales orders for that customer.

[!INCLUDE [order-ship-invoice_md](includes/order-ship-invoice.md)]

## See also

[Sell Products with a Customer Sales Order](sales-how-sell-products.md)  
[Ship Items](warehouse-how-ship-items.md)  
[Make Drop Shipments](sales-how-drop-shipment.md)  
[Sales](sales-manage-sales.md)  
[Getting Ready To Do Business](ui-get-ready-business.md)  
[Administration](admin-setup-and-administration.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
