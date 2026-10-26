---
title: Registration Numbers in the Icelandic Localization
description: Learn where to enter Icelandic registration numbers in Business Central and how sales documents and payment exports use company and recipient details.
author: altotovi
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: registration numbers, Icelandic localization
ms.date: 10/23/2026
ms.author: altotovi
ms.reviewer: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Registration numbers in the Icelandic localization

> [!NOTE]
> These registration number features apply to the [Icelandic localization based on the W1 base app](iceland-global-core-app.md), introduced in version 24.0.

Enter your company's **Registration No.** on **Company Information**. Enter each customer's and vendor's **Registration No.** on the corresponding card.

## Registration number in documents

The customer's **Registration No.** is stored on sales invoice, sales order, and sales credit memo headers. You don't enter the number separately on each sales document.

## Registration numbers in payment exports

When you export payments, `Sender Reg. No.` in the `Payment Export Data` table is populated from **Registration No.** on **Company Information**.

The IS Core app also populates `Recipient Reg. No.` from the vendor's registration number for vendor payment exports, or from the customer's registration number for exports based on customer ledger entries. Whether a number appears in the exported file depends on the export format.

> [!NOTE]
> For extensions, the IS Core app populates recipient registration numbers through the `OnBeforeInsertPmtExportDataJnlFromGenJnlLine`, `OnPreparePaymentExportDataCLEOnBeforeTempPaymentExportDataInsert`, and `OnBeforeInsertPmtExportDataJnlFromVendorLedgerEntry` events.

## Related information

- [The list of Iceland local functionalities](iceland-local-functionality.md)  
- [Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)  
- [Country/regional availability and supported languages](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations)  

## [!INCLUDE[prod_short](../../includes/free_trial_md.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
