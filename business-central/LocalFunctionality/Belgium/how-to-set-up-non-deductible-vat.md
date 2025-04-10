---
title: How to set up Non-Deductible VAT [BE]
description: Learn how to calculate VAT amounts for specific expense types that can be partially declared as VAT.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: VAT amount calculation, Belgian version, expense types, partial declaration
ms.date: 04/04/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up non-deductible VAT in the Belgian version

You can calculate VAT amounts for specific types of expenses that can be partially declared as VAT. For example, on the **G/L Account Card** page, if you enter 75 in the **% Non-Deductible VAT** field, then 75 percent of the regular VAT amount is considered an additional cost and is added to the net amount during posting. The remaining 25 percent is posted as regular VAT.  

> [!NOTE]  
> If no value is entered in the **% Non-Deductible VAT** field, the VAT amount is 100 percent deductible.  

## Set up the non-deductible VAT percentage  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.  
1. Select a general ledger expense account that requires the partial deduction, and then choose the **Edit** action.  
1. Enter the amount in **% Non deductible VAT** field.  
1. Choose the **OK** button.  

## Related information

- [Belgian VAT](belgian-vat.md)
- [Print Periodic VAT Reports](how-to-print-periodic-vat-reports.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
