---
    title: How to Transfer VAT Amounts to the Settlement Account | Microsoft Docs
    description: Transferring VAT amounts to the settlement account means that the purchase VAT account is credited and the sales VAT account is debited with the amounts calculated for the VAT statement period. The net amount is credited or debited, if the purchase VAT amount is larger to the VAT settlement account. You can post the settlement immediately or print a test report first.
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
# How to: Transfer VAT Amounts to the Settlement Account
Transferring VAT amounts to the settlement account means that the purchase VAT account is credited and the sales VAT account is debited with the amounts calculated for the VAT statement period. The net amount is credited or debited, if the purchase VAT amount is larger to the VAT settlement account. You can post the settlement immediately or print a test report first.  
  
### To transfer VAT amounts to the settlement account  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Statements**, and then choose the related link.  
  
2.  In the **VAT Statement** window, on the **Actions** tab, in the **Functions** group, choose **Calc. and Post VAT Settlement**.  
  
3.  On the **VAT Posting Setup** FastTab, you can enter codes in the **VAT Bus. Posting Group** and **VAT Prod. Posting Group** fields to select the entries to be processed. If you do not enter any codes, entries with all business group codes and product group codes are included.  
  
4.  On the **Options** FastTab, specify the conditions for the batch job.   
  
5.  Choose the **Print** button to start the batch job.  
  
 If you print a test report to obtain approval before posting you must the select the **Post** field to run the batch job again.  
  
> [!IMPORTANT]  
>  If you calculate VAT on trade with the EU, you must also prepare a VIES declaration for the tax authorities.  
  
## See Also  
 [How to: Define VAT Statements](../how-to-define-vat-statements.md)   
 [How to: Print VAT Statements](../how-to-print-vat-statements.md)   
 [How to: Record VAT](../how-to-record-vat.md)