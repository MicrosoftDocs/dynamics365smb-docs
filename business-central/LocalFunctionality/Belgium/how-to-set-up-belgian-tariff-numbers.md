---
title: Set Up Belgian Tariff Numbers [BE]
description: Learn how to set up eight-digit Belgian tariff numbers for compliance with customs and tax regulations.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: tariff, tariff numbers, item code, Intrastat, customs, tax regulations, conversion factor, Belgian version
ms.search.form: 310
ms.date: 04/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up Belgian tariff numbers in the Belgian version

The Belgian customs and tax authorities have established an eight-digit item code for various tariff items.  

## Set up tariff numbers

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Tariff Numbers**, and then choose the related link.  
1. Choose the **New** action.  
1. On the **Tariff Numbers** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Conversion Factor**|Enter the conversion factor for the tariff number. The conversion factor is the factor by which you have to multiply the item unit to obtain the unit imposed by Intrastat. The conversion factor can be used when the item unit differs from the imposed Intrastat unit. The field is available when **Supplementary Units** is selected.|  
    |**Unit of Measure**|Enter the unit of measure for the tariff number. The field is available when **Supplementary Units** is selected.|  
    |**Weight Mandatory**|Select this field to show the weight of the items.|  

1. Choose the **OK** button.  
  
## Related information

- [Belgian Intrastat Reporting](belgian-intrastat-reporting.md)
- [Set Up Declaration Types](how-to-set-up-declaration-types.md)
- [Set Up Intrastat Establishment Numbers](how-to-set-up-intrastat-establishment-numbers.md)
- [Export Intrastat Third-Party Declarations](how-to-export-intrastat-third-party-declararations.md)
- [Print the Intrastat Form Report](how-to-print-the-intrastat-form-report.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
