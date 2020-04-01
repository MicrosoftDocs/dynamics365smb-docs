---
    title: Design Details - Inventory Periods | Microsoft Docs
    description: Backdated transactions or cost adjustments often affect balances and stock valuations for accounting periods that may be considered closed. This can have adverse effects on accurate reporting, especially within global corporations. The Inventory Periods feature can be used to avoid such problems by opening or closing inventory periods to limit posting in a set period of time.
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
# Design Details: Inventory Periods
Backdated transactions or cost adjustments often affect balances and stock valuations for accounting periods that may be considered closed. This can have adverse effects on accurate reporting, especially within global corporations. The Inventory Periods feature can be used to avoid such problems by opening or closing inventory periods to limit posting in a set period of time.  

 An inventory period is a period of time, defined by an ending date, in which you post inventory transactions. When you close an inventory period, no value changes can be posted in the closed period. This includes new value postings, expected or invoiced postings, changes to existing values, and cost adjustments. However, you can still apply to an open item ledger entry that falls in the closed period. For more information, see [Design Details: Item Application](design-details-item-application.md).  

 To make sure that all transaction entries in a closed period are final, the following conditions must be met before an inventory period can close:  

-   All outbound item ledger entries in the period must be closed (no negative inventory).  
-   All item costs in the period must be adjusted.  
-   All released and finished production orders in the period must be cost adjusted.  

 When you close an inventory period, an inventory period entry is created by using the number of the last item register that falls in the inventory period. In addition, the time, date, and user code of the user closing the period are recorded in the inventory period entry. By using this information with the last item register for the previous period, you can see which inventory transactions were posted in the inventory period. It is also possible to reopen inventory periods if you need to post in a closed period. When you reopen an inventory period, an inventory period entry is created.  

## See Also  
 [Design Details: Inventory Costing](design-details-inventory-costing.md)
 [Managing Inventory Costs](finance-manage-inventory-costs.md)
 [Finance](finance.md)  
 [Working with Business Central](ui-work-product.md)
