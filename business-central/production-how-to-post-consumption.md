---
    title: How to Batch Post Consumption | Microsoft Docs
    description: If the flushing method is **Manual**, you must post the components manually, using a consumption journal.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 03/30/2021
    ms.author: edupont

---
# Batch Post Production Consumption
If the flushing method is **Manual**, you must post the components manually, using a consumption journal.
>[Note!] If you have placed a check mark in the Require Pick field on the location card to indicate that the location requires inventory pick processing, then you do not need to use this batch job as the program handles consumption when you post inventory pick. For more information, see [Pick for Production or Assembly](warehouse-how-to-pick-for-production.md#to-pick-components-in-basic-warehouse-configurations). 

You can also set the system up to automatically post (*flush*) components when you start or finish production orders. For more information, see [Enable Flushing of Components According to Operation Output](production-how-to-flush-components-according-to-operation-output.md).

## To post consumption for one or more production order lines  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Consumption Journal**, and then choose the related link.  
2.  Fill in the fields with the production order data and the consumption data. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

    You can use the **Calc. Consumption** action to generate journal lines from production orders based on the actual output (the quantity of finished goods that you have reported) or on the expected output (the quantity of finished goods that you expect to produce).
> [!NOTE]
> If you configured location card to require warehouse pick processing, then only quantities that are already picked through a warehouse activity, can be entered in the Quantity field in the Consumption Journal window, not any calculated quantity. For more information, see [Pick for Production or Assembly in Advanced Warehouse Configurations](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing)

3.  Choose the **Post** action to post the consumption. The related inventories are reduced.



## See Also  
[Manufacturing](production-manage-manufacturing.md)    
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)      
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
