---
    title: How to Reverse Output Posting | Microsoft Docs
    description: There are times when output posting must be reversed. An example of this would be if a data entry error occurred and an incorrect amount of output is posted to a production order.
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
# How to: Reverse Output Posting
There are times when output posting must be reversed. An example of this would be if a data entry error occurred and an incorrect amount of output is posted to a production order.  
  
### To reverse an output posting  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Output Journal**, and then choose the related link. Select your batch.  
  
2.  In the **Posting Date** field, type the posting date of the entry to reverse.  
  
3.  In the **Prod. Order No.** field, select the production order of the entry to reverse.  
  
4.  In the **Item No.** field, select the item number of the entry to reverse.  
  
5.  In the **Operation No.** field, type the operation number of the entry to reverse.  
  
6.  In the **Run Time** field, type a negative quantity.  
  
7.  In the **Output Quantity** field, type a negative quantity, if a value was entered into this field during posting.  
  
8.  In the **Applies-To Entry** field, select the associated item ledger entry. This reverses the capacity and item ledger entries.  
  
9. Post the reversal.  
  
 The output journal entries are posted to the item ledger as a positive adjustment.  
  
## See Also  
 Output Journal   
 Production Journal   
 [About Production Orders](../about-production-orders.md)   
 [How to: Post Output Quantity](../how-to-post-output-quantity.md)   
 [How to: Post Run Times](../how-to-post-run-times.md)   
 [How to: Release Production Orders Automatically](../how-to-release-production-orders-automatically.md)   
 [How to: Release Production Orders by Status Change](../how-to-release-production-orders-by-status-change.md)