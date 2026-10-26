---
title: TDS Adjustments
description: Learn how to make corrections to TDS amounts, rates, or base amounts before payment to government authorities in Business Central.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, TDS adjustments, TDS adjustment process
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# TDS adjustments

TDS adjustment can be required, for any corrections in the TDS amount, TDS rate or TDS base amount already deducted but not paid to the government authorities. The revised TDS amount is updated in the relevant GL Accounts for TDS Payable and Vendor Account. Existing TDS entry is updated with revised TDS percentages, TDS amount, and TDS base amount.

## TDS adjustment process

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **TDS Adjustment Journal**, and then choose the related link.
1. Select the relevant entry in **Transaction No**. The lookup includes unpaid TDS entries with a nonzero TDS base amount. The journal is populated with the posted record. Change the following fields as needed:
  
    |Field Name|Use|
    |----------------------------------|---------------------------------------|  
    |**TDS % Applied**|Fill the revised TDS %.|  
    |**TDS Base Amount Applied**|Fill the revised TDS base amount.|

1. Choose **Post**. Posting updates the TDS entry and posts the adjustment to the general ledger and vendor ledger entries. Entries that are already paid can't be adjusted.

## Related information

[TDS Payment to Authority](TDS-TDS-Payment-to-Authority.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
