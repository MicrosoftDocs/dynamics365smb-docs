---
title: Czech local functionality - Reverse charge in setup and posting
description: Learn how to set up and post reverse charge transactions in the Czech version of Business Central, including configuration of tax liability regimes and VAT reporting.
author: bholtorf
ms.service: dynamics-365-business-central
ms.topic: install-set-up-deploy
ms.search.keywords: CZ, Czech, Advance payment, Advance invoices, Payables, Finance,  Cash, EET, Cash Desk
ms.date: 10/08/2026
ms.reviewer: bholtorf
ms.author: bholtorf
ai-usage: ai-assisted
---

# Reverse charge - Setup and posting in the Czech version

Use this feature to set up the regime for transferred tax liability (reverse charge) and how it's reported. Settings on **Tariff Numbers** and **Commodities** let you monitor invoice posting in the correct mode (normal or reverse charge) and report it correctly in the VAT Control Report.

To turn on limit monitoring for a commodity, set the **Reverse Charge Check** field to **Limit Check** on the **VAT Posting Setup** page. When the amount exceeds the limit that's set up for the commodity on the **Commodity Setup** page, Business Central shows a message that the invoice must be posted in the appropriate mode. The codes that are reported in the VAT Control Report are set up on the **Tariff Numbers** page.

## Related information

- [Core Localization Pack for Czech](ui-extensions-core-localization-pack-cz.md)  
- [Czech Local Functionality](czech-local-functionality.md)  
- [Finance](../../finance.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
