---
title: Correct VAT Reports [DE]
description: Learn how to submit a corrected sales VAT advance notification or a corrected VAT-VIES declaration in the German version.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: corrected VAT advance notification, corrected notification, corrective VIES declaration, German version
ms.date: 10/09/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Correct VAT reports in the German version

> [!NOTE]
> This article previously described a **VAT Report** page with **Cancellation**/**Correction** line types and **Suggest Lines**/**Correct Lines** actions that are independent of the report type. That page doesn't exist for the German version. Instead, corrections are made separately for each of the two VAT reporting mechanisms that Germany uses, as described in this article.

## Correct a sales VAT advance notification

If you need to resubmit a sales VAT advance notification, create a new **Sales VAT Adv. Notif. Card** for the same period and select the **Corrected Notification** field. Learn more in [Set up and export sales VAT advance notifications](how-to-set-up-and-export-sales-vat-advance-notifications.md).

## Correct a VAT-VIES declaration

If you need to resubmit a VAT-VIES declaration (EU Sales List), run the **VAT-Vies Declaration Tax – DE** report again for the same period and select the **Corrected Notification** field on the **Options** FastTab. Learn more in [Declare VAT-VIES tax](how-to-declare-vat-vies-tax.md).

If you want to switch between monthly and quarterly reporting, use the **Change to monthly reporting** or **Revoke monthly reporting** fields instead of the **Corrected Notification** field.

## Related information

- [VAT Reporting](vat-reporting.md)
- [Set up and export sales VAT advance notifications](how-to-set-up-and-export-sales-vat-advance-notifications.md)
- [Declare VAT-VIES tax](how-to-declare-vat-vies-tax.md)
- [Set up VAT reports](how-to-set-up-vat-reports.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
