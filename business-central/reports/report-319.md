---
title: Payments on Hold Report in Business Central
description: Review open vendor ledger entries with an On Hold value to follow up on held payments. Learn about alternatives to this obsolete report.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_319_Primary
ms.date: 11/13/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
ai-usage: ai-assisted
ai-seo-date: 10/07/2024
---

# Payments on Hold (report)

The **Payments on Hold** report shows open vendor ledger entries where the **On Hold** field isn't blank. Closed entries aren't included. Use the report to review payments that are on hold, including entries related to vendor disputes.

> [!NOTE]
> This report is obsolete. You can instead filter the **Vendor Ledger Entries** page by **Open** and **On Hold**, as described under [Alternative reports](#alternative-reports).

Learn more in [Handling vendor payment disputes](../payables-how-handling-payment-disputes.md).

## Use cases

[!INCLUDE[report-319-scenario](../includes/report-319-scenario-include.md)]

<!-- 
Prompt
Below is a report in an ERP system. Provide 3-4 use cases for different personas working with procurement.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

## Report description
Shows vendor ledger entries where the On Hold field isn't blank.

### What the report does
Vendor ledger entries may be placed on On Hold, if there is a dispute/query about the supplier document. To place any entry On Hold, enter a non-blank value as there is no validation on this field.

This report will then allow you to print a checklist of all vendor ledger entries where the On Hold field isn't blank.

### Use cases
Print a checklist of all vendor ledger entries where the invoice is in dispute and the On Hold field isn't blank.

Please include your data sources and URLs
 -->

Procurement coordinators use the report to:

* Manage vendor disputes. The report provides a checklist of open vendor ledger entries where the **On Hold** field isn't blank. Use this information to investigate entries that need follow-up.

Accounts payable specialists use the report to:

* Review held payments. The report provides information about open vendor ledger entries that are on hold. An **On Hold** value doesn't identify the reason for the hold.

Controllers use the report to:

* Evaluate vendor performance. The report provides valuable insights into vendor disputes and queries. Use this information to evaluate vendor performance and identify potential issues that might affect financial performance.

## Try the report

Try the report here: [Payments on Hold](https://businesscentral.dynamics.com?report=319)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Alternative reports

There are multiple other options for analyzing entries on hold. 

For instance, on the **Vendor Ledger Entries** page, set **Open** to **Yes** and set a filter on the **On Hold** field to this value:
``` Filter
<>''
```

Or, you can take the vendor ledger entries list page into analysis mode and define an analysis tab. Learn more in [Using data analysis to show vendor ledger entries on hold](../ad-hoc-analysis-purchasing.md#example-finance-accounts-payable---vendor-ledger-entries-on-hold)

## Contributors

[!INCLUDE [contributor_credit](../includes/contributor_credit.md)]

- [Cynthia Priebe](https://www.linkedin.com/in/cynthia-priebe-dcp/) | Microsoft MVP and Business Central Functional Consultant


## Related information

[Handling vendor payment disputes](../payables-how-handling-payment-disputes.md)   
[Ad hoc analysis of purchasing data](../ad-hoc-analysis-purchasing.md)  
[Purchase reports](../purchase-reports.md)  
[Purchasing analytics overview](../purchasing-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
