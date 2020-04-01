---
    title: How to Create Production Order Headers | Microsoft Docs
    description: You can create a production order manually, and the first step is to create a production order header.
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
# Create Production Order Headers
You can create a production order manually, and the first step is to create a production order header.

Production orders are typically created automatically by a planning function to fulfill a known demand. For more information, see [Planning](production-planning.md).   

In the following procedure, a firm planned production order is created. You can also create production orders with a different status.  

## To create a production order header  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Firm Planned Prod. Orders**, and then choose the related link.  
2.  Choose the **New** action.  
3.  In the **No.** field, insert the next number in the series.  
4.  In the **Source Type** field, select the source of the production order.

    Here you can select to produce for a family of items. For more information, see [Work With Production Families](production-how-work-family.md).
5.  In the **Source No.** field, select the item number, family, or sales header for which the production order is to be generated.  
6.  Fill in the **Quantity** and **Due Date** fields according to your specifications.  

When production requirements change, such as components or operations, you can quickly replan the production order. For more information, see [Replan or Refresh Production Orders Directly](production-how-to-replan-refresh-production-orders.md). 

## See Also  
[Manufacturing](production-manage-manufacturing.md)    
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)      
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
