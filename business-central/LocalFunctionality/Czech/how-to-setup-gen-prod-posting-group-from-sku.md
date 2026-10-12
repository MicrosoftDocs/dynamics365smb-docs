---
title: Czech local functionality - Gen.Prod.Posting Group from SKU
description: Learn about the General Product Posting Group functionality from SKU in the Czech version of Business Central.
author: bholtorf
ms.service: dynamics-365-business-central
ms.topic: article
ms.search.keywords: Czech, Finance, Localization, CZ
ms.date: 10/08/2026
ms.reviewer: bholtorf
ms.author: bholtorf
ai-usage: ai-assisted
---

# General production posting group from SKU in the Czech version

By default, the **Gen. Prod. Posting Group** on a document line comes from the item card. This feature lets you use the **Gen. Prod. Posting Group** from the stockkeeping unit (SKU) instead, so items can post to different general ledger accounts depending on location or variant.

## Set up general production posting group from SKU

1. Open the **Inventory Setup** page.
1. Turn on the **Use Gen. Prod. Posting Group from Stockkeeping Unit** toggle.
1. Open a **Stockkeeping Unit Card**, and in the **Gen. Prod. Posting Group** field, enter the posting group to use for that SKU.

When this setup is on, documents use the **Gen. Prod. Posting Group** from the SKU card instead of from the item card whenever a stockkeeping unit exists for the combination of item, location, and variant.

## Related information

- [Advanced Localization Pack for Czech](ui-extensions-advanced-localization-pack-cz.md)  
- [Czech Local Functionality](czech-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
