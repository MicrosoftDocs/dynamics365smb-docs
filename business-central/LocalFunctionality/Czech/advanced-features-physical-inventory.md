---
title: Czech local functionality - Advances features of physical inventory 
description: Companies must differentiate the posting of inventory movements for the same goods, which requires line-break of physical inventory journal lines.
author: v-makune
ms.service: dynamics-365-business-central
ms.topic: article
ms.search.keywords: Czech, Inventory, Localization, CZ, Czech version
ms.date: 10/08/2026
ms.reviewer: bholtorf
ms.author: bholtorf
ai-usage: ai-assisted
---

# Advanced features of the physical inventory in the Czech version

To comply with legislation, companies need to account for deficits and surpluses separately. On the **Inventory Setup** page, you can set a default inventory movement template for positive and negative physical inventory adjustments. Each template can specify its own **Gen. Bus. Posting Group**, so you can change the posting group depending on the type of inventory movement.

Companies also need to distinguish between postings for the same item, for legal reasons. For example, they might need a different account for a deficit within a defined limit than for a deficit that exceeds it. To support this, each line on a physical inventory counting document can be assigned its own inventory movement template, which determines the **Gen. Bus. Posting Group** used for that line.

## Related information

- [Core localization pack for Czech](ui-extensions-core-localization-pack-cz.md)  
- [Czech local functionality](czech-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
