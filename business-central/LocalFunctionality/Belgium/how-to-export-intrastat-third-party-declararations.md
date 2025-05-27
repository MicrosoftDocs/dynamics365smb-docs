---
title: Export intrastat third-party declarations [BE]
description: In Belgium, an external person or company must fill out the Intrastat declaration.
author: sorenfriisalexandersen    
ms.topic: how-to
ms.devlang: al
ms.search.keywords: third-party declaration, intrastat declaration, Belgian version
ms.date: 04/02/2025
ms.author: soalex
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Export intrastat third-party declarations in the Belgian version

[!INCLUDE[intrastat-2022w2](../../includes/intrastat-2022w2.md)]

In Belgium, you must have a third-party declarant fill out the Intrastat declaration. The third-party declarant must be an external person or company.  

## Export the third-party declaration

Before you export the file, it's a good idea to preview the report. Learn more in [Print the Intrastat Form Report](how-to-print-the-intrastat-form-report.md).  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Journals**, and then choose the related link.  
1. Choose the **Create File** action.  
1. Fill in the fields as described in the following table.  

   |Field|Description|  
   |---------------------------------|---------------------------------------|  
   |**Nihil declaration**|Select if you don't have any trade transactions with European Union (EU) countries/regions and want to send an empty declaration.|  
   |**Counter party info**|Check this field to include counter party information in the Intrastat file (new requirement from 2019). The counter party information added to the file is taken from the **Country/Region of Origin Code** and **Partner ID** fields from the Intrastat Journal.|  
   |**Enterprise No./VAT Reg. No.**|Enter the enterprise or VAT registration number.|  

1. Choose the **OK** button.  

Next, submit the declaration to the OneGate portal.  

## Related information

- [Belgian Intrastat Reporting](belgian-intrastat-reporting.md)  
- [Set Up Declaration Types](how-to-set-up-declaration-types.md)  
- [Set Up Belgian Tariff Numbers](how-to-set-up-belgian-tariff-numbers.md)  
- [Set Up Intrastat Establishment Numbers](how-to-set-up-intrastat-establishment-numbers.md)  
- [Print the Intrastat Form Report](how-to-print-the-intrastat-form-report.md)  
- [Set Up Intrastat Reporting](../../finance-how-setup-report-intrastat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
