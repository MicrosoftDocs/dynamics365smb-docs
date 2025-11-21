---
title: Inventory Order Details (report)
description: Analyze outstanding sales orders to understand your expected sales volume for items. To highlight any overdue back orders, compare your overall outstanding shipments with the planned shipment date.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_708_Primary
ms.date: 10/03/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/07/2024
ai.usage: ai-assisted
---

# Inventory Order Details (report)

The **Inventory Order Details** report shows each sales order and the line-level breakdown for each item (such as the order number, customer's name, shipment date, order quantity, delayed quantity, outstanding quantity, and unit price). The information includes unfulfilled shipments, applied line and invoice discounts, and the total amount on order.

Lines with a shipment date in the past are included in the quantity on back order.

## Use cases

<!-- 
Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with sales and order shipment.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

# Report name 
Inventory Order Details 

## Report description
Displays a list of the orders that haven't yet been shipped and the items in the orders. It shows the order number, customer's name, shipment date, order quantity, delayed quantity, outstanding quantity, and unit price, as well as any potential discount percentage and amount. The quantity on back order and outstanding quantity and amount are totaled for each item. Use the report to find out whether there are currently shipment problems or any can be expected.

### What the report does
Shows each sales order and the line level breakdown for each item, including information on unfulfilled shipments, applied line/invoice discounts and total amount on order. Any lines that have a shipment date in the past are included in quantity on back order.


### Use cases
Analyse your outstanding sales orders to understand your expected sales volume grouped by item.
Compare your overall outstanding shipments with the planned shipment date to highlight any overdue back orders.

Please include your data sources and URLs

-->

Sales representatives use the report to:

* Track order status to keep customers updated.
* Spot potential shipment issues to manage customer expectations.
* Determine which orders to prioritize, based on shipment status and expected delivery dates.

Sales managers use the report to:

* Understand expected sales volumes for items by analyzing outstanding sales orders.
* Highlight overdue back orders by comparing overall outstanding shipments with the planned shipment date.
* Address customer complaints proactively by identifying shipments that are delayed or at risk of being delayed.

Logistics coordinators use the report to:

* Optimize shipment schedules by monitoring back orders.
* Prevent revenue leakage by ensuring accurate discount application.
* Proactively address potential issues and ensure that shipments are on schedule.

## Try the report

Try the report here: [Inventory Order Details](https://businesscentral.dynamics.com?report=708)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sales reports](../sales-reports.md)  
[Ad hoc analysis of sales data](../ad-hoc-analysis-sales.md)  
[Sales analytics overview](../sales-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
