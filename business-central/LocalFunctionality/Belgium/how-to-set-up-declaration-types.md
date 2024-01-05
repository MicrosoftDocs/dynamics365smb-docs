---
title: Set up declaration types [BE]
description: In Business Central, there are two types of declaration in the Belgian version, the simplified declaration and the extended declaration.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 11/28/2023
ms.author: bholtorf
---
# Set up declaration types in the Belgian version

[!INCLUDE[intrastat-2022w2](../../includes/intrastat-2022w2.md)]

In [!INCLUDE[prod_short](../../includes/prod_short.md)], there are two types of declaration:  

- Simplified declaration  
- Extended declaration  

The type of declaration depends on the amount of shipped or received goods. To determine the type of declaration that you should use, visit the [National Bank of Belgium](https://aka.ms/BelgianNationalBank) website.  

When using the extended declaration, also, you need to set up an Incoterm in Intrastat Declaration for each shipping method. If you don't see the **Incoterm in Intrastat Decl.** field on the **Shipment Method** page, you might need to customize the page and add the field.

## To set up declaration types  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  
2. Select the **Simplified Intrastat Decl.** check box to set up a simplified declaration type. Clear this field to use extended declaration.  
3. Choose the **OK** button.  

## See also

[Belgian Intrastat Reporting](belgian-intrastat-reporting.md)  
[Set Up Belgian Tariff Numbers](how-to-set-up-belgian-tariff-numbers.md)  
[Set Up Intrastat Establishment Numbers](how-to-set-up-intrastat-establishment-numbers.md)  
[Export Intrastat Third-Party Declarations](how-to-export-intrastat-third-party-declararations.md)  
[Print the Intrastat Form Report](how-to-print-the-intrastat-form-report.md)  
[Set Up Intrastat Reporting](../../finance-how-setup-report-intrastat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
