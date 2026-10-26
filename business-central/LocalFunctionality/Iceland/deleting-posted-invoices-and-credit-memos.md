---
title: Delete Posted Invoices and Credit Memos in Iceland
description: Learn how Icelandic document retention and setup dates control deletion of posted sales and purchase invoices and credit memos in Business Central.
author: brentholtorf
ms.topic: concept-article
ms.search.keywords: Iceland, post, invoice, credit memo
ms.date: 10/23/2026
ms.author: bholtorf
ms.reviewer: jswymer
ms.custom: bap-template
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Delete posted invoices and credit memos in the Icelandic version

## Before version 24.0

In Iceland, in accordance with legislation, you can't delete sales and purchase invoices and credit memos after they're posted. In [!INCLUDE[prod_short](../../includes/prod_short.md)], the **Delete** command isn't available for these types of posted documents. 

## With the IS Core app

With the [Icelandic localization based on the W1 base app](iceland-global-core-app.md), you can delete posted sales and purchase invoices and credit memos only if they were already more than seven years old at the start of the current fiscal year. Their **Posting Date** must also be earlier than the **Allow Document Deletion Before** date on **Sales & Receivables Setup** or **Purchases & Payables Setup**, as applicable. That setup date must not be blank.

For example, if the current fiscal year starts on January 1, 2026, a posting date of December 31, 2018, passes the Icelandic retention check. January 1, 2019, doesn't. The company deletion cutoff and other standard deletion checks still apply.

> [!NOTE]
> The IS Core app sets **Document Retention Period** to **IS Docs Retention Period** in **General Ledger Setup**. This field isn't shown on the page, so you don't need to enable the rule manually.

## Related information  

[Invoice Sales](../../sales-how-invoice-sales.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
