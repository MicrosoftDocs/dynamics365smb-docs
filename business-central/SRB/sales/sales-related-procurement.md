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

In Business Central, there are several ways to create Purchase Orders for retail items. The most common are the <a href="https://learn.microsoft.com/en-us/dynamics365/business-central/production-planning" title="Requisition Worksheets">Requisition Worksheets</a> (from the manufactoring module) and the functionality to create a <a href="https://learn.microsoft.com/en-us/dynamics365/business-central/purchasing-how-purchase-products-sale" title="Purchasing Items for a Sale">Purchase Order</a> from a Sales Order. However, if retail items are needed explicitly for a specific Sales Order, these two options fall short. <br/>
In both cases, the goods are not ordered on an order-by-order basis. Thus, the reservation of the required quantity in the Sales Order line must be done manually. Especially in the second case, both the order (here: Sales Order line) lacks the link to the Purchase Order (here: Purchase Order line) expected by the user and vice versa.


## Create Purchase Order
For this requirement, the separately available app **[DYCE IT-Business Toolkit](/docs/ibt/welcome.md)** offers a simplification compared to the standard of Business Central. Further explanations on how to create Sales Order-related Purchase orders can be found in [this](/docs/ibt/sales-related-procurement.md) part of the DYCE documentation.

:::note Unit costs for Service Commitment Items
Since Service Commitment Items are always considered as a *service per period* and therefore also the Purchase and Sales prices are related to it, Service Commitment Items are initially transferred to the Purchase Order without Unit Cost. The Unit Cost can be changed in the **Create and connect Purchase Orders** page as well as in the created Purchase Order line.
:::


## Reservations
For inventory items (**Type**=*Inventory*), the expected goods are automatically reserved for the Sales Order line when the Purchase Order is created. This is visible in the **Reserved Quantity** field in both the Sales Order line and the Purchase Order line. Clicking on the field will open the Reservation Entries. <br/>
Reservations cannot be created for non-inventory items (**Type**=*Non-Inventory*). In this case, the standard functionality of Business Central is triggered and used to create Purchase Orders.