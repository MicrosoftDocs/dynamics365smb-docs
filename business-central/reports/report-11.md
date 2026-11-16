---
title: G/L - VAT Reconciliation (Report)
description: Compare VAT statement account totals with VAT entries by G/L account, using posting dates for G/L entries and VAT reporting dates for VAT.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: VAT reconciliation, tax reconciliation, G/L, audit, filing
ms.search.form: Report_11_Primary
ms.date: 11/13/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
ai-seo-date: 06/25/2025
ai-usage: ai-assisted
---

# G/L - VAT Reconciliation (report)

The **G/L - VAT Reconciliation** report uses VAT statement lines to show amounts and VAT by G/L account. It includes **Account Totaling** and **VAT Entry Totaling** lines to help you compare general ledger amounts with VAT entries. It doesn't list individual transactions.

Use this report during VAT filing periods to validate that posted VAT entries match the VAT amounts in your general ledger. This report is important for accurate tax filings and audit readiness.

Select the VAT statement name and enter **Starting Date** and **Ending Date**. G/L account totals use posting dates, while VAT entry totals use VAT reporting dates. Choose whether to include open, closed, or both states of VAT entries, and whether to include entries before the period. Reversed VAT entries are excluded.

VAT entries must have a G/L account number for reconciliation. If the report can't determine the account for an entry, exclude the affected entry or ask your partner to help fix the data.

## Use cases

[!INCLUDE [report-11-scenario](../includes/report-11-scenario-include.md)]

> [!TIP]
> Here are some tips on how to use the report:
>
> * Catch discrepancies early by using the report during VAT filing periods.
> * Check for differences between posting dates and VAT reporting dates when you compare amounts.
> * Ensure all VAT entries are properly posted and reconciled with the G/L.
> * Confirm VAT accuracy by using the report as part of your audit preparation checklist.

Accountants can use the report to:

* Verify VAT postings.
* Ensure compliance with tax regulations.

Controllers can use the report to:

* Oversee VAT reconciliation processes.
* Support internal control and audit readiness.

Auditors might reference the report to:

* Confirm the completeness and accuracy of VAT filings.
* Identify account totals that need further investigation in the ledger entries.

## Try the report

Try the report here: [G/L - VAT Reconciliation](https://businesscentral.dynamics.com?report=11)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[VAT management overview](../finance-manage-vat.md)  
[Built-in VAT reports in Business Central](../finance-vat-reports.md)  
[Built-in key finance reports](../finance-reports.md)  
[Ad hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]