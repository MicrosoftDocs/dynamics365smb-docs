---
title: Service items and service item components
description: Learn about the things you must set up before you can use service items, including default values such as response time and service price group.
author: brentholtorf
ms.topic: how-to
ms.search.keywords:
ms.date: 10/10/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---
# Set up service items and service item components

To work with service items, first set up the following information:

* Service item groups
* Service item components
* Optional: Service shelves

## To set up service item groups

You can set up groups of items that are related in terms of repair and maintenance. You can define default values for service items in a service item group, such as response time, contract discount percent, and service price group. For items in a service item group, you can select whether you want them to be automatically registered as service items when they're sold.  

You assign service item groups to items on the **Item** card, and to service items on the **Service Item** card.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Item Groups**, and then choose the related link.  
2. Create a new service item group.  
3. Fill in the **Code** and **Description** fields.  
4. In the **Default Contract Discount %** field, enter the default contract discount percentage that you want the service items in the group to have.  
5. In the **Default Serv. Price Group Code** field, enter the default service price group code that you want the service items in the group to have.  
6. In the **Default Response Time (Hours)** field, enter the default response time in hours that you want the service items in the group to have.  
7. If you want to register the items in the group as service items when they're sold, select the **Create Service Item** field.  

## To set up service item components

A service item can consist of several components, which can be replaced with spare parts when the item is serviced. These components are set up on the **Service Item Component List** page. Also, you can set up components for service items that are bills of material (BOMs). Copy the BOM items, and create them as service item components.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Items**, and then choose the related link.
2. Open the service item for which you want to set up components.  
3. Choose the **Components** action. The **Service Item Component List** page opens.  
4. Add a new component.  
5. In the **Type** field, choose **Service Item** if the component itself is a registered service item. Otherwise, select **Item**.  
6. In the **No.** field, choose the item or service item that is a component of the service item.  

## To set up service item components from a BOM

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Items**, and then choose the related link.  
2. Open the service item for which you want to set up components from a BOM.  
3. Choose the **Components** action. The **Service Item Component List** page opens.  
4. Choose the **Copy from BOM** action.  

    If the item that the service item links to is a BOM, [!INCLUDE [prod_short](includes/prod_short.md)] creates components for all items in the BOM.  

## To set up a service shelf

You can set up service shelves that identify where you store your service items. You assign service shelves to service items on the **Service Order** and **Service Item Worksheet** pages.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Shelves**, and then choose the related link.
2. Fill in the fields as necessary.

## Related information

[Set Up Codes for Standard Services](service-how-setup-service-coding.md)  
[Set Up Troubleshooting](service-how-setup-troubleshooting.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
