---
title: Purchasing in subscription billing
description: Learn about purchasing in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: 
ms.search.form: 8057, 8014, 8015, 8004,
ms.date: 05/07/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Purchasing in subscription billing

In subscription billing, you purchase items with subscription lines in the same way as purchasing features in [!INCLUDE [prod_short](../includes/prod_short.md)]. To learn more, go to [Purchasing](../purchasing-manage-purchasing.md). You map recurring purchases, such as rentals, maintenance, or subscription, with subscription lines. Subscription lines have **Vendor** specified in the **Partner** field on the subscription package lines. A subscription package can have lines for both customer and vendor subscription lines.

## Sales quotes and orders

For purchases, subscription lines work in the same way as sales subscription lines. You can either extend a vendor contract with a new item, or create a sales document with subscription lines that have **Vendor** specified in the **Partner** field on the **Assign Subscription Lines** page. To learn more, go to [Sales process](sales/sales-service-commitments.md). Depending on the selection in the **Calculation Base Type** field, the value in the **Calculation Base Amount** field is determined from the **Unit Cost** field on the sales lines or the **Last Direct Cost** field on the item. To learn more, go to [Price determination of subscription lines](sales/price-calculation.md).

## Subscriptions

When the item is delivered for an order, [!INCLUDE [prod_short](../includes/prod_short.md)] creates the subscription and its subscription lines. You can specify both customer and vendor subscription lines for the subscription.

## Assign a vendor contract

Unlike customer subscription lines, you can assign vendor subscription lines to any vendor contract.

> [!TIP]
> The **Subscription Billing** Role Center shows whether there are vendor subscription lines that aren't assigned to a contract.

## Related information

[Subscription lines](masterdata/service-commitments.md)  
[Termination of contract components](working-with-contracts/service-commitment-cancellation.md)  
