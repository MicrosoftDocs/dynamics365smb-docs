---
title: Introduction to Contoso Coffee Demo Data
description: Overview of scenarios for how Contoso Coffee demo data can help you learn how to use the capabilities in Business Central.
ms.date: 04/01/2022
ms.topic: article
ms.service: dynamics365-business-central
ms.search.form: 4760
author: edupont04
ms.author: andreipa
---

# Introduction to Contoso Coffee Demo Data

Contoso Coffee is a fictitious company that produces consumer and commercial coffee makers. The **Contoso Coffee** apps for Business Central add demo data that you can use to learn how to use the capabilities in Business Central.  


## Set up Contoso Coffee data

To use the Contoso Coffee demo data, you must install two apps in the relevant company in [!INCLUDE [prod_short](../includes/prod_short.md)]:  

- **Contoso Coffee Demo Dataset**  

    This app delivers demo data for the base application.  
- **Contoso Coffee Demo Dataset (country ID)**  

    This app adds country-specific content on top of the base application.

Add the apps to an empty company in a paid subscription or as part of a trial. For example, create a new company with no sample data from the **Create New Company** assisted setup guide that you can open from the **Companies** list. Then add the apps from the [marketplace](../ui-extensions-install-uninstall.md#install) if they are not already listed in the **Extension Management** page.  

You then should complete:
 - The [Manufacturing Setup](manufacturing/contoso-coffee-manufacturing-intro.md) to prepare for use of the [Manufacturing Scenarios](#manufacturing-scenarios)
 - The [Warehousing Setup](warehousing/contoso-coffee-warehousing-intro.md) to prepare for use of the [Warehousing Scenarios](#warehousing-scenarios)

## Manufacturing Scenarios

The Contoso Coffee demo data currently supports the following manufacturing scenarios for test and training:

1. [Create a New Production BOM and BOM Version](manufacturing/create-new-production-bom-version.md)  
2. [Create a New Routing](manufacturing/create-new-routing.md)  
3. [Create a Firm Planned Production Order and Change It](manufacturing/create-firm-planned-production-order-change.md)  
4. [Combine Automatic and Manual Flushing](manufacturing/combine-automatic-manual-flushing.md)  
5. [Use Order Planning to Create and Reserve Supply](manufacturing/order-planning-create-reserve-supply.md)  
6. [Set Up and Process a Subcontracting Operation](manufacturing/set-up-process-subcontracting-operation.md)  
7. [Set Up New Capacity](manufacturing/set-up-new-capacity.md)  
8. [Forecast demand for item variants with different BOMs assigned](manufacturing/variants.md)  

Read the steps for each scenario in the relevant article.  

> [!IMPORTANT]
> The Manufacturing walkthroughs require that the user experience is set to *Premium* in the **Company Information** page.

## Warehousing Scenarios

The Contoso Coffee demo data currently supports the following warehousing scenarios for test and training:

1.	[Basic Location](warehousing/basic-location.md)
    1.	[Receiving Items with Inventory Put-Away](warehousing/basic/receiving-items-with-inventory-put-away.md)
    2.	[Shipping Items with Inventory Picks](warehousing/basic/shipping-items-with-inventory-picks.md)
    3.	[Transferring Items](warehousing/basic/transferring-items.md)
    4.	[Moving Items Between Bins](warehousing/basic/moving-items-between-bins.md)
    5.	[Adjusting Items out of Inventory](warehousing/basic/adjusting-items-out-of-inventory.md)
2.	[Simple Logistics Location](warehousing/simple-logistics-location.md)
    1.	[Receiving a Single Order with Whse. Receipt](warehousing/simple/receiving-a-single-order-with-whse-receipt.md)
    2.	[Combining Orders on a Whse. Receipt](warehousing/simple/combining-orders-on-a-whse-receipt.md)
    3.	[Shipping a Single Order with Whse. Shipment](warehousing/simple/shipping-a-single-order-with-whse-shipment.md)
    4.	[Combining Orders on a Whse. Shipment](warehousing/simple/combining-orders-on-a-whse-shipment.md)
    5.	[Transferring Items](warehousing/simple/transferring-items.md)
3.	[Advanced Logistics Location](warehousing/advanced-logistics-location.md)
    1.	Receiving Scenarios
        1.	[Receiving & Put-Away with Bin Defaults](warehousing/advanced/receiving-put-away-with-bin-defaults.md)
        2.	[Receiving & Put-Away with Breakbulk](warehousing/advanced/receiving-put-away-with-breakbulk.md)
        3.	[Receiving & Put-Away with Bin Capacity Limits](warehousing/advanced/receiving-put-away-with-bin-capacity-limits.md)
    2.	[Warehouse Shipments](warehousing/advanced/warehouse-shipments.md)
    3.	[Cross-Docking with Warehousing](warehousing/advanced/cross-docking-with-warehousing.md)
    4.	[Transferring Items](warehousing/advanced/transferring-items.md)
    5.	[Moving Items with Directed Pick & Put Away](warehousing/advanced/moving-items-with-directed-pick-put-away.md)
    6.	[Adjusting Items with Directed Pick & Put Away](warehousing/advanced/adjusting-items-with-directed-pick-put-away.md)

> [!IMPORTANT]
> After running the [Warehousing Setup](warehousing/contoso-coffee-warehousing-intro.md), you will need to add [Warehouse Employees](warehousing/adding-warehouse-employee.md).


## See also

[Manufacturing](../production-manage-manufacturing.md)  
[Warehousing](../warehouse-manage-warehouse.md)  

