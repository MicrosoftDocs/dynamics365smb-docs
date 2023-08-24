---
title: Introduction to Contoso Coffee 
description: Overview of scenarios for how Contoso Coffee demo data can help you learn how to use the warehousing capabilities in Business Central.
ms.date: 04/01/2022
ms.topic: article
ms.service: dynamics365-business-central
ms.search.form: 4760
author: brentholtorf04
ms.author: andreipa
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

To use the Contoso Coffee Warehousing demo data, you must install two apps in the relevant company in [!INCLUDE [prod_short](../../includes/prod_short.md)]:  

- **Contoso Coffee Demo Dataset**  

    This app delivers demo data for the base application.  
- **Contoso Coffee Demo Dataset (country ID)**  

    This app adds country-specific content on top of the base application.

Add the apps to an empty company in a paid subscription or as part of a trial. For example, create a new company with no sample data from the **Create New Company** assisted setup guide that you can open from the **Companies** list. Then add the apps from the [marketplace](../../ui-extensions-install-uninstall.md#install) if they are not already listed in the **Extension Management** page.  

Once the relevant apps are installed, go to the [Contoso Coffee Whse Demo Data](https://businesscentral.dynamics.com/?page=4761) page in [!INCLUDE [prod_short](../../includes/prod_short.md)], and change the default settings to suit your needs. The following table describes the settings:  

|Field  |Description  |
|---------|---------|
|**Starting Year** |Specifies the first year that you want to use for the Contoso Coffee demonstration data. Depending on the company setup, the year is either a calendar year or a fiscal year.|
|**Location Bin**  |The location to use for the basic Location scenarios.|
|**Location Adv. Logistics**  |The location to use for the simple logistics scenarios.|
|**Location Directed Put-Away and Pick**  |The location to use for the advanced logistics scenarios.|
|**Location In-Transit**  |The location to use for the in-transit location in transfer scenarios.|
|**Customer No.**  |The customer to use for the basic and simple scenarios in sales operations.|
|**Vendor No.**  |The vendor to use for all scenarios in purchasing operations.|
|**Main Item No.**  |The item to use for all scenarios in sales operations.|
|**Item 1 No.**  |The main item to use for all scenarios.|
|**Item 2 No.**  |The extra item to use for all scenarios.|
|**Customer Posting Group**|Specifies a business code for domestic customers. The business codes are used when transactions are posted. |
|**Customer General Business Posting Group**|Specifies a business code for domestic customers. The business codes are used when transactions are posted. |
|**Vendor Posting Group**|Specifies a business code for domestic customers and vendors. The business codes are used when transactions are posted. |
|**Vendor General Business Posting Group**|Specifies a business code for domestic customers and vendors. The business codes are used when transactions are posted. |
|**Domestic - VAT Business Posting Group**|Specifies a VAT business code for customers and vendors for posting VAT if VAT is enabled.|
|**Resale - Inventory Posting Group**    |Specifies a code for items that must be used for posting resale.|
|**Retail - General Product Posting Group**    |Specifies a code for items that must be used for posting retail.|
|**VAT Product Posting Group**    |Specifies a VAT product code for items for posting VAT if VAT is enabled.|
|**Price Factor**     |Specifies a factor to convert a price from USD/EUR to the local currency. *1* means that the price is the same amount in any currency. A higher number will be used to get the price in the local currency. |
|**Rounding Precision**  |Defines how calculated consumption quantities are rounded when entered on consumption journal lines. Quantities less than 0.5 will be rounded down. Quantities equal to or greater than 0.5 will be rounded up.|

Once you're ready, choose the **Create Demo Data** action. It takes a few minutes to add the data to the underlying database, but then you're ready to run the various scenarios.  

> [!IMPORTANT]
> If you are running the Scenarios, you may want to verify that your user has been added as for selected locations. For more information, see [Set Up Warehouse Employees](../../warehouse-how-to-set-up-warehouse-employees.md).

## Scenarios

The Contoso Coffee warehousing demo data currently supports the following scenarios for test and training:

1.	[Walkthrough of inbound and outbound flow in Basic Warehouse Configurations](warehouse-basic-flow-putaway-pick.md)
2.	[Walkthrough of inbound and outbound flow in mixed Warehouse Configurations](warehouse-mixed-flow-receive-pick-ship.md)
3.	[Walkthrough of inbound and outbound flow in Advanced Warehouse Configuration with Directed Put-away and Pick](warehouse-directed-flow.md)

Read the steps for each scenario in the relevant article.  

## See also

[Setting Up Inventory](../../inventory-setup-inventory.md) 
[How to Setup Locations](../../inventory-how-setup-locations.md) 
[Warehousing](../../warehouse-manage-warehouse.md) 
[Design Details](../../design-details-warehouse-overview.md) 
