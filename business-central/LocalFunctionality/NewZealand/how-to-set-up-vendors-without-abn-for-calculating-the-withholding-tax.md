---
title: Set up vendors without IRD for calculating withholding tax (NZ)
description: Learn how to set up vendors without IRD numbers to calculate withholding tax, ensuring compliance with New Zealand tax regulations for local vendors.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: IRD number, calculate withholding tax, vendor setup, New Zealand tax compliance
ms.search.form: 28043
ms.date: 05/06/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up vendors without IRD numbers for calculating the withholding tax

Withholding Tax (WHT) is calculated for local vendors who don't have a New Zealand Inland Revenue Department number (IRD), as required by tax law.  

## Setup process

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.  
1. Choose the required vendor, and then choose the **Edit** action.  
1. On the **Vendor Card** page, on the **Registration** FastTab, make sure the **IRD No.** field and the **Foreign Vend** field must be empty.  
1. Choose the **OK** button.  

> [!NOTE]  
> The WHT percentage is automatically withheld in accordance with what was specified on the **WHT Posting Setup** page. The WHT certificate is produced for submission to the vendor. Learn more in [Withholding Tax](withholding-tax.md).  

## Related information

- [Withholding Tax](withholding-tax.md)
- [Set Up Withholding Tax](how-to-set-up-withholding-tax.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
