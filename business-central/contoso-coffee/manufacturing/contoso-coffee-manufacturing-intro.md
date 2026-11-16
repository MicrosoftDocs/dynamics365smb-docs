---
title: Introduction to Contoso Coffee Manufacturing
description: Overview of scenarios for how Contoso Coffee demo data can help you learn how to use the manufacturing capabilities in Business Central.
ms.date: 11/12/2026
ms.topic: overview
ms.service: dynamics-365-business-central
ms.search.form: 4765,
author: brentholtorf
ms.author: bholtorf
ai-usage: ai-assisted
---

# Introduction to Contoso Coffee manufacturing

Contoso Coffee is a fictitious company that produces consumer and commercial coffee makers. The **Contoso Coffee** apps for Business Central add demo data that you can use to learn how to use the manufacturing capabilities in Business Central.  

The app provides four products that are optimized for different scenarios:

- **SP-SCM1009 Airpot**  

  This item has a production bill of materials (BOM) that includes the **SP-BOM2000, Reservoir Assembly** subassembly. Its default routing is **SP-SCM1009-SERIAL**. Use it to demonstrate the standard production flow. It's set up with alternative routings for parallel operations and subcontracting scenarios. The costing method is *Standard*.

- **SP-SCM1011 Airpot Duo**  

  This product requires item tracking and has a component that also requires item tracking. The costing method is *Specific*.  

- **SP-SCM1004 Autodrip**  

  This item has a production BOM with the **SP-BOM2000, Reservoir Assembly** subassembly and routing **SP-SCM1004**. We recommend it to demonstrate the various flushing methods both for components and operations. The costing method is *FIFO*.

- **SP-SCM1006 AutoDripLite**

  This product has three variants and three color-specific production BOMs that can be assigned to stockkeeping units. Each color-specific BOM includes the **SP-SCM1006-BASE** phantom BOM. The costing method is *FIFO*.

The walkthroughs use the default **Manufacturing Location**, **MAIN**. If you configure another location, use that location instead.

> [!IMPORTANT]
> Generate the **Manufacturing** module before you start a walkthrough. Generation creates the items, certified production BOMs, routings, and work and machine centers. It also posts opening component inventory automatically. Installing the apps or choosing **Generate Setup Data** alone doesn't create these records.

## Set up Contoso Coffee manufacturing data

[!INCLUDE [contoso-coffee-app-install](../../includes/contoso-coffee-app-install.md)]

Open the **Contoso Demo Tool** page, select **Manufacturing**, and choose **Configure**. The following table describes the settings:

|Field  |Description  |
|---------|---------|
|**Manufacturing Location** |Specifies the warehouse that you want to use for production operations. The default is *MAIN*, but you can change it to suit your needs.|
|**Subcontracting Location**|Specifies the location for subcontracting inventory posting setup. The default is **S82000, Bulk Assembly**. Generation also creates **S83000, Local Assembly**, for the other subcontractor.|


For shared settings such as the starting year and price factor, configure **Common**. Then return to **Contoso Demo Tool**, select **Manufacturing**, and choose **Generate**. Required dependency modules are generated automatically. Learn more in [Set up Contoso Coffee data](../contoso-coffee-intro.md#set-up-contoso-coffee-data).

## Explore manufacturing scenarios

The Contoso Coffee manufacturing demo data currently supports the following scenarios for test and training:

1. [Create a New Production BOM and BOM Version](create-new-production-bom-version.md)  
2. [Create a New Routing](create-new-routing.md)  
3. [Create a Firm Planned Production Order and Change It](create-firm-planned-production-order-change.md)  
4. [Combine Automatic and Manual Flushing](combine-automatic-manual-flushing.md)  
5. [Use Order Planning to Create and Reserve Supply](order-planning-create-reserve-supply.md)  
6. [Set Up and Process a Subcontracting Operation](set-up-process-subcontracting-operation.md)  
7. [Use Different Component Supply Methods in Subcontracting](subcontracting-component-supply-methods.md)  
8. [Set Up Subcontracting Prices and Allocate Item Charges](subcontracting-pricing-item-charges.md)  
9. [Set Up New Capacity](set-up-new-capacity.md)  
10. [Forecast demand for item variants with different BOMs assigned](variants.md)  

Read the steps for each scenario in the relevant article.  

> [!IMPORTANT]
> These walkthroughs require that you set the user experience to **Premium** on the **Company Information** page. Learn how to [select the Premium experience](../../ui-experiences.md#to-select-the-premium-experience).

## Related information

[Manufacturing](../../production-manage-manufacturing.md)  
[Production Reports and Analytics in Business Central](../../production-reports.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
