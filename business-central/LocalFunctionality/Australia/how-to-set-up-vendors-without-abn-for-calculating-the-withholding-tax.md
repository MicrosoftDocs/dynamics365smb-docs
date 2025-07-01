---
title: Set Up Vendors Without ABN for Calculating WHT
description: In Business Central, Withholding Tax (WHT) is calculated for local vendors without an Australian Business Number (ABN), as required by tax law.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: withholding tax, WHT, Australian business number, ABN, local vendor, Australian version
ms.date: 03/27/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up vendors without ABN for calculating Withholding Tax in the Australian version

Withholding Tax (WHT) is calculated for local vendors who don't have an Australian Business Number (ABN), as required by tax law.  

## Set up process

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.  
1. Choose the required vendor, and then choose the **Edit** action.  
1. On the **Vendor Card** page, make sure the **ABN** field and the **Foreign Vend** field are empty.  
1. Choose the **OK** button.  

   > [!NOTE]  
   > The WHT percentage is automatically withheld in accordance with what was specified on the **WHT Posting Setup** page. The WHT certificate is produced for submission to the vendor. Learn more in [Withholding Tax](withholding-tax.md).  

## Related information

- [Withholding Tax](withholding-tax.md)
- [Set Up Withholding Tax](how-to-set-up-withholding-tax.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
