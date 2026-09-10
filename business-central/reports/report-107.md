---
title: Customer - Order Summary (report)
description: See outstanding sales order amounts by customer, grouped into 30-day shipment periods, to gauge expected sales volume.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_107_Primary
ms.date: 09/10/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/10/2026
ai.usage: ai-assisted
---

# Customer - Order Summary (report)

The **Customer - Order Summary** report shows the outstanding quantity not yet shipped for each customer, broken down into three consecutive 30-day periods starting from a date you specify. It also includes columns for orders due before and after those three periods, plus a total order amount per customer, so you get a full picture of a customer's open order pipeline. The report can be generated with amounts shown in local currency (LCY) or in the original currency of each order.

You can filter the report by customer number, search name, customer posting group, and currency filter to narrow the report to specific customers or currencies. You also set a starting date, which determines the beginning of the three 30-day periods used to group outstanding order amounts, and you can choose whether amounts are shown in LCY.

## Use cases

[!INCLUDE [report-107-scenario](../includes/report-107-scenario-include.md)]

Sales managers can use the report to:

* Review which customers have large outstanding order volumes due for shipment in the next 30, 60, or 90 days.
* Identify customers with orders overdue for shipment by checking the 'before' period column.
* Plan capacity and prioritize order fulfillment based on upcoming shipment periods per customer.,Controllers and finance teams can use the report to:

* Estimate expected sales revenue by period using order amounts grouped by shipment date.
* Compare outstanding order amounts in LCY versus original currency to assess currency exposure.
* Use customer and currency filters to analyze order backlogs for specific markets or currency zones.

## Try the report

Try the report here: [Customer - Order Summary](https://businesscentral.dynamics.com?report=107)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sales reports](../sales-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
