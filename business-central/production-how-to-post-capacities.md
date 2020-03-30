---
    title: How to Post Capacities | Microsoft Docs
    description: In the capacity journal, you post consumed capacities that are not assigned to the production order. For example, maintenance work must be assigned to capacity, but not to a production order.
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
# Post Capacities
In the capacity journal, you post consumed capacities that are not assigned to the production order. For example, maintenance work must be assigned to capacity, but not to a production order.  

## To post capacities  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Capacity Journals**, and then choose the related link.  
2.  Fill in the **Posting Date** and **Document No.** fields.  
3.  In the **Type** field, enter the type of the capacity, either **Machine Center** or **Work Center**, that you are posting.  
4.  In the **No.** field, enter the number of the machine center or work center.  
5.  Enter the relevant data in the other fields, such as **Starting Time**, **Ending Time**, **Quantity**, and **Scrap**.  
6.  Choose the **Post** action to post the capacities.  

## To view work center ledger entries  
In the **Work Center Card** and **Machine Center Card** pages, you can view the posted capacities as a result of finished production orders.    
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Work Centers**, and then choose the related link.  
2.  Open the relevant **Work Center** card from the list, and then choose the **Capacity Ledger Entries** action.  

The **Capacity Ledger Entries** page displays the posted entries from the work center in the order they were posted.   

## See Also  
[Manufacturing](production-manage-manufacturing.md)    
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)      
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
