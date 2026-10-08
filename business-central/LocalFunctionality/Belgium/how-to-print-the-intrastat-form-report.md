---
title: Verify the Intrastat Report Before Export [BE]
description: Learn how to verify the Belgian Intrastat report with the Checklist Report action before you export and submit your monthly declaration.
author: brentholtorf   
ms.topic: how-to
ms.devlang: al
ms.search.keywords: intrastat form report, intrastat report, intrastat declaration, statistics authorities, tax authorities, monthly reporting, Belgian version
ms.date: 10/08/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
ai-usage: ai-assisted
---

# Verify the Intrastat report in the Belgian version

[!INCLUDE[intrastat-2022w2](../../includes/intrastat-2022w2.md)]

In Belgium, you must report the movement of goods to the statistics authorities every month, and the report must be sent to the tax authorities.  

> [!NOTE]
> The standalone **Intrastat - Form** and **Intrastat Checklist** reports described in earlier versions of this article are no longer available. Use the **Checklist Report** action on the **Intrastat Report** page instead to verify the contents of your declaration before you export it.

## Verify the Intrastat report before you export it

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Report List**, and then choose the related link.  
1. Open the Intrastat report that you want to verify.  
1. Choose the **Checklist Report** action.  
1. Review the errors and warnings shown in the **Error Messages** FactBox, and fix any lines that are missing required information.  

For the fields you fill in before you export the declaration, such as **Nihil Declaration** and **Enterprise No./VAT Reg. No.**, see [Export Intrastat Third-Party Declarations](how-to-export-intrastat-third-party-declararations.md).  

## Related information

- [Belgian Intrastat Reporting](belgian-intrastat-reporting.md)  
- [Set Up Declaration Types](how-to-set-up-declaration-types.md)  
- [Set Up Belgian Tariff Numbers](how-to-set-up-belgian-tariff-numbers.md)  
- [Set Up Intrastat Establishment Numbers](how-to-set-up-intrastat-establishment-numbers.md)  
- [Export Intrastat Third-Party Declarations](how-to-export-intrastat-third-party-declararations.md)  
- [Work with Intrastat Reporting](../../finance-how-report-intrastat.md)  
- [Set Up Intrastat Reporting](../../finance-how-setup-report-intrastat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
