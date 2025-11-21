---
title: Inventory Sales Back Orders (report)
description: Get an overview of sales orders that can't be fulfilled because of out-of-stock items. 
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_718_Primary
ms.date: 10/03/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/07/2024
ai.usage: ai-assisted
---

# Inventory Sales Back Orders (report)

The **Inventory Sales Back Orders** report shows sales lines where you can't fulfill the outstanding quantity by the specified shipment date.

The report groups data by item and includes:

* Customer details.
* The ship date.
* Other back-ordered items for the customer.

The report shows the following data for individual orders for each item:

* Number
* Customer name
* Customer telephone number
* Shipment date
* Order quantity
* Quantity on back order

## Use cases

<!-- 
Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with sales and order fullfilment.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

## Report description
Shows a list with the order lines whose shipment date has been exceeded. The following information is shown for the individual orders for each item: number, customer name, customer's telephone number, shipment date, order quantity and quantity on back order. The report also shows whether there are other items for the customer on back order.

### What the report does
Shows sales lines where the outstanding quantity can't be fulfilled by the specified shipment date. 

This information is grouped by item and includes detail on the customer that ordered the item, when it was due to be shipped, and whether the customer is also awaiting supply on any other back ordered items.

### Use cases
See an overview of sales orders that can't be fulfilled due to out-of-stock items. 

Please include your data sources and URLs
-->

Sales representatives use the report to:

* Keep customers informed about the status of their orders.
* Prioritize orders that are delayed, to ensure that they are fulfilled as soon as possible.
* Identify any potential issues with order fulfillment and work with logistics teams to resolve them.

Sales managers use the report to:

* Identify orders that are delayed and take proactive measures to address customer complaints.
* Monitor orders that they can't fulfill on time and work with logistics teams to resolve any issues.
* Analyze trends in delayed shipments to identify areas for improvement in order fulfillment processes.

Logistics coordinators use the report to:

* Monitor orders that they can't fulfill on time and take action to expedite the process.
* Identify trends in delayed shipments and work with sales and production teams to address the root causes.
* Optimize shipment schedules to fulfill orders on time.

## Try the report

Try the report here: [Inventory Sales Back Orders](https://businesscentral.dynamics.com?report=718)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sales reports](../sales-reports.md)  
[Ad hoc analysis of sales data](../ad-hoc-analysis-sales.md)  
[Sales analytics overview](../sales-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
