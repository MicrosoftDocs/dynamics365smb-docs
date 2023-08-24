---
title: Batch Post Consumption
description: If the flushing method is Manual, you must post the components manually, using a consumption journal.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 99000846, 99000850
ms.date: 03/08/2023
ms.author: bholtorf

---
# Batch Post Production Consumption

If the flushing method is **Manual**, use a consumption journal to post the components manually.  

> [!NOTE]
> If you have placed a check mark in the **Require Pick** field on the location card to indicate that the location requires inventory pick processing, then you do not need to use this batch job. [!INCLUDE[prod_short](includes/prod_short.md)] will handle consumption when you post the inventory pick. For more information, see [Pick for Production in Basic Warehouse Configurations](warehouse-how-to-pick-for-production.md).  

You can also set up [!INCLUDE[prod_short](includes/prod_short.md)] to automatically post (*flush*) components when you start or finish production orders. For more information, see [Enable Flushing of Components According to Operation Output](production-how-to-flush-components-according-to-operation-output.md).

## To post consumption for one or more production order lines

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Consumption Journal**, and then choose the related link.  
2. Fill in the fields with the production order data and the consumption data. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

    Use the **Calc. Consumption** action to generate journal lines from production orders based on the actual output (the quantity of finished goods that you have reported) or on the expected output (the quantity of finished goods that you expect to produce).

    > [!NOTE]
    > If you configured the location card to require warehouse pick processing, then only quantities that are already picked through a warehouse activity can be entered in the **Quantity** field in the **Consumption Journal** page, not any calculated quantity. For more information, see [Pick for Production or Assembly in Advanced Warehouse Configurations](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md)

3. Choose the **Post** action to post the consumption. The related inventories are reduced.

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

## See Also

[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
