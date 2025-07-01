---
title: Registration numbers in the Icelandic localization
description: This article provides instructions about how to use registration numbers in the Icelandic localization.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: registration numbers, Icelandic localization
ms.date: 02/06/2025
ms.author: altotovi
ms.reviewer: v-soumramani
ms.service: dynamics-365-business-central
---

# Registration numbers in the Icelandic localization

> [!NOTE]
> These changes only apply from version 24.0 if the user activates the new [Icelandic localization](iceland-global-core-app.md).

## Registration number in documents

The **Registration No.** field is added to the header of the following documents: sales invoice, sales order, and sales credit memo.

## Sender registration number for payments

The **Sender Reg. No.** field is added to the **Payment Export Data** table when the user exports payments.

> [!NOTE]
> This field can be used in the following list of events: _OnBeforeInsertPmtExportDataJnlFromGenJnlLine_, _OnPreparePaymentExportDataCLEOnBeforeTempPaymentExportDataInsert_, and _OnBeforeInsertPmtExportDataJnlFromVendorLedgerEntry_.

## See also

- [The list of Iceland local functionalities](iceland-local-functionality.md)  
- [Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)  
- [Country/regional availability and supported languages](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations)  

## [!INCLUDE[prod_short](../../includes/free_trial_md.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
