---
title: Batch post consumption
description: If the flushing method is Manual, post the components manually using a consumption journal.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 99000846, 99000850
ms.date: 09/01/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---
# Batch post production consumption

If the flushing method is **Manual**, use a consumption journal to post the components manually.  

> [!NOTE]
> If you select the **Inventory Pick/Movement** option in the **Prod. Consumption Whse. Handling** field on the location card to indicate that the location requires inventory pick processing, you don't need to use this batch job. [!INCLUDE[prod_short](includes/prod_short.md)] handles consumption when you post the inventory pick. To learn more, go to [Pick for Production in Basic Warehouse Configurations](warehouse-how-to-pick-for-production.md).  

You can also set up [!INCLUDE[prod_short](includes/prod_short.md)] to automatically post (*flush*) components when you start or finish production orders. To learn more, go to [Enable Flushing of Components According to Operation Output](production-how-to-flush-components-according-to-operation-output.md).

## To post consumption for one or more production order lines

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Consumption Journal**, and then choose the related link.  
2. Fill in the fields with the production order data and the consumption data. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

    > [!TIP]
    > Use the **Calc. Consumption** action to generate journal lines from production orders based on the actual output (the quantity of finished goods that you reported) or on the expected output (the quantity of finished goods that you expect to produce).
    >
    > When you do, the **Calculation Based on** field might be filled in already. On the **Manufacturing Setup** page, you can specify the value to use by default in the **Default Consumption Calculation Based on** field. Specifying a default value lets you align consumption calculations with your preferred process, and saves you a step.

    > [!NOTE]
    > If you configured the location to require warehouse pick processing, only quantities that are already picked through a warehouse activity can be entered in the **Quantity** field in the **Consumption Journal** page. It can't be a calculated quantity. To learn more, go to [Pick for Production or Assembly in Advanced Warehouse Configurations](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md).

3. Choose the **Post** action to post the consumption. The related inventories are reduced.

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

[!INCLUDE [production-journals-edit-excel](includes/production-journals-edit-excel.md)]

## Related information

[Cancel production orders that have consumption](production-cancel-production-orders-that-have-consumption.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
