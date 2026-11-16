---
title: G/L Consolidation Eliminations (Report)
description: Preview prepared consolidation elimination journal lines alongside consolidated balances before posting the elimination journal.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting, consolidation, intercompany
ms.search.form: Report_16_Primary
ms.date: 11/13/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
ai-seo-date: 06/18/2025
ai-usage: ai-assisted
---

# G/L Consolidation Eliminations (report)

The **G/L Consolidation Eliminations** report previews the effect of elimination entries during financial consolidation. It shows consolidated amounts, amounts for a selected business unit or posted eliminations, and unposted elimination lines from a general journal batch. It doesn't create or post elimination entries.

Run the report after you consolidate business unit data and prepare elimination entries in a general journal. Enter the consolidation period, journal template, and journal batch. Choose **Net Change** or **Balance** in **Show**.

## Use cases

[!INCLUDE [report-16-scenario](../includes/report-16-scenario-include.md)]

> [!TIP]
> Here are some tips on how to use the report:
>
> * Run the report before you post the elimination journal to review its effect.
> * Review the output to ensure all expected eliminations are captured.
> * Use with your consolidation schedule to maintain accuracy.

Controllers and financial analysts can use the report to:

* Review proposed eliminations of internal transactions between entities during financial consolidation.
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