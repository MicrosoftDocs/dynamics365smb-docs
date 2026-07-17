---
title: Batch post production output and run times
description: Learn how to post completed quantities, scrap, setup time, and run time for one or more released production orders.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 99000773, 99000778, 99000823, 99000827
ms.date: 07/15/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Batch post output and run times

When you post output, you record the quantities completed during production and the setup and run time used by work or machine centers. When you post output, you update production progress, capacity ledger entries, production costs, and, for the last routing operation, finished-goods inventory. Use the output journal to register results for one or more released production orders.

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
  
   You can use the **Explode Routing** action to generate journal lines from production orders. This action creates one output journal line for each routing operation on the production order, so you can record output and run time per operation rather than posting everything on a single line. Use Explode Routing when:

   - You want to record setup time, run time, and scrap for each operation separately.
   - You need to post output for individual operations as they finish, rather than waiting until the last operation.
   - You want to track capacity consumption per work or machine center.

   Each generated line includes the operation number, work or machine center number, the expected times from the routing, and the output quantity. For operations that use a subcontracting work center, the output quantity is set to zero because subcontracted output is posted through the purchase order instead.

   > [!NOTE]
   > When you report production output for items with serial number tracking, you often need one journal line per serial number. When you turn on **Item Tracking on Lines** in the **Output Journal** and choose **Explode Routing**, [!INCLUDE [prod_short](includes/prod_short.md)] respects the item tracking setting when it explodes routing lines in output journals:
   >
   > * For serial-tracked items, [!INCLUDE [prod_short](includes/prod_short.md)] splits the last routing operation into multiple lines with quantity 1 per serial number, and the journal line is ready for you to enter the assigned serial number.
   > * For lot-tracked items, the operation is on a single line with the full quantity.
  
3. If the operation is complete, select the **Finished** field.  
4. Choose the **Post** action to post the operations.

    Capacity ledger entries are updated for the used work or machine centers with information about time and quantity of output and scrap. If you posted the last operation, the item is added to inventory.

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

## Stop codes and scrap codes

When you post output, you can record downtime and scrap with reason codes that help you analyze production efficiency.

- **Stop codes**: Track why a work center or machine center was idle during an operation (for example, maintenance, tool change, or machine failure). Enter the stop code and the stop time on the output journal line. The posted stop time appears on capacity ledger entries for the work or machine center.
- **Scrap codes**: Categorize why units were scrapped during an operation (for example, defective material, setup error, or tool wear). Enter the scrap code and the scrap quantity on the output journal line. The scrap quantity is posted to the item ledger as a negative adjustment, and the scrap code appears on the capacity ledger entry.

To set up stop codes and scrap codes, use the **Stop Codes** and **Scrap Codes** pages. To open them, [!INCLUDE[open-search](includes/open-search.md)], enter **Stop Codes** or **Scrap Codes**, and then choose the related link.

> [!TIP]
> Use stop code and scrap code analysis to identify recurring quality or downtime issues. Over time, this data helps you improve routing operations, reduce waste, and increase overall equipment effectiveness.

[!INCLUDE [production-journals-edit-excel](includes/production-journals-edit-excel.md)]

## Related information

[Post Scrap Manually](production-how-to-post-scrap.md)  
[Reverse and correct production order transactions](production-cancel-production-orders-that-have-consumption.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
