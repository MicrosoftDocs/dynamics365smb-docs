---
title: Introduction to Contoso Coffee Manufacturing
description: Overview of scenarios for how Contoso Coffee demo data can help you learn how to use the manufacturing capabilities in Business Central.
ms.date: 04/01/2023
ms.topic: article
ms.service: dynamics-365-business-central
ms.search.form: 4765,
author: brentholtorf
ms.author: bholtorf
---

# Introduction to Contoso Coffee Manufacturing

Contoso Coffee is a fictitious company that produces consumer and commercial coffee makers. The **Contoso Coffee** apps for Business Central add demo data that you can use to learn how to use the manufacturing capabilities in Business Central.  

The app provides four products that are optimized for different scenarios:

- **SP-SCM1009 Airpot**  

  This product is a bill of material (BOM) with a subassembly, **Routing**. Use it to demonstrate the standard production flow. It's set up with alternative routings that you can use to demonstrate various scenarios that involve subcontractors. The costing method is *Standard*.  

- **SP-SCM1011 Airpot Duo**  

  This product requires item tracking and has a component that also requires item tracking. The costing method is *Specific*.  

- **SP-SCM1004 Autodrip**  

  This product is a BOM with a subassembly, **Routing**. We recommend it to demonstrate the various flushing methods both for components and operations. The costing method is *Standard*.

- **SP-SCM1006 AutoDripLite**

  This product has three variants and three bills of material (BOMs) that can be assigned to stockkeeping units. The product uses the phantom BOM concept. The costing method is *Standard*.

The manufacturing activities for all scenarios use the *MAIN* location.  

> [!IMPORTANT]
> Before you run any of the scenarios for Contoso Coffee, post any item journal lines with opening balances. For more requirements, see the [Set up Contoso Coffee data](#set-up-contoso-coffee-manufacturing-data) section.

## Set up Contoso Coffee Manufacturing data

[!INCLUDE [contoso-coffee-app-install](../../includes/contoso-coffee-app-install.md)]

|Field  |Description  |
|---------|---------|
|**Manufacturing Location** |Specifies the warehouse that you want to use for production operations. The default is *MAIN*, but you can change it to suit your needs.|


Once you're ready, choose the **Create Demo Data** action. It takes a few minutes to add the data to the underlying database, but then you're ready to run the various scenarios.  

## Scenarios

The Contoso Coffee manufacturing demo data currently supports the following scenarios for test and training:

1. [Create a New Production BOM and BOM Version](create-new-production-bom-version.md)  
2. [Create a New Routing](create-new-routing.md)  
3. [Create a Firm Planned Production Order and Change It](create-firm-planned-production-order-change.md)  
4. [Combine Automatic and Manual Flushing](combine-automatic-manual-flushing.md)  
5. [Use Order Planning to Create and Reserve Supply](order-planning-create-reserve-supply.md)  
6. [Set Up and Process a Subcontracting Operation](set-up-process-subcontracting-operation.md)  
7. [Set Up New Capacity](set-up-new-capacity.md)  
8. [Forecast demand for item variants with different BOMs assigned](variants.md)  

Read the steps for each scenario in the relevant article.  

> [!IMPORTANT]
> These walkthroughs require that the user experience is set to *Premium* in the **Company Information** page.

## Related information

[Manufacturing](../../production-manage-manufacturing.md)  
[Production Reports and Analytics in Business Central](../../production-reports.md)  
