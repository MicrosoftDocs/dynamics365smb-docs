---
    title: How to: Post Scrap Manually | Microsoft Docs
    description: If scrap is produced during processing, it can be entered in the output journal. Note that the scrap quantity does not increase the output quantity.
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
# How to: Post Scrap Manually
If scrap is produced during processing, it can be entered in the output journal. Note that the scrap quantity does not increase the output quantity.  
  
### To post scrap manually  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Output Journal**, and then choose the related link.  
  
2.  In the **Posting Date** field, enter the posting date.  
  
3.  In the **Production Order No.**, enter the production order number.  
  
4.  In the **Item No.** field, select the item number.  
  
5.  In the **Operation No.** field, select the operation that you want to post the scrap to.  
  
6.  In the **Run Time** field, enter the time that was needed to process the scrap.  
  
7.  In the **Scrapped Quantity** field, enter the scrap quantity.  
  
8.  In the **Scrap Code** field, enter the scrap code.  
  
9. If the warehouse location where the items should be put away uses bins but does not require put-away processing, assign a bin code to the journal line to specify where the items should be placed in the warehouse. For more information, see [How to: Assign Bin Codes on Journal Lines](../how-to-assign-bin-codes-on-journal-lines.md).  
  
10. Click **Actions**, **Posting**, **Post** to post the operations.  
  
## See Also  
 [How to: Register Consumption and Output](../how-to-register-consumption-and-output.md)   
 [How to: Post Output Quantity](../how-to-post-output-quantity.md)   
 [How to: Post Run Times](../how-to-post-run-times.md)   
 [About Production Orders](../about-production-orders.md)