---
title: Proportional VAT [NO]
description: Norwegian features enable calculation of VAT when both deductible and non-deductible VATs apply.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: VAT calculation, deductible VAT, non-deductible VAT, Norwegian version
ms.search.form: 10602, 10697, 10698, 10604
ms.date: 05/15/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Proportional VAT in Norway

[!INCLUDE[prod_short](../../includes/prod_short.md)] allows you to calculate VAT when there's both deductible and non-deductible VAT. Because it's difficult to know where and how an item is used, you must contact the Norwegian tax authorities to determine whether a specified percentage of the VAT is deductible based on historical data.  

## Example

A bus company owns both buses and trucks. When gasoline is purchased, the gasoline is stored in one holding tank. When the gasoline is used in a bus for transporting children, it isn't deductible. When the gasoline is used in a truck, the gasoline may be deductible. The agreement between the bus company and the Norwegian tax authorities might be that 60 percent of the VAT is deductible.  

If you have a purchase invoice of $12,500 based on 25 percent VAT with the **Calc. Prop. Deduction VAT** field on the **VAT Posting Setup** page set to **Yes** and the **Proportional Deduction VAT %** field set to **60 percent**, only 60 percent of the VAT is deductible in a journal. When the invoice is posted, the postings are as follows:  

- To vendor general ledger account - $12,500 (credit)  
- To cost account 4010 - $11,000 (debit)  
- To VAT account 2720 - $1,500 (debit)  

Generally, based on 25 percent VAT, the VAT amount would be $2,500. However, only 60 percent is deductible; therefore the VAT amount is $2,500 x 60% = $1,500. The non-deductible amount of $1,000 is added to the cost account. The VAT base has corresponding values. This amount should have been $10,000, but because only 60 percent is deductible, the base is $6,000.  

This also works if the transaction with this VAT combination is posted through a purchase order.  

> [!NOTE]  
> If this functionality is used on a purchase order that is used for buying items for inventory, the functionality doesn't influence the cost of the item. The cost of the item is added by using the non-deductible VAT. This works on the general ledger level only.  

## Related information

- [Calculate Proportional VAT](how-to-calculate-proportional-vat.md)
- [Norwegian VAT Reporting](norwegian-vat-reporting.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
