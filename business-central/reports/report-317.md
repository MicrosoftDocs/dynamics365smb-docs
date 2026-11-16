---
title: Vendor Pre-Payment Journal (Report)
description: Check unposted payment journal lines, applications, discounts, tolerances, and errors before creating payment files or posting in Business Central.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_317_Primary
ms.date: 11/13/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
ai-seo-date: 10/18/2024
ai-usage: ai-assisted
---

# Vendor Pre-Payment Journal (report)

The **Vendor Pre-Payment Journal** report shows unposted payment journal lines, their proposed applications, payment discounts, tolerances, and error messages. Use it to check payments before creating payment files or posting the journal. This report reviews payment journals before posting, not purchase prepayments.

> [!NOTE]
> The report shows payment discounts incorrectly if multiple credit memos were used in a payment application. In this case, the payment discounts for the extra credit memos show as unapplied amounts.

## Use cases

<!-- 
Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with procurement.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

## Report name
Vendor Pre-Payment Journal

### What the report does
The *Vendor Pre-Payment Journal* report shows the payment journal with payment discount and tolerance information. 
**Note**: The report shows payment discounts incorrectly when multiple credit memos were used in an application. In this case, the payment discounts for the extra credit memos are shown as unapplied amounts.

### Use cases
The report can be used to check payments before creating payment files and posting the journal.
It helps businesses ensure accuracy and compliance in their payment processes.

Please include your data sources and URLs
-->

Procurement officers use the report to:

* Review payment journals to check payment information, including discounts and tolerances, before creating payment files and posting the journal.
* Identify potential issues or discrepancies in the payment process and proactively address them.
* Get data to prepare payment reports or dashboards for internal or external stakeholders.

Accounts payable professionals use the report to:

* Review how payment journal lines will apply to vendor ledger entries.
* Identify discrepancies or errors in payment information and investigate them.
* Review unapplied amounts before posting the journal.

Financial analysts use the report to:

* Analyze payment information, such as discounts and tolerances, to identify areas to save cost or generate revenue.
* Review proposed payment amounts before they affect posted balances.
* Investigate errors in the payment journal.

## Try the report

Try the report here: [Vendor Pre-Payment Journal](https://businesscentral.dynamics.com?report=317)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Accounts payable analytics](../payables-reports.md)
[Key finance report overview](../finance-reports.md)  
[Ad hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]