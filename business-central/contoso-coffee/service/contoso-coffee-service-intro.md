---
title: Introduction to Contoso Coffee service management
description: This article introduces you to the Consoso Coffee demonstration data for service management.
author: andreipanko
ms.author: andreipa
ms.topic: how-to
ms.date: 11/27/2023
ms.custom: bap-template
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Introduction to Contoso Coffee service management

Contoso Coffee is a fictitious company that produces consumer and commercial coffee makers. The **Contoso Coffee** apps for [!INCLUDE [prod_short](../../includes/prod_short.md)] add demo data that you can use to learn how to use the Service Management capabilities in [!INCLUDE [prod_short](../../includes/prod_short.md)].

This app provides several elements that are used for the main walkthroughs:

- Resources with assigned Skills
- Items configured to create Service Items
- Loaner Items

## Set up Contoso Coffee service management data

[!INCLUDE [contoso-coffee-app-install](../../includes/contoso-coffee-app-install.md)]

Once the relevant apps are installed, go to the [Contoso Demo Tool](https://businesscentral.dynamics.com/?page=5194) page in [!INCLUDE [prod_short](../../includes/prod_short.md)], select the *Service Module* line and use the **Configure** action to prepare the  modules. The following table describes the settings:  

|Field  |Description  |
|---------|---------|
|**Customer No.**  |The customer to use for the scenarios in sales operations.|
|**Vendor No.**  |The vendor to use for all scenarios in purchasing operations.|
|**Item 1 No.**  |The item to use for the repair and maintenance scenarios.|
|**Service Item 1 No.**  |The item of type service to use repear scenario.|
|**Service Item 2 No.**  |The item of type service to use repear scenario.|
|**Resource 1 No.**  |The resource to use for the contract scenarios.|
|**Resource 2 No.**  |The resource to use for the break/fix scenarios.|
|**Service Location** |Specifies the warehouse that you want to use for service operations. The default is *MAIN*, but you can change it to suit your needs.|

Once you're ready, choose the **Create Demo Data** action. It takes a few minutes to add the data to the underlying database, but then you're ready to run the various scenarios.  

## Scenarios

The Contoso Coffee demo data currently supports the following service scenarios for test and training:

1. Create service order for ad-hoc repair request, place and receive Loaners, register time, and invoice customers with [Walkthrough of Service Orders for Service Items](service-basic-flow-order.md)
2. Create service contracts, generate service orders, invoice contract fees, and allocate resources with [Walkthrough of Service Contracts for Service Items](service-contract-flow.md)

Read the steps for each scenario in the relevant article.  

> [!IMPORTANT]
> The Service walkthroughs require that the user experience is set to **Premium** in the **Company Information** page.


## See also

[Service](../../service-service.md)
