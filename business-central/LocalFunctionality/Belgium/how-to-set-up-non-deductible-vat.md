---
    title: How to Set Up Non-Deductible VAT
    description: You can calculate VAT amounts for specific types of expenses which can be partially declared as VAT.

    services: project-madeira 
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Set Up Non-Deductible VAT
You can calculate VAT amounts for specific types of expenses which can be partially declared as VAT. For example, in the **G/L Account Card** window, if you enter 75 percent in the **% Non-Deductible VAT** field, then 75 percent of the regular VAT amount is considered an additional cost and will be added to the net amount during posting. The remaining 25 percent will be posted as regular VAT.  

> [!NOTE]  
>  If no value is entered in the **% Non-Deductible VAT** field, the VAT amount is 100 percent deductible.  

## To set up the non-deductible VAT percentage  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Chart of Accounts**, and then choose the related link.  
2.  Select a general ledger expense account that requires the partial deduction, and then choose the **Edit** action.  
3.  On the **Posting** FastTab, enter the amount in **% Non deductible VAT** field.  
4.  Choose the **OK** button.  

## See Also  
 [Belgian VAT](belgian-vat.md)   
 [Print Periodic VAT Reports](how-to-print-periodic-vat-reports.md)
