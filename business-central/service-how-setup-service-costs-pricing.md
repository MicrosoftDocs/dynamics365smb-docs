---
title: Set Up Pricing and Costs for Services
description: Learn how to use pricing features to set up and customize your application so that you apply and adjust pricing on service items, repairs, and orders.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: service, cost, service order
ms.date: 10/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up pricing and additional costs for services

You can use the [!INCLUDE[prod_short](includes/prod_short.md)] pricing features to set up and customize your application so that you apply and adjust pricing on service items, repairs, and orders. These pricing decisions are then easily transmitted to the invoicing process.  
  
As your implementation requires, you can set up pricing groups and map them to specific time periods, customers, or currency. You can set up fixed, minimum, or maximum pricing, depending on the service contracts that you have with customers. Finally, as you adjust your prices, you can view and approve the changes before committing them to the ledger.  

## Set up a service price group

You can set up groups containing service items that you want to receive the same special service pricing. You assign service price groups to service items on service item lines. You can also assign service price groups to service item groups.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Price Groups**, and then choose the related link.  
2. Create a new service price group.  
3. Fill in the **Code** and **Description** fields.  
4. Choose the **Setup** action.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

 > [!Tip]
 > The **Adjustment Type** and **Amount** fields work together to specify whether an adjustment concerns a fixed amount, or applies only when the total service price exceeds or is lower than the amount in the **Amount** field.  

## Set up a service price adjustment group

You can set up price adjustment groups to adjust service pricing of service items. For example, you can set up price adjustment groups that adjust price of freight or spare parts.  
  
1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Price Adjustment Groups**, and then choose the related link.  
2. Create a new service price adjustment group.  
3. Fill in the **Code** and **Description** fields.  
4. In the **Type** field, enter the type of the entry that you want to adjust.  
  
    * To adjust only one specific entry, enter the number of this entry in the **No.** field. When you leave this field blank, your adjustment group adjusts all entries of the type defined in the **Type** field.  
    * To adjust service prices related to only one specific service, fill in the **Work Type** field. When you leave this field blank, it will just be ignored.  
  
5. In the **Description** field, enter a short description of the service price adjustment.  
6. To adjust service prices related to only one specific general product posting group, fill in the **Gen. Prod. Posting Group** field.

> [!Tip]
> You can choose **Details** to add additional information about the adjustment group. For example, you can specify which item belongs to the service price adjustment group, and whether this is an item, a resource, a resource group, or a service charge.  

## Set up additional costs for services

When you work with service items and service orders, you may need to register additional costs, such as travel costs to particular service zones or starting fees. When you create a service order, you can insert these costs and a line with the type **Cost** will be added to the order. Alternatively, if you want to apply the cost to all service orders, you can set up a default cost. For example, if you always want to apply a starting fee.
  
### Set up service costs

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Costs**, and then choose the related link. 
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

### Specify a default cost for service orders

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Setup**, and then choose the related link.
2. In the **Service Order Starting Fee** field, choose the appropriate service cost.

## Related information

- [Setting Up Service Management](service-setup-service.md)  
- [Service Management](service-service.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
