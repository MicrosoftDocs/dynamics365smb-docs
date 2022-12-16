---
title: Introduction to Contoso Coffee 
description: Overview of scenarios for how Contoso Coffee demo data can help you learn how to use the warehousing capabilities in Business Central.
ms.date: 04/01/2022
ms.topic: article
ms.service: dynamics365-business-central
ms.search.form: 4760
author: edupont04
ms.author: andreipa
---

# Introduction to Contoso Coffee Warehousing

Contoso Coffee is a fictitious company that produces consumer and commercial coffee makers. The **Contoso Coffee** apps for Business Central add demo data that you can use to learn how to use the warehousing capabilities in Business Central.  

The app provides three locations that are optimized for different scenarios:

- **SILVER**  

  This Location uses a Basic configuration.  The Location requires Bins.  Logistic Operations use Inventory Put-Aways and Picks. 

- **YELLOW**  

  This Location uses the Simple Logistics configuation.  The Logistics Operations use Warehouse Documents for Put-Away, Picks, Shipments and Receipts.

- **WHITE**  

  This Location uses the Advanced Logistics configuation.  The Logistics Operations use Warehouse Documents for Put-Away, Picks, Shipments and Receipts.  Additionally, with Direct Pick and Put-Away enabled, more advanced rules apply to how items move throughout Warehouse Operations.

> [!IMPORTANT]
> Before you run any of the scenarios for Contoso Coffee, post any item journal lines with opening balances. For more requirements, see the [Set up Contoso Coffee data](#set-up-contoso-coffee-warehousing-data) section.

## Set up Contoso Coffee Warehousing data

To use the Contoso Coffee Warehousing demo data, you must install two apps in the relevant company in [!INCLUDE [prod_short](../../includes/prod_short.md)]:  

- **Contoso Coffee Demo Dataset**  

    This app delivers demo data for the base application.  
- **Contoso Coffee Demo Dataset (country ID)**  

    This app adds country-specific content on top of the base application.

Add the apps to an empty company in a paid subscription or as part of a trial. For example, create a new company with no sample data from the **Create New Company** assisted setup guide that you can open from the **Companies** list. Then add the apps from the [marketplace](../../ui-extensions-install-uninstall.md#install) if they are not already listed in the **Extension Management** page.  

Once the relevant apps are installed, go to the [Contoso Coffee Whse Demo Data](https://businesscentral.dynamics.com/?page=4761) page in [!INCLUDE [prod_short](../../includes/prod_short.md)], and change the default settings to suit your needs. The following tables describes the settings:  

|Field  |Description  |
|---------|---------|
|**Starting Year** |Specifies the first year that you you want to use for the Contoso Coffee demonstration data. Depending on the company setup, the year is either a calendar year or a fiscal year.|
|**Location Basic**  |The location to use for the basic Location scenarios.|
|**Location Simple Logistics**  |The location to use for the simple logistics scenarios.|
|**Location Advanced Logistics**  |The location to use for the advanced logistics scenarios.|
|**Location In-Transit**  |The location to use for the in-transit location in transfer scenarios.|
|**Small Customer No.**  |The customer to use for the basic and simple scenarios in sales operations.|
|**Large Customer No.**  |The customer to use for the advanced scenarios in sales operations.|
|**Vendor No.**  |The vendor to use for all scenarios in purchasing operations.|
|**Main Item No.**  |The item to use for the basic and simple scenarios, as well as some advanced scenarios.|
|**Complex Item No.**  |The item to use for advanced scenarios with unit of measure conversions.|
|**CrossDock Item No.**  |The item to use for the cross-dock scenarios.|
|**Customer Posting Group**|Specifies a business code for domestic customers. The business codes are used when transactions are posted. |
|**Customer General Business Posting Group**|Specifies a business code for domestic customers. The business codes are used when transactions are posted. |
|**Vendor Posting Group**|Specifies a business code for domestic customers and vendors. The business codes are used when transactions are posted. |
|**Vendor General Business Posting Group**|Specifies a business code for domestic customers and vendors. The business codes are used when transactions are posted. |
|**Domestic - General Business Posting Group**|Specifies a business code for domestic customers and vendors. The business codes are used when transactions are posted. |
|**Resale - Inventory Posting Group**    |Specifies a code for items that must be used for posting resale.|
|**Retail - General Product Posting Group**    |Specifies a code for items that must be used for posting retail.|
|**VAT Product Posting Group**    |Specifies a VAT product code for items for posting VAT if VAT is enabled..|
|**Price Factor**     |Specifies a factor to convert a price from USD/EUR to the local currency. *1* means that the price is the same amount in any currency. A higher number will be used to get the price in the local currency. |
|**Rounding Precision**  |Defines how calculated consumption quantities are rounded when entered on consumption journal lines. Quantities less than 0.5 will be rounded down. Quantities equal to or greater than 0.5 will be rounded up.|

Once you're ready, choose the **Create Demo Data** action. It takes a few minutes to add the data to the underlying database, but then you're ready to run the various scenarios.  

> [!IMPORTANT]
> If you are running the Scenarios, you may want to verify that your user has been added as a [Warehouse Employees](adding-warehouse-employee.md).

## Scenarios

The Contoso Coffee warehousing demo data currently supports the following scenarios for test and training:

1.	[Basic Location](basic-location.md)
    1.	[Receiving Items with Inventory Put-Away](basic/receiving-items-with-inventory-put-away.md)
    2.	[Shipping Items with Inventory Picks](basic/shipping-items-with-inventory-picks.md)
    3.	[Transferring Items](basic/transferring-items.md)
    4.	[Moving Items Between Bins](basic/moving-items-between-bins.md)
    5.	[Adjusting Items out of Inventory](basic/adjusting-items-out-of-inventory.md)
2.	[Simple Logistics Location](simple-logistics-location.md)
    1.	[Receiving a Single Order with Whse. Receipt](simple/receiving-a-single-order-with-whse-receipt.md)
    2.	[Combining Orders on a Whse. Receipt](simple/combining-orders-on-a-whse-receipt.md)
    3.	[Shipping a Single Order with Whse. Shipment](simple/shipping-a-single-order-with-whse-shipment.md)
    4.	[Combining Orders on a Whse. Shipment](simple/combining-orders-on-a-whse-shipment.md)
    5.	[Transferring Items](simple/transferring-items.md)
3.	[Advanced Logistics Location](advanced-logistics-location.md)
    1.	Receiving Scenarios
        1.	[Receiving & Put-Away with Bin Defaults](advanced/receiving-put-away-with-bin-defaults.md)
        2.	[Receiving & Put-Away with Breakbulk](advanced/receiving-put-away-with-breakbulk.md)
        3.	[Receiving & Put-Away with Bin Capacity Limits](advanced/receiving-put-away-with-bin-capacity-limits.md)
    2.	[Warehouse Shipments](advanced/warehouse-shipments.md)
    3.	[Cross-Docking with Warehousing](advanced/cross-docking-with-warehousing.md)
    4.	[Adjusting Items with Directed Pick & Put Away](advanced/adjusting-items-with-directed-pick-put-away.md)
    5.	[Transferring Items](advanced/transferring-items.md)
    6.	[Moving Items with Directed Pick & Put Away](advanced/moving-items-with-directed-pick-put-away.md)

Read the steps for each scenario in the relevant article.  

## See also

[Setting Up Inventory](../../inventory-setup-inventory.md)
[How to Setup Locations](../../inventory-how-setup-locations.md)
[Warehousing](../../warehouse-manage-warehouse.md)
[Design Details](../../design-details-warehouse-overview.md)
