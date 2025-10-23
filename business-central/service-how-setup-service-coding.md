---
title: Set up codes for standard services
description: Learn how to set up codes for regularly performed service activities with a predefined set of service lines.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: service, service item, service order, repairs, maintenance
ms.date: 10/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up standard service codes

When you perform typical service, you often have to create service documents that use service lines that contain similar information. To make it easy to create these lines, you can set up standard service codes that have a predefined set of service lines. When you choose the code on a service document, the lines are entered automatically. You can set up any number of standard service codes, and each code can have an unlimited number of service lines of different types, including item, resource, cost, or standard text linked to it. You create service lines of each standard service code on the **Standard Service Code** card. You then assign standard service codes to service item groups on the **Standard Serv. Item Gr. Codes** page. Later, when you create a service document, you can use the **Get Standard Service Codes** action to add service lines.  
  
> [!Tip]
> You can use the same concept to create lines on sales and purchase documents. Learn more in [Create Recurring Sales and Purchase Lines](sales-how-work-standard-lines.md).  
  
## Set up a standard service code

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Standard Service Codes**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Fill in the service lines linked to this service code.  

## Assign a standard service code to a service item group

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service item Groups**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Fill in the service lines linked to this service code.  

## Related information

[Service Management](service-service.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
