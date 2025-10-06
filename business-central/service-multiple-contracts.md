---
title: Multiple Contracts | Microsoft Docs
description: You may need to manage a service item under multiple service contracts based on your agreements with customers.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: service management, service item, service contract, service order, service level agreement, SLA, multiple contracts
ms.date: 10/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Multiple contracts

Depending on your service level agreements with a customer, you may have to handle a service item under more than one service contract.  
  
By handling a service item under multiple contracts, you can do the following:  
  
* Issue different contracts for the same service item.  
* Service parts separately.  
* Consider different skills that are required to service different aspects of a service item, such as mechanical components and software.  
* Specify different response times and frequencies in servicing different parts of a service item.  
* Address different kinds of activities to be performed on a service item when the service item requires different types of service in different time periods.  
* Select and assign an appropriate contract number to a service item line when you are creating a service order.  
* Handle relevant financial information about service items and service level agreements.  
  
You can consider the following examples of using the multiple contracts functionality.  
  
## Create multiple contracts per service item

You can manually create a service contract or contract quote for service items already registered in non-canceled contracts owned by the same customer. To do this, follow the standard procedure of creating service contracts and service contract quotes. Learn more in [Work with Service Contracts and Service Contract Quotes](service-how-to-create-service-contracts-and-service-contract-quotes.md).  
  
When you add a service item on a contract line that is registered in other service contracts or contract quotes, a warning message is displayed stating that the service item already belongs to one or more service contracts or contract quotes. If you confirm this message, all relevant service item information is copied to a newly created contract line.  
  
## Copy documents

You can automatically create a service contract or contract quote for service items that are already registered in other service contracts or contract quotes by using the **Copy from Document** action.  
  
## Create service orders for multiple contracts

You can manually create a service order for a service item that is registered in multiple active contracts. A service contract is active when it is signed and not expired.  
  
## Related information

- [Fulfilling Service Contracts](service-fulfill-service-contracts.md)  
- [Create Service Orders](service-how-to-create-service-orders.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
