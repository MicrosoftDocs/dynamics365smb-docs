---
title: Introduction to Contoso Coffee Service Management
description: Set up Contoso Coffee service demo data to explore repairs, loaners, service contracts, and resources with the right skills in Business Central.
author: andreipanko
ms.author: andreipa
ms.topic: how-to
ms.date: 11/12/2026
ms.custom: bap-template
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Introduction to Contoso Coffee service management

Contoso Coffee is a fictitious company that produces consumer and commercial coffee makers. The **Contoso Coffee** apps for [!INCLUDE [prod_short](../../includes/prod_short.md)] add demo data that you can use to learn how to use the Service Management capabilities in [!INCLUDE [prod_short](../../includes/prod_short.md)].

This app provides several elements that are used for the main walkthroughs:

- Resources with assigned Skills
- Items configured to create Service Items
- Loaner Items

## Set up Contoso Coffee service management data

[!INCLUDE [contoso-coffee-app-install](../../includes/contoso-coffee-app-install.md)]

Once the relevant apps are installed, go to the [Contoso Demo Tool](https://businesscentral.dynamics.com/?page=5194) page, select **Service**, and choose **Configure**. The following table describes the settings:

|Field  |Description  |
|---------|---------|
|**Customer No.**|Specifies the customer for the service scenarios. The default is **10000**.|
|**Item 1 No.**|Specifies the inventory item used in repair and maintenance scenarios. The default is **S-100, S-100 Semi-Automatic**, which requires the plumbing skill.|
|**Service Item 1 No.**|Specifies the service-type item used to charge an equipment fee. The default is **SER101, Equipment Fee**, with a unit of measure of **DAY**.|
|**Service Item 2 No.**|Specifies the service-type item used to charge for repairs. The default is **SER102, Repair**, with a unit of measure of **HOUR**.|
|**Resource 1 No.**|Specifies the first service resource. The default is **RESOURCE1**, with the electrical skill.|
|**Resource 2 No.**|Specifies the second service resource. The default is **RESOURCE2**, with the plumbing skill required for item **S-100**.|
|**Service Location**|Specifies the location for service operations. The default is **MAIN**, but you can change it to suit your needs.|

When you're ready, return to **Contoso Demo Tool**, select **Service**, and choose **Generate**. Required dependency modules are generated automatically. **Generate Setup Data** creates only setup records, not the items, resources, or sales order needed for the walkthroughs. If you configure different identifiers, use your values instead of the defaults in the walkthroughs.

## Explore service management scenarios

The Contoso Coffee demo data currently supports the following service scenarios for test and training:

1. Create a service order for a repair request, lend and receive a loaner, and invoice the customer with [Walkthrough of service orders for service items](service-basic-flow-order.md).
1. Create a service contract, invoice contract fees, and allocate a resource with the required skill with [Walkthrough of service contracts for service items](service-contract-flow.md).

Read the steps for each scenario in the relevant article.  

> [!IMPORTANT]
> The service walkthroughs require that you set the user experience to **Premium** on the **Company Information** page. Learn how to [select the Premium experience](../../ui-experiences.md#to-select-the-premium-experience).


## Related information

[Service](../../service-service.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
