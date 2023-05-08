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
 - The [Service Setup](service/contoso-coffee-service-intro.md) to prepare for user of the [Service Scenarios](#service-scenarios)

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

1.	Configure default bins, receive and put-away with inventory put-away, pick and ship with inventory pick in order-by-order fashion with [Walkthrough of inbound and outbound flow in Basic Warehouse Configurations](warehousing/warehouse-basic-flow-putaway-pick.md)
2.	Receive and put-away multiple inbound orders at once with warehouse receipt, ship multiple orders at once with warehouse shipment, pick with warehouse picks with [Walkthrough of inbound and outbound flow in mixed Warehouse Configurations](warehousing/warehouse-mixed-flow-receive-pick-ship.md)
3.	Configure fixed bins for item unit of measure, user cross-docking to reduce physical movements of goods, optimize placing of goods with bin replenishment, break-bulk large units of measure into smaller ones, distribute picking among warehouse employes with picking worksheet with [Walkthrough of inbound and outbound flow in Advanced Warehouse Configuration with Directed Put-away and Pick](warehousing/warehouse-directed-flow.md)

Read the steps for each scenario in the relevant article.
   
## Service Scenarios

The Contoso Coffee demo data currently supports the following manufacturing scenarios for test and training:

1. Create service items through sale of items, place and receive Loaners, register time, and invoice customers with [Walkthrough of Service Orders for Service Items](service/service-basic-flow-order.md)
2. Create service contracts, generate service orders, invoice contract fees, and allocate resources with [Walkthrough of Service Contracts for Service Items](service/service-contract-flow.md)

Read the steps for each scenario in the relevant article.  

> [!IMPORTANT]
> The Service walkthroughs require that the user experience is set to *Premium* in the **Company Information** page.


## See also

[Manufacturing](../production-manage-manufacturing.md)  
[Warehousing](../warehouse-manage-warehouse.md)  
[Service](../service-service.md)

