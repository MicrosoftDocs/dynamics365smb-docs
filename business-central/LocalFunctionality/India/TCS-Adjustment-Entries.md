---
title: TCS Adjustment Entries
description: This article provides information about TCS adjustment entries and process in Business Central for India.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, TCS adjustment entries, adjustment process
ms.date: 06/27/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# TCS adjustment entries

TCS adjustment is applicable for any correction of the TCS amount, TCS rate, and TCS base amount already calculated but not paid to the government authorities. Provision is available to enter the new TCS rates, new TCS amount, and new TCS base amount for the TCS entry, which was created against invoice or payment and not paid to the government authorities. System should recalculate TCS amount and adjustments would be made accordingly. The revised TCS amount should be updated in the relevant GL Accounts for TCS Payable and Customer Account. Existing TCS entry should be updated with revised TCS percentages, TCS amount, and TCS base amount.

## TCS adjustment process

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **TCS Adjustment Journal**, and then choose the related link.
1. Select the relevant transaction number in **Transaction No.** field from the drop-down, and the selected line gets populated with the posted record. The following information can be changed, in the adjustment journal as per the requirements:
  
   |Field Name|Use|
   |----------------------------------|---------------------------------------|  
   |**TCS % Applied**|Fill the revised TCS %.|  
   |**Surcharge % Applied**|Fill the revised Surcharge %.|
   |**eCESS % Applied**| Fill the revised eCess %.|
   |**SHE Cess % Applied**|Fill the revised SHE Cess %.|
   |**TCS Base Applied**|Fill the revised TCS base amount.|

1. On posting of the adjustment journal G/L Entry, TCS Entry, Customer Ledger Entry, and Detailed Customer Ledger Entry are updated with the adjusted amount and revised information.

## Related information

[TCS Payment to Authority](TCS-Payment-to-Authority.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
