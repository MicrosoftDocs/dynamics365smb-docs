---
title: Vendor - Order Detail (Report)
description: Review outstanding purchase order lines by vendor, including expected receipt dates, discounts, amounts, and back order quantities in Business Central.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_308_Primary
ms.date: 11/13/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
ai-seo-date: 10/07/2024
ai-usage: ai-assisted
---

# Vendor - Order Detail (report)

The **Vendor - Order Detail** report shows purchase order lines with outstanding quantities, grouped by vendor and order. The report includes:

* Outstanding purchase receipts.
* Applied line and invoice discounts.
* Outstanding amounts.

Lines with an **Expected Receipt Date** on or before the work date are included in the quantity on back order. You can filter by expected receipt date, show amounts in local currency, and start a new page for each vendor.

## Use cases

[!INCLUDE[report-308-scenario](../includes/report-308-scenario-include.md)]

<!-- 
Prompt
Below is a report in an ERP system. Provide 3-4 use cases for different personas working with procurement.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

## Report description

### What the report does
Shows each purchase order and the line level breakdown for each vendor, including information on outstanding purchase receipts, applied line/invoice discounts and outstanding amount. Any lines that have an Expected Receipt Date in the past are included in quantity on back order.

### Use cases
Analyze your outstanding purchase orders to understand your expected purchase volume grouped by vendor.

Compare your overall outstanding receipts with the expected receipt date to highlight any overdue back orders.

Please include your data sources and URLs 
-->

Procurement specialists use the report to:

* Analyze outstanding purchase orders from vendors. The report provides a concise view of outstanding purchase orders and their line-level breakdown for each vendor. Use this information to analyze your expected purchase volume by vendor and make informed decisions about managing your purchasing activities.
* Identify overdue back orders. The report includes information about outstanding receipts and expected receipt dates for each purchase order. Use this information to compare overall outstanding receipts with the expected receipt date to highlight overdue back orders. This comparison can help identify potential supply chain issues so that you can take action to avoid delays.

Procurement managers use the report to:

* Review expected receipts. Use outstanding quantities and expected receipt dates to follow up with vendors.
* Review purchase commitments. Compare outstanding amounts and discounts across open order lines.

## Try the report

Try the report here: [Vendor - Order Detail](https://businesscentral.dynamics.com?report=308)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Purchase reports](../purchase-reports.md)  
[Ad hoc analysis of purchasing data](../ad-hoc-analysis-purchasing.md)  
[Purchasing analytics overview](../purchasing-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]

