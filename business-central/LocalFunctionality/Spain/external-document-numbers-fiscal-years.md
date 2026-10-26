---
title: Use the Same External Document Numbers Across Fiscal Years
description: Learn how to allow repeated external document numbers across years in Business Central for Spain and how document dates limit duplicate checks.
author: jswymer
ms.topic: how-to
ms.reviewer: jswymer
ai-usage: ai-assisted
ms.search.keywords: external document numbers, external document, Spanish version
ms.date: 10/20/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
---

# Use the same external document numbers across fiscal years

In general, [!INCLUDE[prod_short](../../includes/prod_short.md)] doesn't allow for posting documents with the same value in **External Document No.**, not even across fiscal years, due to legislation. In Spain however, this is accepted, and now [!INCLUDE[prod_short](../../includes/prod_short.md)] includes an option to allow this behavior.  

## Allow the same external document number across fiscal years

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Purchases & Payables Setup**, and then choose the related link.  
1. In the **General** FastTab, select the **Same Ext. Doc. No. in Diff. FY** field.

The duplicate-number check uses the calendar year of **Document Date**, not the fiscal year defined in **Accounting Periods**. With this setting enabled, the check is limited to vendor ledger entries whose document dates fall in that same calendar year.

## Related information

[Spain Local Functionality](spain-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
