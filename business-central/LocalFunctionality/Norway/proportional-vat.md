---
    title: Proportional VAT
    description: Norwegian enhancements allow you to calculate VAT when there is both deductible and non-deductible VAT.

    services: project-madeira 
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Proportional VAT
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] allows you to calculate VAT when there is both deductible and non-deductible VAT. Because it is difficult to know where and how an item is used, you will have to contact the Norwegian tax authorities to determine whether a specified percentage of the VAT is deductible based on historical data.  

## Example  
A bus company owns both buses and trucks. When gasoline is purchased, the gasoline is stored in one holding tank. When the gasoline is used in a bus for transporting children, it is not deductible. When the gasoline is used in a truck, the gasoline may be deductible. The agreement between the bus company and the Norwegian tax authorities might be that 60 percent of the VAT is deductible.  

If you have a purchase invoice of $12,500 based on 25 percent VAT with the **Calc. Prop. Deduction VAT** field on the **VAT Posting Setup** page set to **Yes** and the **Proportional Deduction VAT %** field set to **60 percent**, only 60 percent of the VAT is deductible in a journal. When the invoice is posted, the postings are as follows:  

- To vendor general ledger account - $12,500 (credit)  
- To cost account 4010 - $11,000 (debit)  
- To VAT account 2720 - $1,500 (debit)  

Generally, based on 25 percent VAT, the VAT amount would be $2,500. However, only 60 percent is deductible; therefore the VAT amount is $2,500 x 60% = $1,500. The non-deductible amount of $1,000 is added to the cost account. The VAT base has corresponding values. This amount should have been $10,000, but because only 60 percent is deductible, the base is $6,000.  

This also works if the transaction with this VAT combination is posted through a purchase order.  

> [!NOTE]  
>  If this functionality is used on a purchase order that is used for buying items for inventory, the functionality will not influence the cost of the item. The cost of the item will be added by using the non-deductible VAT. This works on the general ledger level only.  

## See Also  
 [Calculate Proportional VAT](how-to-calculate-proportional-vat.md)   
 [Norwegian VAT Reporting](norwegian-vat-reporting.md)
