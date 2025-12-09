---
title: Fixed Asset Book Value 02 (report)
description: View the movement in valuation of assets over a period time with a breakdown of values under additions and disposals during the period.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_5606_Primary
ms.date: 10/23/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/23/2024
ai.usage: ai-assisted
---

# Fixed Asset Book Value 02 (report)

The **Fixed Asset Book Value 02** report shows the breakdown of fixed asset book value by changes in acquisition, depreciation, and appreciation within the period, with a further breakdown by additions and disposals within the period.

To include information about Write-downs, Appreciation, Custom 1, and Custom 2 posting types in the report, select either the **Acquisition Type** or the **Depreciation Type* fields on the **FA Posting Type Setup** page.

You can include reclassified entries in the report. The report then shows the reclassification entries in a separate column.

If you select the **Budget Report** field, the report calculates the expected depreciation for the period.

Enter a group type if you want to group the fixed assets and show group totals. For example, if you have six FA classes, select the **FA Class** option to print group totals for each FA class.

Use this report to describe the changes in fixed assets for a given period when there are many changes across groups of fixed assets.


## Fixed Asset Book Value reports

[!INCLUDE[report-5605-5606-difference](../includes/report-5605-5606-difference.md)]


## Use cases

[!INCLUDE[report-5606-scenario](../includes/report-5606-scenario-include.md)]

<!-- 

Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with fixed asset management or finance for fixed assets.

Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

Do not start lines with "Use the data to"

## Report name
Fixed Asset Book Value 02

### What the report does
The *Fixed Asset Book Value 02* report shows the movement in valuation of assets over a period time.
To obtain information on Write-downs, Appreciation, Custom 1, and Custom 2 posting types included in the Book Value 02 report, select either the Acquisition Type or the Depreciation Type field in the FA Posting Type Setup window. 
You can include reclassified entries in the Book Value 02 report.
Also, you can select the Budget Report check box to calculate depreciation from the last FA posting date up to the specified ending date. 
The report is useful when the you want to view the movement in valuation of assets over a period time. There is further breakdown of values under additions and disposals during the period, further grouped under classes/subclasses if needed.

### Use cases
View the movement in valuation of assets over a period time with a breakdown of values under additions and disposals during the period, further grouped under classes/subclasses, if needed.

Please include your data sources and URLs

-->

Fixed asset managers use the report to:

* Track the value of fixed assets over time and identify trends or patterns in their valuation.
* Analyze the effect of acquisitions, disposals, and reclassifications on the overall value of fixed assets.
* Identify discrepancies or errors in the fixed asset ledger entries and work with the accounting team to correct them.

Financial analysts use the report to:

* Analyze the movement in valuation of fixed assets over time and identify trends or patterns.
* Calculate the return on investment for fixed assets and assess their overall contribution to an organization's financial performance.
* Identify discrepancies or errors in the fixed asset ledger entries and work with the accounting team to correct them.

Accountants use the report to:

* Reconcile the book value of fixed assets with the general ledger and ensure that they're accurate.
* Identify and correct errors or discrepancies in fixed asset transactions and the depreciation book setup.
* Track the value of fixed assets over time and assess their overall contribution to an organization's financial performance.

## Try the report

Try the report here: [Fixed Asset Book Value 02](https://businesscentral.dynamics.com?report=5606)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Fixed assets report overview](../fa-reports.md)  
[Ad hoc analysis of fixed assets data](../ad-hoc-analysis-fa.md)  
[Fixed assets analytics overview](../fa-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]