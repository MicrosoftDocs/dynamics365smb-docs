---
title: Sales-related procurement
description: You can use sales related procurement in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# Procurement in connection with a sales order

In Business Central, there are several ways to create Purchase Orders for retail items. The most common are the [Planning](../../production-planning.md) (from the manufactoring module) and the [Purchase items for a sale by creating purchase invoices](../../purchasing-how-purchase-products-sale.md) functionality to create a purchase order from a sales order. However, if retail items are needed explicitly for a specific sales order, these two options fall short.

In both cases, the goods are not ordered on an order-by-order basis. Thus, the reservation of the required quantity in the sales order line must be done manually. Especially in the second case, both the order (here: sales order line) lacks the link to the purchase order (here: purchase order line) expected by the user and vice versa.

## Create purchase order

For this requirement, the separately available app **[IT-Business Toolkit](/docs/ibt/welcome.md)** offers a simplification compared to the standard of Business Central. Further explanations on how to create sales order-related purchase orders can be found in [Procurement in connection with a sales order](sales-related-procurement.md).

> [!NOTE]
> Since service commitment items are always considered as a *service per period* and therefore also the purchase and sales prices are related to it, service commitment items are initially transferred to the purchase order without unit cost. The unit cost can be changed on the **Create and connect Purchase Orders** page as well as in the created purchase order line.

## Reservations

For inventory items (**Type**=*Inventory*), the expected goods are automatically reserved for the sales order line when the purchase order is created. This is visible in the **Reserved Quantity** field in both the sales order line and the purchase order line. Clicking on the field will open the Reservation Entries.

Reservations cannot be created for non-inventory items (**Type**=*Non-Inventory*). In this case, the standard functionality of Business Central is triggered and used to create purchase orders.