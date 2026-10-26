---
title: Require Descriptions in General Ledger Entries
description: Require a meaningful description on journal lines by omitting the default G/L account description in the Dutch version of Business Central.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: journal lines, general journal description, Dutch version, Netherlands
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Require descriptions in general ledger entries

When you select an account on a general journal line, the account name is entered in **Description** by default. The description is stored in the G/L entry when you post the journal. You can omit the default account name to prompt users to enter a more useful description for the audit trail.

On the **G/L Account Card** page, select **Omit Default Descr. in Jnl.** to stop the G/L account name from being entered automatically when you select that account on a journal line.

Posting requires a nonblank **Description** on each journal line. If a description is blank, posting is blocked. The check requires text but doesn't assess how detailed the description is.

> [!NOTE]  
> This setting applies to general journal lines and the Dutch cash and bank/giro journal lines. It doesn't make descriptions mandatory on every type of document.

## Related information

- [Apply Customer Payments Manually](../../receivables-how-apply-sales-transactions-manually.md)  
- [Create an Audit File for the Tax Authority](how-to-create-an-audit-file-for-the-tax-authority.md)  
- [Understanding the General Ledger and the COA](../../finance-general-ledger.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
