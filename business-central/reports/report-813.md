---
title: Inventory Picking List (report)
description: View which sales orders are covered when collecting items from inventory.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_813_Primary
ms.date: 10/03/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/07/2024
ai.usage: ai-assisted
---

# Inventory Picking List (report)

The **Inventory Picking List** report shows a list of the sales orders that include a particular item.

The report shows the following information for each item: 

* Sales order line
* Customer name
* Variant code
* Location code
* Bin code
* Shipment date
* Quantity to ship
* Unit of measure

The quantity to ship is a total for each item.

> [!NOTE]
> This report isn't available for advanced warehouse functionality.

## Use cases

<!-- 
Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with sales and order fullfilment.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

## Report name
Inventory Picking List

## Report description
The *Inventory Picking List* report shows a list of the sales orders for which an item is included. 

The following information is shown for each item: Sales order line with the name of the customer, variant code, location code, bin code, shipment date, quantity to be shipped, and unit of measure. 

The quantity to be shipped is totaled for each item. 

### Use cases
Streamline the process of gathering items from inventory to fulfill orders. 

Please include your data sources and URLs

-->

Sales representatives use the report to:

* Keep customers informed about the status of their orders.
* Identify any potential delays in fulfillment and work with the warehouse team to address them.
* Prioritize orders based on the shipment date and fulfill them on time.

Warehouse managers use the report to:

* Streamline the picking process when fulfilling orders.
* Assign picking tasks to warehouse personnel.
* Optimize warehouse operations by identifying items that are often ordered together.

Logistics coordinators use the report to:

* Monitor the progress of order fulfillment and ship orders on time.
* Optimize shipment schedules and efficiently fulfill orders.
* Identify potential bottlenecks and work with the warehouse team to address them.

## Try the report

Try the report here: [Inventory Picking List](https://businesscentral.dynamics.com?report=813)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sales reports](../sales-reports.md)  
[Ad hoc analysis of sales data](../ad-hoc-analysis-sales.md)  
[Sales analytics overview](../sales-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
