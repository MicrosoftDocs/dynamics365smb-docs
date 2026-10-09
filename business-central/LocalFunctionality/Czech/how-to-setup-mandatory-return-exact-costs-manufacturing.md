---
title: Mandatory returning of exact costs in manufacturing [CZ]
description: Describes the local functionality for enforcing the return of exact manufacturing costs in the Czech version of Business Central.
author: bholtorf
ms.service: dynamics-365-business-central
ms.topic: article
ms.search.keywords: Czech, Finance, Localization, CZ
ms.date: 10/08/2026
ms.reviewer: bholtorf
ms.author: bholtorf
ai-usage: ai-assisted
---

# Mandatory returning of exact costs in manufacturing in the Czech version

This feature prevents a storno (reversing) consumption transaction from posting unless it's applied to the exact entry it reverses. It helps make sure manufacturing cost reversals always use the correct cost.

## Set up mandatory exact cost reversal for consumption

1. Open the **Manufacturing Setup** page.
1. Turn on the **Exact Cost Rev.Manda. (Cons.)** toggle.

When this setting is on, you can't post a negative consumption journal line for an item with item tracking unless the **Applies-from Entry** field specifies the entry it reverses.

> [!NOTE]
> A similar setting, **Exact Cost Reversing Mandatory**, is available on the **Inventory Setup** page and applies the same requirement to negative adjustment entries.

## Related information

- [Advanced Localization Pack for Czech](ui-extensions-advanced-localization-pack-cz.md)  
- [Czech Local Functionality](czech-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
