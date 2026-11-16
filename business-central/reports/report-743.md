---
title: VAT Reconciliation Report (Report)
description: Review G/L entries and their linked posted VAT bases and amounts to support tax reconciliation without recalculating VAT from source documents.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: VAT, tax, reconciliation, general ledger, reporting
ms.search.form: Report_743_Primary
ms.date: 11/13/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
ai-seo-date: 06/25/2025
ai-usage: ai-assisted
---

# VAT Reconciliation Report (report)

The **VAT Reconciliation Report** shows general ledger (G/L) entries and their linked posted VAT entries. It breaks down sales, purchase, and reverse-charge VAT bases and amounts to support reconciliation before tax submission. It doesn't recalculate VAT from source documents.

Filter by **G/L Account No.** and **Posting Date**. Choose **Show Details** for entry-level information, and use **VAT Amount Type** to include nondeductible VAT or show deductible amounts only. **Show Transactions without VAT** can include linked entries with zero VAT amounts, but G/L entries without a VAT entry link aren't included.

## Use cases

[!INCLUDE [report-743-scenario](../includes/report-743-scenario-include.md)]

> [!TIP]
> Here are some tips on how to use the report:
>
> * Use before tax filing to review posted VAT amounts linked to G/L entries.
> * Reconcile VAT ledger and transaction-level entries to verify accuracy.
> * Review differences between G/L amounts and linked VAT bases or amounts.
> * Use this report as part of your tax preparation checklist to ensure compliance and accuracy.

Accountants can use the report to:

* Validate VAT postings against the general ledger.
* Ensure compliance with tax reporting requirements.

Controllers can use the report to:

* Oversee VAT reconciliation processes.
* Support audit readiness and financial accuracy.

Auditors might reference the report to:

* Verify the accuracy and completeness of VAT entries.
* Confirm that VAT calculations are properly reflected in the G/L.

## Try the report

Try the report here: [VAT Reconciliation Report](https://businesscentral.dynamics.com?report=743)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[VAT management overview](../finance-manage-vat.md)  
[Built-in VAT reports in Business Central](../finance-vat-reports.md)  
[Built-in key finance reports](../finance-reports.md)  
[Ad hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]