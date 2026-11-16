---
title: Insurance - Uninsured FAs (report)
description: Find active fixed assets without insurance coverage ledger entries, and review their acquisition cost, depreciation, and book value for insurance follow-up.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_5626_Primary
ms.date: 11/13/2026
ms.service: dynamics-365-business-central
ms.custom:
  - ai-gen-docs-bap
ai-seo-date: 10/23/2024
ai-usage: ai-assisted
---

# Insurance - Uninsured FAs (report)

The **Insurance - Uninsured FAs** report shows active, undisposed fixed assets without an insurance coverage ledger entry that isn't marked **Disposed FA**. An asset with such an entry is considered insured even if its net insured amount is zero.

The report requires **Insurance Depr. Book** in **Fixed Asset Setup**. It shows acquisition cost, depreciation, and book value from that book. Assets without that depreciation book are excluded. The report identifies missing coverage entries, not whether policy limits are adequate.

## Use cases

[!INCLUDE[report-5626-scenario](../includes/report-5626-scenario-include.md)]

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
Insurance - Uninsured FAs

## Report description

### What the report does

### Use cases

Please include your data sources and URLs

-->

## Try the report

Try the report here: [Insurance - Uninsured FAs](https://businesscentral.dynamics.com?report=5626)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Fixed assets report overview](../fa-reports.md)  
[Ad hoc analysis of fixed assets data](../ad-hoc-analysis-fa.md)  
[Fixed assets analytics overview](../fa-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]