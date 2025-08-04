---
title: Set up declaration types [BE]
description: Learn how to set up simplified and extended declaration types in the Belgian version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: declaration types, Belgian version, simplified declaration, extended declaration, Incoterm, Intrastat
ms.date: 03/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up declaration types in the Belgian version

[!INCLUDE[intrastat-2022w2](../../includes/intrastat-2022w2.md)]

In [!INCLUDE[prod_short](../../includes/prod_short.md)], there are two types of declaration:  

- Simplified declaration  
- Extended declaration  

The type of declaration depends on the amount of shipped or received goods. To determine the type of declaration that you should use, visit the [National Bank of Belgium](https://aka.ms/BelgianNationalBank) website.  

When using the extended declaration, also, you need to set up an Incoterm in Intrastat Declaration for each shipping method. If you don't see the **Incoterm in Intrastat Decl.** field on the **Shipment Method** page, you might need to customize the page and add the field.

## Set up declaration types  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  
1. Select the **Simplified Intrastat Decl.** checkbox to set up a simplified declaration type. Clear this field to use extended declaration.  
1. Choose the **OK** button.  

## Related information

- [Belgian Intrastat Reporting](belgian-intrastat-reporting.md)  
- [Set Up Belgian Tariff Numbers](how-to-set-up-belgian-tariff-numbers.md)  
- [Set Up Intrastat Establishment Numbers](how-to-set-up-intrastat-establishment-numbers.md)  
- [Export Intrastat Third-Party Declarations](how-to-export-intrastat-third-party-declararations.md)  
- [Print the Intrastat Form Report](how-to-print-the-intrastat-form-report.md)  
- [Set Up Intrastat Reporting](../../finance-how-setup-report-intrastat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
