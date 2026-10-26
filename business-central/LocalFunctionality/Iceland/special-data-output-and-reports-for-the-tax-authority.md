---
title: Special Data Output and Reports for the Icelandic Tax Authority
description: Learn how to prepare Icelandic tax reporting data in Business Central by mapping IRS numbers to posting accounts and reviewing account balances.
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: data file, data file format, data file output, tax authorities
ms.date: 10/23/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Special data output and reports for the Icelandic tax authority

It's a legal requirement to send the tax authority a data file in a predefined format.  

To prepare the reporting data, map the relevant posting accounts in the chart of accounts to the Internal Revenue Service (IRS) numbers defined by the tax authority. Learn more in [Map IRS numbers to the chart of accounts](how-to-map-irs-numbers-to-chart-of-accounts.md).

The predefined government account codes are divided into groups and types. Add the relevant IRS numbers, and manually map the general ledger accounts to these codes.

## Review account mappings and balances

Use the following reports to review the data before you prepare your submission:

|Report|Purpose|
|---|---|
|**IRS Details**|Lists posting accounts by IRS number and shows **Balance at Date**. Use **IRS Number** and **Date Filter** to limit the results.|
|**Trial Balance - IRS Number**|Shows general ledger accounts with their assigned IRS numbers, net changes, and balances at the specified date.|

Submit the required data file to the tax authority using its prescribed format and process.

## Related information

- [Map IRS numbers to the chart of accounts](how-to-map-irs-numbers-to-chart-of-accounts.md)
- [Report VAT to Tax Authorities](../../finance-how-report-vat.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
