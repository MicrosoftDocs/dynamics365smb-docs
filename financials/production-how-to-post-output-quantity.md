---
    title: How to Batch Post Production Output and Run Times| Microsoft Docs
    description: The output quantity represents the work progress in the form of the finished quantity.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 09/06/2017
    ms.author: sgroespe

---
# How to: Batch Post Production Output and Run Times
The output quantity represents the work progress in the form of the finished quantity.  

When you post output quantity on the last operation, the inventory is updated automatically.  

## To post output quantities for one or more production order lines

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Output Journal**, and then choose the related link.  

2.  In the **Posting Date** field, enter a posting date.  

3.  In the **Production Order No.** field, enter the production order number.  

4.  In the **Item No.** field, select the item number.  

5.  In the **Operation No.** field, enter the operation number.  

6.  In the **Output Quantity** field, enter the product quantity.  

7.  If the operation has been completed, select the **Finished** field.  

8.  If the warehouse location where the items should be put away uses bins but does not require put-away processing,  assign a bin code to the journal line to specify where the items should be placed in the warehouse. For more information, see [How to: Assign Bin Codes on Journal Lines](../how-to-assign-bin-codes-on-journal-lines.md).  

9. On the **Actions** tab, in the **Posting** group, choose **Post** to post the operations. The output quantity will be posted. The item is now available for shipping.  

## To post run times for one or more production order lines
The run time represents work progress in the form of the necessary working time.    

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Output Journal**, and then choose the related link.  

2.  In the **Posting Date** field, enter a posting date.  

3.  In the **Production Order No.** field, enter a production order number.  

4.  In the **Item No.** field, enter an item number.  

5.  In the **Operation No.** field, enter an operation number.  

6.  In the **Run Time** field, enter the time necessary for processing the operation.  

7.  In the **Output Quantity** field, enter the quantity produced in the period.  

8.  If the operation is completed, select the **Finished** field.  

9. If the warehouse location where the items should be put away uses bins but does not require put-away processing, assign a bin code to the journal line to specify where the items should be placed in the warehouse. For more information, see [How to: Assign Bin Codes on Journal Lines](../how-to-assign-bin-codes-on-journal-lines.md).  

10. On the **Actions** tab, in the **Posting** group, choose **Post** to post the operations. Choose the **Yes** button.  

## See Also  
 [How to: Register Consumption and Output](../how-to-register-consumption-and-output.md)   
 [How to: Enter Master Data for Output Posting](../how-to-enter-master-data-for-output-posting.md)   
 [How to: Post Run Times](../how-to-post-run-times.md)   
 [How to: Post Consumption Manually](../how-to-post-consumption-manually.md)   
 [About Production Orders](../about-production-orders.md)
