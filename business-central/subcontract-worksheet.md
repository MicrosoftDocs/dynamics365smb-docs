---
title: Use the subcontracting worksheet
description: Learn how to use the subcontracting worksheet to find production orders ready for subcontracting and create purchase orders.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: 99000886,
ms.date: 05/16/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---
# Use the subcontracting worksheet

The subcontracting worksheet lets you find production orders with material ready to send to a subcontractor and automatically create purchase orders for subcontract operations from production order routings. The worksheet functions like the planning worksheet — it calculates the needed supply (purchase orders), which you review and then create with the **Carry Out Action Message** action.

> [!TIP]
> You can also create subcontracting purchase orders directly from released production order routings without using the worksheet. Learn more in [Order subcontracting from production orders](subcontract-order.md).

> [!NOTE]
> Only production orders with a status of **Released** can be accessed and used from a subcontracting worksheet.

## Calculate the subcontracting worksheet

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Subcontracting Worksheet**, and then choose the related link.
2. To calculate the worksheet, choose the **Calculate Subcontracts** action.
3. On the **Calculate Subcontracts** page, set filters for the subcontracted operations, or the work centers where they're performed, to calculate only the relevant production orders.
4. Choose the **OK** button.

    Review the lines on the **Subcontracting Worksheet** page. The information in this worksheet comes from the production order and production order routing lines and flows to the purchase order when that document is created. You can delete a row from the worksheet without affecting the original information, just as you can with the other worksheets. The information reappears the next time you run the **Calculate Subcontracts** function.

## Create the subcontract purchase order

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Subcontracting Worksheet**, and then choose the related link.
2. Choose the **Carry Out Action Message** action.
3. Select the **Print Orders** field to print the purchase order as it's created.
4. Choose the **OK** button.

If all subcontracted operations are sent to the same vendor location, then only one purchase order is created.

The worksheet line that was turned into a purchase order is deleted from the worksheet. After a purchase order is created, it doesn't appear in the worksheet again.

## Post subcontracting purchase orders

After subcontracting purchase orders are created, you can post them. To learn about posting and its effects on production order entries, see [Post subcontracting purchase orders](subcontract-order.md#post-subcontracting-purchase-orders).

## Related information

[Subcontracting overview](production-how-to-subcontract-manufacturing.md)  
[Order subcontracting from production orders](subcontract-order.md)  
[Set up subcontracting](subcontract-setup.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
