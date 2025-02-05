---
title: Create a production order
description: You can create a production order manually, and the first step is to create a production order header.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.form: 9325, 99000815, 99000829, 9900083
ms.date: 02/05/2025
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Create a production order header

You can create a production order manually, and the first step is to create a production order header.

Production orders are typically created automatically by a planning function to fulfill a known demand. For more information, see [Planning](production-planning.md).  

In the following procedure, a firm planned production order is created. You can also create production orders with a different status.  

## To create a production order header

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Firm Planned Prod. Orders**, and then choose the related link.  
2. Choose the **New** action.  
3. In the **No.** field, insert the next number in the series.  
4. In the **Source Type** field, select the source of the production order.

    Here you can select to produce for a family of items. For more information, see [Work With Production Families](production-how-work-family.md).
5. In the **Source No.** field, select the item number, family, or sales header for which the production order is to be generated.  
6. Fill in the **Quantity** and **Due Date** fields according to your specifications.  

When production requirements change, such as components or operations, you can quickly replan the production order. For more information, see [Replan or Refresh Production Orders Directly](production-how-to-replan-refresh-production-orders.md).  

## Print barcodes for the finished goods

To remove a step or two from the process of tracking finished goods, [!INCLUDE [prod_short](includes/prod_short.md)] offers a **Print Label** action on the **Released Production Order** and **Finished Production Order** pages. The action prints a report that includes the **Item No.**, **Description**, **Unit of Measure**, and 1D and 2D barcode information from the orders. On the request page, you can also specify whether to print the **Lot No.**, **Serial No.** or **Package No.** values as barcodes.

> [!NOTE]
> Some printers and barcode/QR code formats require a specific implementation. You might need to upload a different Word template.
>
> Check with your equipment supplier to learn how to print Word documents on your device.

 If you decide to clone the report to create your own custom version, you can easily connect if you select **Prod. Output Item Label** on the **Report Selection Production Order** page.

## Related information

[Manufacturing](production-manage-manufacturing.md)
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]