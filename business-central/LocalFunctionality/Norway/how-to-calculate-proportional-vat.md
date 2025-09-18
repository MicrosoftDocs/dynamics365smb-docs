---
title: Calculate proportional VAT [NO]
description: Learn how to calculate VAT using proportional VAT for both deductible and non-deductible items in the Norwegian version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: proportional VAT, proportional VAT calculation, Norwegian version
ms.search.form: 472
ms.date: 05/12/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Calculate proportional VAT in the Norwegian version

You can use proportional VAT to calculate VAT when there's both deductible and non-deductible  VAT. Because it's difficult to know where and how an item is used, you have to contact the Norwegian tax authorities to determine whether a specified percentage of the VAT is deductible, based on historical data.  

### Steps to calculate proportional VAT

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Posting Setup**, and then choose the related link.  
1. On the **VAT Posting Setup** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Calc. Prop. Deduction VAT**|Select to indicate that you want to use the proportional VAT percentage. **Important:**  This field is available on the **VAT Posting Setup** page, but it isn't shown by default. [!INCLUDE[bp_customize](../../includes/bp_customize_md.md)]|  
    |**Proportional Deduction VAT %**|Enter the percentage of VAT to deduct.|  

1. Choose the **OK** button.  

## Related information

- [Proportional VAT](proportional-vat.md)
- [Norway Local Functionality](norway-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
