---
title: Purchasing in subscription billing
description: Learn about purchasing in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Purchasing in subscription billing

In subscription billing, you purchase items with service commitments in the same way as purchasing features in [!INCLUDE [prod_short](../includes/prod_short.md)]. To learn more, go to [Purchasing](../purchasing-manage-purchasing.md). You map recurring purchases, such as rentals, maintenance, or subscription, with service commitments. Service commitments have **Vendor** specified in the **Partner** field on the service commitment package lines. A service commitment package can have lines for both customer and vendor service commitments.

## Sales quotes and orders

For purchases, service commitments work in the same way as sales service commitments. You can either extend a vendor contract with a new item, or create a sales document with service commitments that have **Vendor** specified in the **Partner** field on the **Assign Service Commitments** page. To learn more, go to [Sales process](sales/sales-service-commitments.md). Depending on the selection in the **Calculation Base Type** field, the value in the **Calculation Base Amount** field is determined from the **Unit Cost** field on the sales lines or the **Last Direct Cost** field on the item. To learn more, go to [Price determination of service commitments](sales/price-calculation.md).

## Service objects

When the item is delivered for an order, [!INCLUDE [prod_short](../includes/prod_short.md)] creates the service object and its service commitments. You can specify both customer and vendor service commitments for the service object.

## Assign a vendor contract

Unlike customer service commitments, you can assign vendor service commitments to any vendor contract.

> [!TIP]
> The **Subscription & Recurring Billing** Role Center shows whether there are vendor service commitments that aren't assigned to a contract.

## Related information

[Service commitments](masterdata/service-commitments.md)  
[Termination of contract components](working-with-contracts/service-commitment-cancellation.md)  
