---
    title: How to Post Capacities | Microsoft Docs
    description: In the capacity journal, you post consumed capacities that are not assigned to the production order. For example, maintenance work must be assigned to capacity, but not to a production order.
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
# How to: Post Capacities
In the capacity journal, you post consumed capacities that are not assigned to the production order. For example, maintenance work must be assigned to capacity, but not to a production order.  

### To post capacities  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Capacity Journals**, and then choose the related link.  

2.  Fill in the **Posting Date** and **Document No.** fields.  

3.  In the **Type** field, enter the type of the capacity, either **Machine Center** or **Work Center**, that you are posting.  

4.  In the **No.** field, enter the number of the machine center or work center.  

5.  Enter the relevant data in the other fields, such as **Starting Time**, **Ending Time**, **Quantity**, and **Scrap**.  

6.  ADD INCLUDE<!--[!INCLUDE[bp_ribbonxml](../../includes/bp_ribbonxml_md.md)]-->On the **Action** tab, in the **Posting** group, choose **Post** to post the capacities.  

7.  Choose the **Yes** button to confirm the question.

## To view work center ledger entries  
In the **Work Center Card** and **Machine Center Card** windows, you can view the posted capacities as a result of finished production orders.    
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Work Centers**, and then choose the related link.  
2.  Open the relevant **Work Center** card from the list, and then choose the **Capacity Ledger Entries** action.  

The **Capacity Ledger Entries** window displays the posted entries from the work center in the order they were posted.   

## See Also  
 [How to: Post Output Quantity](../how-to-post-output-quantity.md)   
 [How to: Post Scrap Manually](../how-to-post-scrap-manually.md)   
 [How to: Register Consumption and Output](../how-to-register-consumption-and-output.md)   
 [Structure of the Capacity](../structure-of-the-capacity.md)
