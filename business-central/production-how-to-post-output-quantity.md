---
title: Batch post production output and run times
description: The output quantity represents the work progress in the form of the finished quantity and used capacity of work or machine center.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 99000773, 99000778, 99000823, 99000827
ms.date: 03/10/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Batch post output and run times

The output quantity represents the work progress in the form of the finished quantity and used capacity of the work or machine center.

You can use an output journal to:

* Adjust inventory with the output of finished items from production.
* Register quantities and scrap for each operation in a production routing.
* Register setup and run time for work and machine centers.

> [!NOTE]
> If you use a production routing, inventory is updated only when you post output quantity for the last operation.

The **Production Journal** page lets you do the same tasks as the **Output Journal** page, and also do consumption posting tasks. To learn more, go to [Register Consumption and Output for a Released Production Order Line](production-how-to-register-consumption-and-output.md).

## To post output quantities and/or register run times for one or more production order lines

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Output Journal**, and then choose the related link.  
2. Fill in the fields with the production order data and the output data and/or run time. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
  
   You can use the **Explode Routing** action to generate journal lines from production orders.

   > [!NOTE]
   > When you report production output for items with serial number tracking, you often need one journal line per serial number. When you turn on **Item Tracking on Lines** in the **Output Journal** and choose **Explode Routing**, [!INCLUDE [prod_short](includes/prod_short.md)] respects the item tracking setting when it explodes routing lines in output journals:
   >
   > * For serial-tracked items, [!INCLUDE [prod_short](includes/prod_short.md)] splits the last routing operation into multiple lines with quantity 1 per serial number, and the journal line is ready for you to enter the assigned serial number.
   > * For lot-tracked items, the operation is on a single line with the full quantity.
  
3. If the operation is complete, select the **Finished** field.  
4. Choose the **Post** action to post the operations.

    Capacity ledger entries are updated for the used work or machine centers with information about time and quantity of output and scrap. If you posted the last operation, the item is added to inventory.

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

[!INCLUDE [production-journals-edit-excel](includes/production-journals-edit-excel.md)]

## Related information

[Post Scrap Manually](production-how-to-post-scrap.md)  
[Reverse Output Posting](production-how-to-reverse-output-posting.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
