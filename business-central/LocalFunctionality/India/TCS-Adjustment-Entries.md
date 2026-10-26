---
title: TCS Adjustment Entries
description: Create TCS adjustment entries and review the transaction fields and processing steps for the India localization of Microsoft Dynamics 365 Business Central.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, TCS adjustment entries, adjustment process
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# TCS adjustment entries

TCS adjustment is applicable for any correction of the TCS amount, TCS rate, and TCS base amount already calculated but not paid to the government authorities. Provision is available to enter the new TCS rates, new TCS amount, and new TCS base amount for the TCS entry, which was created against invoice or payment and not paid to the government authorities. System should recalculate TCS amount and adjustments would be made accordingly. The revised TCS amount should be updated in the relevant GL Accounts for TCS Payable and Customer Account. Existing TCS entry should be updated with revised TCS percentages, TCS amount, and TCS base amount.

## TCS adjustment process

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **TCS Adjustment Journal**, and then choose the related link.
1. Select the relevant entry in **Transaction No**. The lookup includes unpaid TCS entries with a nonzero TCS amount. The journal is populated with the posted record. Change the following fields as needed:
  
   |Field Name|Use|
   |----------------------------------|---------------------------------------|  
   |**TCS % Applied**|Fill the revised TCS %.|  
   |**Surcharge % Applied**|Fill the revised Surcharge %.|
   |**eCESS % Applied**| Fill the revised eCess %.|
   |**SHE Cess % Applied**|Fill the revised SHE Cess %.|
   |**TCS Base Amount Applied**|Fill the revised TCS base amount.|

1. Choose **Post**. Posting updates the TCS entry and posts the adjustment to the general ledger and customer ledger entries. Entries that are already paid can't be adjusted.

## Related information

[TCS Payment to Authority](TCS-Payment-to-Authority.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
