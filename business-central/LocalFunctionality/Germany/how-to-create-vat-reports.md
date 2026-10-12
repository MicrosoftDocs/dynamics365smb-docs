---
title: How to Create VAT Reports [DE]
description: Learn how to create and submit sales VAT advance notifications and VAT-VIES declarations in the German version.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: VAT reports, sales VAT advance notification, VAT-VIES declaration, German version
ms.date: 10/09/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Create VAT reports in the German version

> [!NOTE]
> This article previously described a single **VAT Report** page with a **No.**, **VAT Report Type**, **Trade Type**, **Sign-off**, and **Suggest Lines**/**Release**/**Export**/**Mark as Submitted** actions. That page doesn't exist for the German version. Instead, Germany uses two separate mechanisms: the **Sales VAT Adv. Notif. Card** page for ELSTER sales VAT advance notifications, and the **VAT-VIES Declaration** reports for EU Sales List data. This article points you to both.

In the German version, you don't create VAT reports on a single generic page. Instead, you work with two separate reporting mechanisms, depending on what you need to submit:

- **Sales VAT advance notifications**: Create and export an XML file for the Elektronische Steuererklärungen (ELSTER) online portal. Learn more in [Set up and export sales VAT advance notifications](how-to-set-up-and-export-sales-vat-advance-notifications.md).
- **VAT-VIES declarations (EU Sales List)**: Create and submit declarations about sales transactions with other EU countries/regions to the Bundeszentralamt für Steuern (BZSt). Learn more in [Declare VAT-VIES tax](how-to-declare-vat-vies-tax.md).

Both mechanisms use the **Suggest Lines** and **G/L - VAT Reconciliation** actions to pull data from VAT entries and reconcile it against the general ledger, and both let you create a corrective version if you need to resubmit a period. Learn more in [Correct VAT reports](how-to-correct-vat-reports.md).

## Related information

- [VAT Reporting](vat-reporting.md)
- [Set up and export sales VAT advance notifications](how-to-set-up-and-export-sales-vat-advance-notifications.md)
- [Declare VAT-VIES tax](how-to-declare-vat-vies-tax.md)
- [Correct VAT reports](how-to-correct-vat-reports.md)
- [Set up VAT reports](how-to-set-up-vat-reports.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
