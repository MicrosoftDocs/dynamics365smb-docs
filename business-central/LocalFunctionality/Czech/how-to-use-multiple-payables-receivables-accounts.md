---
title: Czech local functionality - Multiple payables/receivables accounts 
description: Learn how to post customer and vendor transactions to an alternate posting group in the Czech version of Business Central.
author: bholtorf
ms.service: dynamics-365-business-central
ms.topic: article
ms.search.keywords: Czech, Finance, Localization, CZ
ms.date: 10/08/2026
ms.reviewer: bholtorf
ms.author: bholtorf
ai-usage: ai-assisted
---

# Multiple payables/receivables accounts in the Czech version

Users often post transactions, like bad debt or other types of receivable/payable transactions, that need to be recorded in the customer and vendor ledgers, but posted to a different receivable/payable G/L account than the one specified on the customer's or vendor's posting group.

This capability is now provided by the standard [!INCLUDE[d365fin](../../includes/d365fin_md.md)] alternative posting groups feature, rather than by Czech-specific functionality. Turn on the **Allow Multiple Posting Groups** toggle on the **Sales & Receivable Setup** or **Purchase & Payables Setup** page, use the **Alternative Groups** action on the **Customer Posting Groups** or **Vendor Posting Groups** page to specify the allowed substitute groups, and then turn on **Allow Multiple Posting Groups** on the relevant customer or vendor card. After setup, you can choose an alternative posting group when you post sales or purchase documents and journals.

## Related information

- [Set up posting groups](../../finance-posting-groups.md#allow-alternative-posting-groups-on-documents)
- [Core Localization Pack for Czech](ui-extensions-core-localization-pack-cz.md)  
- [Czech Local Functionality](czech-local-functionality.md)  
- [Finance](../../finance.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
