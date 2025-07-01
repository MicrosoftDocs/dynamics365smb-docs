---
title: Deleting posted invoices and credit memos [IS]
description: In Iceland, in accordance with legislation, you can't delete posted sales and purchase invoices and credit memos.
author: brentholtorf
ms.topic: conceptual
ms.search.keywords: Iceland, post, invoice, credit memo
ms.date: 02/05/2025
ms.author: bholtorf
ms.reviewer: v-soumramani
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Delete posted invoices and credit memos in the Icelandic version

## Before v24.0

In Iceland, in accordance with legislation, you can't delete sales and purchase invoices and credit memos after they're posted. In [!INCLUDE[prod_short](../../includes/prod_short.md)], the **Delete** command isn't available for these types of posted documents. 

## After v24.0

If you activate the new [Icelandic localization based on W1 Base App](iceland-global-core-app.md), you can delete sales, purchase invoices, and credit memos, but only in cases where they're older than seven years at the beginning of the new fiscal year.

> [!NOTE]
> The deletion is technically controlled with the new ENUM field **Document Retention Period** in the **General Ledger Setup** page. This field is hidden and has the **IS Docs Retention Period** option by default enabling this control.

## See also  

[Invoice Sales](../../sales-how-invoice-sales.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
