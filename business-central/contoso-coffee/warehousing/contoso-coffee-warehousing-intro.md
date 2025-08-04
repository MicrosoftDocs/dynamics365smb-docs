---
title: Introduction to Contoso Coffee 
description: Overview of scenarios for how Contoso Coffee demo data can help you learn how to use the warehousing capabilities in Business Central.
ms.date: 04/01/2022
ms.topic: concept-article
ms.service: dynamics-365-business-central
ms.search.form: 4764
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
---

# Introduction to Contoso Coffee Warehousing

Contoso Coffee is a fictitious company that produces consumer and commercial coffee makers. The **Contoso Coffee** apps for Business Central add demo data that you can use to learn how to use the warehousing capabilities in Business Central. You can configure warehouse features in various ways, see [Overview of different configuration options](../../design-details-warehouse-management.md#overview-of-different-configuration-options).

The app provides three locations that are optimized for different scenarios:

- **SILVER**  

  This Location configured to use Bins. It can be easily configured to support basic or advanced. 

- **YELLOW**  

  This Location uses the advanced warehouse configuration, but doesn't use Bins. It can be reconfigured to support basic configurations.

- **WHITE**  

  This Location uses the Advanced Warehouse configuration with directed put-aways and picks, which enables more advanced rules to how items move throughout Warehouse.

## Set up Contoso Coffee Warehousing data

[!INCLUDE [contoso-coffee-app-install](../../includes/contoso-coffee-app-install.md)]

Once the relevant apps are installed, go to the [Contoso Demo Tool](https://businesscentral.dynamics.com/?page=5194) page in [!INCLUDE [prod_short](../../includes/prod_short.md)], select the *Warehouse Module* line and use the **Configure** action to prepare the  modules. The following tables describes the settings:  

|Field  |Description  |
|---------|---------|
|**Location Bin**  |The location to use for the basic Location scenarios.|
|**Location Advanced**  |The location to use for the simple logistics scenarios.|
|**Location Directed Put-Away and Pick**  |The location to use for the advanced logistics scenarios.|
|**Location In-Transit**  |The location to use for the in-transit location in transfer scenarios.|
|**Customer No.**  |The customer to use for the basic and simple scenarios in sales operations.|
|**Vendor No.**  |The vendor to use for all scenarios in purchasing operations.|
|**Item 1 No.**  |The main item to use for all scenarios.|
|**Item 2 No.**  |The extra item to use for all scenarios.|
|**Item 3 No.**  |The item with tracking.|

Once you're ready, choose the **Create Demo Data** action. It takes a few minutes to add the data to the underlying database, but then you're ready to run the various scenarios.  

> [!IMPORTANT]
> If you are running the Scenarios, you may want to verify that your user has been added as for selected locations. For more information, see [Set Up Warehouse Employees](../../warehouse-how-to-set-up-warehouse-employees.md).

## Scenarios

The Contoso Coffee warehousing demo data currently supports the following scenarios for test and training:

1.	[Walkthrough of inbound and outbound flow in Basic Warehouse Configurations](warehouse-basic-flow-putaway-pick.md)
2.	[Walkthrough of inbound and outbound flow in mixed Warehouse Configurations](warehouse-mixed-flow-receive-pick-ship.md)
3.	[Walkthrough of inbound and outbound flow in Advanced Warehouse Configuration with Directed Put-away and Pick](warehouse-directed-flow.md)

Read the steps for each scenario in the relevant article.  

## Related information

[Setting Up Inventory](../../inventory-setup-inventory.md) 
[How to Setup Locations](../../inventory-how-setup-locations.md) 
[Warehousing](../../warehouse-manage-warehouse.md) 
[Design Details](../../design-details-warehouse-overview.md) 
