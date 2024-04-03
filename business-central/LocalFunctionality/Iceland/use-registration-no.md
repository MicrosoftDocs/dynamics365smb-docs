---
title: Registration number in the Icelandic localization
description: This article provides instructions how to use registration numbers in the Icelandic localization.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords:
ms.date: 04/02/2024
ms.author: altotovi
ms.reviewer: solsen
ms.service: dynamics-365-business-central
---

# Registration number in the Icelandic localization 

> [!NOTE]
> These changes only apply from version 24.0 if the user activates the new [Icelandic localization](iceland-global-core-app.md).  

## Registration No. in documents

The **Registration No.** field has been added to the headers in the following documents **Sales Invoice**, **Sales Order**, and **Sales Credit Memo**.  

## Sender Registration No. for payments  

The **Sender Reg. No.** field has been added to the **Payment Export Data** when user exports payments.  

> [!NOTE]
> This field can be used withing the following list of events: _OnBeforeInsertPmtExportDataJnlFromGenJnlLine_, _OnPreparePaymentExportDataCLEOnBeforeTempPaymentExportDataInsert_, and _OnBeforeInsertPmtExportDataJnlFromVendorLedgerEntry_.  

## See also

[The list of Iceland local functionalities](iceland-local-functionality.md)   
[Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)
[Country/regional availability and supported languages](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations)

## [!INCLUDE[prod_short](../../includes/free_trial_md.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
