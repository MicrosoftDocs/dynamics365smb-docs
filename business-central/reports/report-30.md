---
title: Dimension Check Value Posting (Report)
description: Find conflicts between default dimension value posting rules during setup or when investigating dimension-related document posting errors.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting, value posting, general ledger, validation
ms.search.form: Report_30_Primary
ms.date: 11/13/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
ai-seo-date: 06/21/2025
ai-usage: ai-assisted
---

# Dimension Check Value Posting (report)

The **Dimension Check Value Posting** report checks default dimension rules for conflicts. It compares **Value Posting** requirements, such as **Code Mandatory**, **Same Code**, and **No Code**, across default dimensions. It doesn't check inventory value entries or reconcile costs with the general ledger.

Use the report during setup or when troubleshooting dimension-related posting errors. It reports conflicting rules for individual records and related customers, vendors, salespeople, purchasers, and responsibility centers. You can filter by **Dimension Code**.

## Use cases

[!INCLUDE [report-30-scenario](../includes/report-30-scenario-include.md)]

> [!TIP]
> Here are some tips on how to use the report:
>
> * Run this report when reviewing document posting behavior or investigating posting issues.
> * Use it to support audits or quality checks during implementation phases.

Finance and implementation teams can use this report to:

* Find conflicting default dimension requirements before posting documents.
* Troubleshoot dimension value posting errors.
* Review default dimension setup during implementation or testing.

## Try the report

Try the report here: [Dimension Check Value Posting](https://businesscentral.dynamics.com?report=30)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Work with dimensions](../finance-dimensions.md)
[Built-in key finance reports](../finance-reports.md)  
[Ad hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]