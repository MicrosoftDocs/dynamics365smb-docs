---
title: G/L Consolidation Eliminations (report)
description: Identifies and removes internal transactions between entities to prevent duplication in consolidated financial statements.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting, consolidation, intercompany
ms.search.form: Report_16_Primary
ms.date: 06/18/2025
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 06/18/2025
ai.usage: ai-assisted
---

# G/L Consolidation Eliminations (report)

The **G/L Consolidation Eliminations** report is used during intercompany (IC) financial consolidation to remove duplicate revenue and expense balances. It ensures consolidated financial statements are free of double counting by eliminating internal entries, which is essential for compliant reporting.

Run this report after you post all intercompany (IC) transactions to ensure accuracy.

## Use cases

[!INCLUDE [report-16-scenario](../includes/report-16-scenario-include.md)]

> [!TIP]
> Here are some tips on how to use the report:
>
> * Always run this report after all IC transactions are posted.
> * Review the output to ensure all expected eliminations are captured.
> * Use with your consolidation schedule to maintain accuracy.

Controllers and financial analysts can use the report to:

* Eliminate internal transactions between entities during financial consolidation.
* Ensure group-level financial statements reflect only external transactions.
* Maintain compliance with financial reporting standards by avoiding duplication.

Auditors can use the report to:

* Verify that intercompany entries are properly eliminated.
* Confirm the integrity of consolidated financial data.

## Try the report

Try the report here: [G/L Consolidation Eliminations](https://businesscentral.dynamics.com?report=16)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Set Up Company Consolidation](../finance-consolidated-company-reporting-setup.md)  
[Built-in key finance reports](../finance-reports.md)  
[Ad hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]