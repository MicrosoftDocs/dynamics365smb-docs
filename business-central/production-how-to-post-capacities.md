---
title: Post capacities
description: Learn how to record time used by work and machine centers for maintenance or other activities outside production orders.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form: 5832, 99000802, 99000820
ms.date: 07/15/2026
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Post capacities

Capacity journals record time used by work or machine centers outside a production order, such as maintenance or internal work. When you post this time, you create capacity ledger entries so that resource usage and availability reflect both production and nonproduction activities.

## To post capacities  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Capacity Journals**, and then choose the related link.  
1. Fill in the **Posting Date** and **Document No.** fields.  
1. In the **Type** field, enter the type of the capacity, either **Machine Center** or **Work Center**, that you are posting.  
1. In the **No.** field, enter the number of the machine center or work center.  
1. Enter the relevant data in the other fields, such as **Starting Time**, **Ending Time**, **Quantity**, and **Scrap**.  
1. Choose the **Post** action to post the capacities.  

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

## To view work center ledger entries  

On the **Work Center Card** and **Machine Center Card** pages, you can view the posted capacities as a result of finished production orders.    
1. [!INCLUDE[open-search](includes/open-search.md)], enter **Work Centers**, and then choose the related link.  
1. Open the relevant **Work Center** page from the list, and then choose the **Capacity Ledger Entries** action.  

    The **Capacity Ledger Entries** page displays the posted entries from the work center in the order they were posted.   

## Related information  

[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
