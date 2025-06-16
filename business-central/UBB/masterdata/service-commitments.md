---
title: Service commitments
description: You can use service commitments in usage based billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Extension of service commitments

Usage based billing extends the service commitments in [subscription billing](../../SRB/welcome.md), so this article only describes the differences. To learn more about service commitments and how to set them up, go to [Service commitments in subscription billing](../../SRB/masterdata/service-commitments.md).

## Service commitment templates

Using service commitment templates is optional. To learn more about the additional fields for usage based billing, go to [Service commitment packages](#service-commitment-packages).

## Service commitment packages

You can use both service commitment templates and service commitment package lines to create the default settings required to process usage data.

Service commitments that come from a package line are generally billed based on usage. This is done in the form of usage data that you [import and process](../processing-usage-data/imports-processing.md). Therefore, the **Usage Based Billing** field in the service commitment package determines the service object. The **Usage Based Pricing** field is only relevant on the sales side, and is decisive for billing. On the purchasing side, the purchase prices from the usage data are used for vendor or supplier contract invoices.

* The **Usage Based Pricing** field defines how prices are determined. The following options are available:
    * If **Usage Based Billing** is set, but the **Usage Based Pricing** field is blank, no pricing is determined for the usage data.
    * **Usage Quantity** is used when the customer is charged for the actual used quantity. This can be per billing period, for example, licenses (software), consumption minutes (car sharing), or the number of transactions. Therefore, only integer quantities (without decimal places) can be processed. The sales price (per unit) is determined on the basis of the related item, depending on the quantity.
    * For **Fixed Quantity**, the original quantity remains fixed when you import the usage data. The customer is always charged for the quantity entered in the service object. Quantities aren't adjusted based on the usage data. This pricing serves the flat-rate billing of service commitments, which, however, only takes place if usage data is available.
    * The **Unit Cost Surcharge** option also disregards the imported consumption quantity. However, the customer is charged for the unit cost plus the specified surcharge. This option is usually used for consumption-based or volume-based billing. In this case, all unit costs for the subscription are added up and the surcharge is calculated on the total.
    * The **Consumption Quantity** option also leaves the quantity in the service object unchanged. This means that, in contrast to the **Used Quantity** option, you can process non-integer consumption quantities. However, there is no aggregation of all usage data to one service commitment, as with the **Unit Cost Surcharge** option. Here, too, the sales price (per unit) is determined on a quantity-dependent basis using the related item.
* If you select the **Unit Cost Surcharge** option in the **Usage Based Pricing** field, the percentage value for the surcharge shows in **Pricing Unit Cost Surcharge %** field. For all other options, you can't edit this field.

## Related information

[Overview of usage based billing](../welcome.md)  
[Usage based billing customers and subscriptions](customers-subscriptions.md)  
