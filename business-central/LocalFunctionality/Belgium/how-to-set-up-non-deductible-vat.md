---
    title: How to set up Non-Deductible VAT [BE]
    description: You can calculate the VAT amounts for specific types of expenses that can be partially declared as VAT.
    author: brentholtorf
    ms.topic: conceptual
    ms.devlang: al
    ms.search.keywords:
    ms.date: 07/08/2024
    ms.author: bholtorf
    ms.service: dynamics-365-business-central
    ms.reviewer: bholtorf
---
# Set up Non-Deductible VAT in the Belgian version
You can calculate VAT amounts for specific types of expenses that can be partially declared as VAT. For example, on the **G/L Account Card** page, if you enter 75 in the **% Non-Deductible VAT** field, then 75 percent of the regular VAT amount is considered an additional cost and will be added to the net amount during posting. The remaining 25 percent will be posted as regular VAT.  

> [!NOTE]  
>  If no value is entered in the **% Non-Deductible VAT** field, the VAT amount is 100 percent deductible.  

## To set up the non-deductible VAT percentage  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.  
2.  Select a general ledger expense account that requires the partial deduction, and then choose the **Edit** action.  
3.  Enter the amount in **% Non deductible VAT** field.  
4.  Choose the **OK** button.  

## See also  
 [Belgian VAT](belgian-vat.md)   
 [Print Periodic VAT Reports](how-to-print-periodic-vat-reports.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]