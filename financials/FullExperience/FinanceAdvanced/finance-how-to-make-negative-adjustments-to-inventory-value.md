---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# How to: Make Negative Adjustments to Inventory Value
Sometimes, you must make a negative adjustment to the value, but not the quantity, of one or more items.  
  
### To make negative adjustments to inventory value  
  
1.  In the **Search** box, enter **Item Journal**, and then choose the related link.  
  
2.  Fill in the first journal line by decreasing the quantity on inventory with a negative adjustment. Use a unit cost that corresponds to the actual posted cost.  
  
3.  Make a positive adjustment of the same quantity, setting the unit cost at the new, correct value.  
  
> [!NOTE]  
>  You can find the actual cost on a ledger entry list for an item. If you set the filter **Open** \= **Yes**, only the entries that are used to calculate the inventory value are shown. You can also see the cost in the **Inventory Valuation** report.  
  
## See Also  
 Revaluation Journal   
 [How to: Close Open Item Ledger Entries Resulting from Fixed Application in the Item Journal](../how-to-close-open-item-ledger-entries-resulting-from-fixed-application-in-the-item-journal.md)   
 [How to: Enter New Values When Revaluing Items](../how-to-enter-new-values-when-revaluing-items.md)