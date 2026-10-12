---
title: Czech local functionality - WIP extended posting
description: Learn about the WIP Extended Posting local functionality available in the Czech version of Business Central.
author: bholtorf
ms.service: dynamics-365-business-central
ms.topic: article
ms.search.keywords: Czech, Finance, Localization, CZ
ms.date: 10/08/2026
ms.reviewer: bholtorf
ms.author: bholtorf
ai-usage: ai-assisted
---

# WIP extended posting in the Czech version

The Czech version extends inventory posting with three extra general ledger (G/L) accounts that are used when manufacturing output and consumption are posted. The extended scheme separates the G/L accounts used for work in process (WIP) from the accounts used for finished inventory, so that you can track consumption and inventory changes on dedicated accounts instead of posting everything to the same inventory accounts.

## Set up WIP extended posting

The extra accounts are set up on the **Inventory Posting Setup** page, for each combination of **Location Code** and **Invt. Posting Group Code**:

- **Consumption Account**: The production consumption account that's used for inventory posting.
- **Change In Inv.Of WIP Acc.**: The balancing account used when a change is made to the WIP inventory account.
- **Change In Inv.Of Product Acc.**: The balancing account used when a change is made to the finished product inventory account.

To set up the accounts, follow these steps:

1. Choose the ![Tell me Feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Posting Setup**, and then choose the related link.
1. Select the line for the location and inventory posting group combination that you want to set up.
1. Fill in the **Consumption Account**, **Change In Inv.Of WIP Acc.**, and **Change In Inv.Of Product Acc.** fields.

## How WIP extended posting works

When you post manufacturing consumption or output, [!INCLUDE [d365fin](../../includes/d365fin_md.md)] uses the accounts that you set up on the **Inventory Posting Setup** page instead of the standard inventory accounts. If an account isn't filled in, posting stops with an error until you set up the missing account.

## Related information

- [Advanced localization pack for Czech](ui-extensions-advanced-localization-pack-cz.md)  
- [Czech local functionality](czech-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
