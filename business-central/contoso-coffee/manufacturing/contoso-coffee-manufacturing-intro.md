---
title: Introduction to Contoso Coffee Manufacturing
description: Overview of scenarios for how Contoso Coffee demo data can help you learn how to use the manufacturing capabilities in Business Central.
ms.date: 04/01/2022
ms.topic: article
ms.service: dynamics365-business-central
ms.search.form: 4760
author: edupont04
ms.author: andreipa
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

The manufacturing activities for all scenarios use the *NORTH* location.  

> [!IMPORTANT]
> Before you run any of the scenarios for Contoso Coffee, post any item journal lines with opening balances. For more requirements, see the [Set up Contoso Coffee data](#set-up-contoso-coffee-manufacturing-data) section.

## Set up Contoso Coffee Manufacturing data

To use the Contoso Coffee Manufacturing demo data, you must install two apps in the relevant company in [!INCLUDE [prod_short](../includes/prod_short.md)]:  

- **Contoso Coffee Demo Dataset**  

    This app delivers demo data for the base application.  
- **Contoso Coffee Demo Dataset (country ID)**  

    This app adds country-specific content on top of the base application.

Add the apps to an empty company in a paid subscription or as part of a trial. For example, create a new company with no sample data from the **Create New Company** assisted setup guide that you can open from the **Companies** list. Then add the apps from the [marketplace](../../ui-extensions-install-uninstall.md#install) if they are not already listed in the **Extension Management** page.  

Once the relevant apps are installed, go to the [Contoso Coffee Demo Data](https://businesscentral.dynamics.com/?page=4760) page in [!INCLUDE [prod_short](../../includes/prod_short.md)], and change the default settings to suit your needs. The following tables describes the settings:  

|Field  |Description  |
|---------|---------|
|**Starting Year** |Specifies the first year that you you want to use for the Contoso Coffee demonstration data. Depending on the company setup, the year is either a calendar year or a fiscal year.|
|**Manufacturing Location** |Specifies the warehouse that you want to use for production operations. The default is *NORTH*, but you can change it to suit your needs.|
|**Company Type**    |Specifies if the current company must report VAT or sales tax. |
|**Domestic - General Business Posting Group**|Specifies a business code for domestic customers and vendors. The business codes are used when transactions are posted. |
|**Capacity - General Product Posting Group**    |Specifies a code for items or resources that must be used for posting capacity.|
|**Retail - General Product Posting Group**    |Specifies a code for items or resources that must be used for posting retail.|
|**Raw - General Product Posting Group**    |Specifies a code for items or resources that must be used for posting raw material. |
|**Base VAT Code**    |Specifies an existing VAT product group that will be used for items.|
|**Finished Code**    |Specifies an existing product group that will be used for finished items.|
|**Price Factor**     |Specifies a factor to convert a price from USD/EUR to the local currency. *1* means that the price is the same amount in any currency. A higher number will be used to get the price in the local currency. |
|**Rounding Precision**  |Defines how calculated consumption quantities are rounded when entered on consumption journal lines. Quantities less than 0.5 will be rounded down. Quantities equal to or greater than 0.5 will be rounded up.|

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

## See also

[Manufacturing](../../production-manage-manufacturing.md)  
[Production Reports and Analytics in Business Central](../../production-reports.md)  
