---
title: Post scrap manually
description: Learn how to record scrap quantities and reason codes by production operation without increasing finished output.
author: brentholtorf
ms.topic: how-to
ms.search.form: 99000823,
ms.date: 07/15/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---

# Post scrap manually

When you post scrap, you record the quantities that an operation processed but that don't qualify as finished output. To keep good output separate from production losses and to show scrap by operation, enter scrap quantities and reason codes in the output journal.

> [!NOTE]
> The scrap quantity doesn't increase the output quantity.  

## To post scrap manually

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Output Journal**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. In the **Scrapped Quantity** field, enter the scrap quantity.  
4. In the **Scrap Code** field, enter the scrap code.  
5. Choose the **Post** action to post the specified scrap per operation.  

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

## Related information

[Reverse and correct production order transactions](production-cancel-production-orders-that-have-consumption.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
