---
    title: Norwegian VAT Reporting
    description: Norwegian enhancements allow you to calculate and report VAT to the Norwegian tax authorities.

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
# Norwegian VAT Reporting
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] ../../includes Norwegian enhancements that allow you to calculate and report VAT to the Norwegian tax authorities.  

This topic shows the typical steps that you should follow when reporting Norwegian VAT.  

## Print the Trade Settlement  
First, you must print the trade settlement. Use the **Tradesettlement** report to print the trade settlement that is required by the authorities.  

This report prints detailed information about the posted VAT in the specified period. On the last page of the report, the actual trade settlement to report is printed.  

This report can be printed as many times as required. No posting or other changes are made to the data when you use this report.  

## Check the Trade Settlement  
Next, you must check the trade settlement. Verify that the amounts in the trade settlement are correct, and make any necessary adjustments.  

## Post VAT  
If the information in the trade settlement is correct, the final step is to post the VAT using the **Calc. and Post VAT Settlement** report. It is required that you manually specify the correct VAT period in the **Starting Date** and **Ending Date** fields. Generally, these dates correspond to the period previously specified in the **Tradesettlement** report.  

When using this report, you can decide not to post if you want to check the results before you actually post VAT.  

When posting VAT, the corresponding VAT period is created and marked as closed in the **Settled VAT Period** table. If you specify a period that does not correspond to one of the typical six Norwegian VAT periods, all periods that are affected by the specified date interval are closed.  

## See Also  
 [Norway Local Functionality](norway-local-functionality.md)
