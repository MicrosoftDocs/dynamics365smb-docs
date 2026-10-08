---
title: Export intrastat third-party declarations [BE]
description: In Belgium, an external person or company must fill out the Intrastat declaration.
author: sorenfriisalexandersen    
ms.topic: how-to
ms.devlang: al
ms.search.keywords: third-party declaration, intrastat declaration, Belgian version
ms.date: 10/08/2026
ms.author: soalex
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
ai-usage: ai-assisted
---

# Export intrastat third-party declarations in the Belgian version

[!INCLUDE[intrastat-2022w2](../../includes/intrastat-2022w2.md)]

In Belgium, you must have a third-party declarant fill out the Intrastat declaration. The third-party declarant must be an external person or company.  

> [!NOTE]
> The **Intrastat Journals** page and its **Create File** action described in earlier versions of this article are no longer available. Exporting the declaration is now done from the **Intrastat Report** page, part of the current Intrastat experience. If you haven't filled in and validated your Intrastat report yet, see [Work with Intrastat Reporting](../../finance-how-report-intrastat.md) first.

## Export the third-party declaration

Before you export the file, it's a good idea to run the **Checklist Report** action to verify the contents of the report. Learn more in [Verify the Intrastat Report](how-to-print-the-intrastat-form-report.md).  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Report List**, and then choose the related link.  
1. Open the Intrastat report that you want to export.  
1. On the **Export Parameters** group on the **General** FastTab, fill in the fields as described in the following table.  

   |Field|Description|  
   |---------------------------------|---------------------------------------|  
   |**Nihil Declaration**|Select if you don't have any trade transactions with European Union (EU) countries/regions and want to send an empty declaration.|  
   |**Enterprise No./VAT Reg. No.**|Enter the enterprise or VAT registration number.|  

1. Choose the **Create File** action.  

[!INCLUDE[prod_short](../../includes/prod_short.md)] automatically includes counterparty information, such as the country/region of origin and partner ID, in the exported file, so you don't need to select this separately.

Next, submit the declaration to the OneGate portal.  

## Related information

- [Belgian Intrastat Reporting](belgian-intrastat-reporting.md)  
- [Set Up Declaration Types](how-to-set-up-declaration-types.md)  
- [Set Up Belgian Tariff Numbers](how-to-set-up-belgian-tariff-numbers.md)  
- [Set Up Intrastat Establishment Numbers](how-to-set-up-intrastat-establishment-numbers.md)  
- [Verify the Intrastat Report](how-to-print-the-intrastat-form-report.md)  
- [Set Up Intrastat Reporting](../../finance-how-setup-report-intrastat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
