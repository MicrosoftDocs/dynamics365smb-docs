---
title: Introduction to Contoso Coffee Warehousing
description: Overview of scenarios for how Contoso Coffee demo data can help you learn how to use the warehousing capabilities in Business Central.
ms.date: 11/12/2026
ms.topic: overview
ai-usage: ai-assisted
ms.service: dynamics-365-business-central
ms.search.form: 4766
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
---

# Introduction to Contoso Coffee warehousing

Contoso Coffee is a fictitious company that produces consumer and commercial coffee makers. The **Contoso Coffee** apps for Business Central add demo data that you can use to learn how to use the warehousing capabilities in Business Central. You can configure warehouse features in various ways. Learn more in [Overview of different configuration options](../../design-details-warehouse-management.md#overview-of-different-configuration-options).

The app provides three locations that are optimized for different scenarios:

- **SILVER**  

  This location requires bins but initially doesn't require receipts, shipments, put-aways, or picks. It can be configured to support basic or advanced warehousing. The basic walkthrough turns on **Require Put-away** and **Require Pick**.

- **YELLOW**  

  This location requires receipts, shipments, put-aways, and picks, but doesn't require bins. It can be reconfigured to support basic configurations. The mixed walkthrough turns off **Require Put-away**.

- **WHITE**  

  This location requires receipts, shipments, put-aways, picks, and bins. It uses directed put-away and pick, with cross-docking and breakbulk enabled, which enables more advanced rules for how items move through the warehouse.

## Set up Contoso Coffee warehousing data

[!INCLUDE [contoso-coffee-app-install](../../includes/contoso-coffee-app-install.md)]

Once the relevant apps are installed, go to the [Contoso Demo Tool](https://businesscentral.dynamics.com/?page=5194) page in [!INCLUDE [prod_short](../../includes/prod_short.md)], select the **Warehouse** line, and choose **Configure** to review the warehouse module settings. The following table describes the settings:

|Field  |Description  |
|---------|---------|
|**Location Bin**  |The location to use for the basic Location scenarios.|
|**Location Advanced**  |The location to use for the simple logistics scenarios.|
|**Location Directed Pick and Put-away**  |The location to use for the advanced logistics scenarios.|
|**Location In-Transit**  |The location to use for the in-transit location in transfer scenarios.|
|**Customer No.**  |The customer to use for the generated sales orders.|
|**Vendor No.**  |The vendor to use for the generated purchase orders.|
|**Item 1 No.**  |The main item to use for all scenarios.|
|**Item 2 No.**  |The extra item to use for all scenarios.|
|**Item 3 No.**  |The item with tracking.|

Once you're ready, choose the **Generate** action on the **Contoso Demo Tool** page. It takes a few minutes to add the data to the underlying database, but then you're ready to run the various scenarios. This action creates setup data, master data, and transactions for the warehouse module and its dependencies. **Generate Setup Data** alone doesn't create the locations, items, or orders needed for the walkthroughs.

The walkthroughs use the default locations **SILVER**, **YELLOW**, and **WHITE**, items **WRB-1000** and **WRB-1001**, and customer **10000**. Generated purchase orders use vendor **20000**. If you configure other records, use those records instead in the walkthroughs. The items use **PCS** as their base unit of measure, and one **BAG** contains 48 **PCS**.

> [!IMPORTANT]
> Generating warehouse master data adds the user who runs the action as a warehouse employee at the three configured warehouse locations. For new employee assignments, the directed put-away and pick location is the default. Existing assignments aren't changed. If another user runs the walkthroughs, verify that the user is set up for the relevant locations. Learn more in [Set Up Warehouse Employees](../../warehouse-how-to-set-up-warehouse-employees.md).

## Warehousing walkthrough scenarios

The Contoso Coffee warehousing demo data currently supports the following scenarios for test and training:

1.	[Walkthrough of inbound and outbound flow in Basic Warehouse Configurations](warehouse-basic-flow-putaway-pick.md)
2.	[Walkthrough of inbound and outbound flow in mixed Warehouse Configurations](warehouse-mixed-flow-receive-pick-ship.md)
3.	[Walkthrough of inbound and outbound flow in Advanced Warehouse Configuration with Directed Put-away and Pick](warehouse-directed-flow.md)

Read the steps for each scenario in the relevant article.  

## Related information

[Setting Up Inventory](../../inventory-setup-inventory.md) 
[How to Setup Locations](../../inventory-how-setup-locations.md) 
[Warehouse management overview](../../design-details-warehouse-management.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
