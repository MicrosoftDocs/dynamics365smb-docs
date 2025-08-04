---
title: Currencies
description: You can use currencies in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# Currencies

In [!INCLUDE [prod_short](../../includes/prod_short.md)], you can make transactions in foreign currencies by entering a currency code. For example, on a sales order or the customer or vendor contract. To learn more about using foreign currencies, go to [Update currency exchange rates](../../finance-how-update-currencies.md).

## Foreign currencies in service commitments

If you enter a currency code on a sales order, for example, or if you specify a currency for a customer, the price on the order is converted to that currency. This conversion is the same for sales service commitments in subscription billing. In the service commitments for the service object, the **Currency Code** field also indicates the currency to which the **Service Amount** field refers.

When you manually create a service object with service commitments, the **Currency Code** field and the corresponding fields in the service are initially empty, even if a currency code is specified for the customer. The currency code can remain blank because the contract that's used to bill the service determines which currency to use.

When you create the service object and service commitments by using a sales shipment, the currency code from the sales order automatically transfers to the service.

## Convert service amounts

When assigning service commitments to a contract, [!INCLUDE [prod_short](../../includes/prod_short.md)] checks whether to convert the amounts. If the currency code in the contract is the same as the currency code in the service commitments, no conversion is required. Otherwise, the conversion is done by a query in which the last conversion factor is suggested based on the work date. If you choose **OK**, [!INCLUDE [prod_short](../../includes/prod_short.md)] recalculates the fields for the currency, update the service commitment, and then add it to the contract. The dialog also displays when you change the currency code in the contract.

> [!NOTE]
> When you assign service commitments to a contract that requires currency conversion, all services must have the same currency code.

## Update exchange rates on service objects

The method described in this section ensures that prices for service commitments in a foreign currency don't automatically change as a result of a change in the exchange rate. However, you might need to use the **Update exchange rates** action to adjust the exchange rate manually. The action is available on the **Service Object**, **Customer Contract**, and **Vendor Contract** pages.

> [!NOTE]
> If you manually change some fields, other fields also update.
>
> Changes to these fields update other fields:
>
> * Calculation Base Amount
> * Calculation Base %
> * Price
> * Discount %
> * Discount Amount
> * Service Amount
>
> These are the fields that your changes update based on the specified exchange rate:
>
> * Price (LCY)
> * Discount Amount (LCY)
> * Service Amount (LCY)

## Update exchange rates for currencies automatically

You can automatically update exchange rates using the job queue. To learn more, go to [Update currency exchange rates](../../finance-how-update-currencies.md) and [Use job queues to schedule tasks](../../admin-job-queues-schedule-tasks.md).

## Related information

[Price determination of service commitments](price-calculation.md)  
[Customer contracts](../working-with-contracts/customer-contracts.md)  
