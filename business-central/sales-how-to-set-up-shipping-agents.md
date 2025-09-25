---
title: How to Set Up Shipping Agents
description: Learn how to set up a code for each of your shipping agents and enter descriptive information about each of them and the services they provide.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.date: 06/23/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Set Up Shipping Agents
You can set up a code for each of your shipping agents and enter information about them.  

If you enter an Internet address for the shipping agent, and the agent provides package tracking services on the Internet, you can use the automatic package tracking feature. For more information, see [Track Packages](sales-how-track-packages.md).

When you set up shipping agents on your sales orders, you can also specify the services that each shipping agent offers.  
For each shipping agent, you can set up an unlimited number of services, and you can specify a shipping time for each service.  

When you have assigned a shipping agent service to a sales order line, the shipping time of the service will be included in the order promising calculation, for that line. For more information, see [Calculate Order Promising Dates](sales-how-to-calculate-order-promising-dates.md).

## To set up a shipping agent  
1.  [!INCLUDE[open-search](includes/open-search.md)], enter **Shipping Agents**, and then choose the related link.  
2.  Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].  
3.  Choose the **Shipping Agent Services** action.
4. In the **Shipping Agent Services**, fill in the fields as necessary.

> [!NOTE]  
>  If you delete the shipping agent on the order line, the shipping agent service code is also deleted. The contents of fields that were based in part on the shipping agent service are recalculated.  

## Related information
[Set Up Shipment Methods](sales-how-set-up-shipment-methods.md)  
[Track Packages](sales-how-track-packages.md)    
[Warehouse Management Overview](design-details-warehouse-management.md)
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
