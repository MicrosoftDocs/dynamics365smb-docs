---
title: How to Create Service Items
description: Read about the different ways you can create service items in Business Central, for example within a service order or when shipping items.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords:
ms.date: 03/22/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Create service items

In [!INCLUDE[prod_short](includes/prod_short.md)], the term "service item" refers to equipment or items that require service. When you create a service order, you specify the items that need service. In the order, you can link a service item to an item in inventory or a service item group.

When you receive an item that needs service, you can register it as a service item. There are several ways to do so. For example, you can create a service item on the **Service Items** page, or as part of another process, such as when working with a service order.

## To create a service item

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Items**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## To create service items within a service order

When you receive items for service that you want to register as service items, you can create them as service items in the **Service Order** or **Service Quote** pages.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Orders**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Choose the **Create Service Item** action.  

    A number is assigned to the service item and a service item card is created. The **Service Item No.** field is filled in with the number of the new service item.

## To create a service item when shipping items

When you ship items by posting either sales orders or sales invoices, the shipped items are automatically registered as service items if the following condition is met. The items must belong to a service item group with the **Create Service Item** check box selected. If the items have serial numbers registered in the Item Tracking Lines page, this information is copied automatically to the **Serial No.** field on the service item card when creating service items.  

The following procedure shows how to create service items when you ship items on sales orders.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Orders**, and then choose the related link.  
2. Open the relevant sales order.  
3. Choose the **Post** or **Post and Print** action.  
4. Choose the **Ship** or **Ship and Invoice** action.  
5. The service items are automatically created for the items on the order, provided these belong to a service item group that you have set up to create service items. If you registered specific serial numbers on the **Item Tracking Lines** page, they will be assigned to these service items.  

> [!NOTE]  
> If an item is a BOM and you have exploded the BOM, the exploded BOM items are processed in the same way as regular items. Service items are created based on the service items group condition and, optionally, the serial numbers condition. Additionally, if a service item is created for an exploded BOM item that is made up of other BOM components, these items are created as service item components for the exploded BOM service item.  
>
> If an item is a BOM and you have not exploded the BOM, a service item is created for it based on the service item group condition and, optionally, the serial numbers condition.  

## To insert a starting fee for a service item

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Tasks**, and then choose the related link.
2. Choose the **Item Worksheet** action.
3. Choose the service line, and then choose **Actions**, choose **Functions**, and then choose **Insert Starting Fee** action.  

    A service line of type **Cost** is inserted with the starting fee. The starting fee applies to the selected service item.

## Block items, item variants, or specific service items

You can prevent items, item variants, or service items from being used in service management transactions, such as service contracts, service orders, and service invoices. This can be useful if you want to restrict the availability of some items or service items for service purposes, for example, due to discontinued support, limited stock, or contractual agreements.

To block an item or an item variant from being used in service management transactions, turn on the **Service Blocked** toggle on the **Item Card**, **Item Variants**, and **Item Variant Card** page. You can also set this field on the **Item Template** page, and it will be copied to the items created from that template.

When an item or an item variant is service blocked, it isn't available for selection on the following pages:

- Service Line (except for service credit memos, where you'll see a notification that the item or variant is blocked, but allowed on this type of document)
- Service Item
- Service Contract Line
- Standard Service Line

If you manually enter an item number or variant that's blocked, you'll get an error message that states, "The field contains a value that cannot be found in the related table."

Additionally, if you have service contracts, service contract quotes, or service orders that include blocked service items or item variants, you can't use the following actions:

- **Lock** or **Make Contract** on the **Service Contract Quote** page.
- **Lock Contract**, **Sign Contract**, **Create Contract Service Orders** or **Create Contract Invoices**  on the **Service Contract** page.
- **Make Order** on the **Service Quote** page.
- **Release to Ship** or **Post** on the **Service Order** page.
- **Post** in the **Service Invoice** page.

### Block a service item

To block a service item from being used in service management transactions, on the **Service Item Card** page, in the **Blocked** field, choose one of the following options:

- **Service Contract**: Block the service item from being used in service contracts and service contract quotes, but not in service orders or other service documents.
- **All**: Block the service item from being used in any service management transaction, including service contracts, service orders, and other service documents.

When a service item is blocked, you can't select it on the following pages:

- Service Contract Line (if blocked for service contract, or all)
- Service Item Line (except for service credit memos, if blocked for all)

If you manually enter a service item number for a blocked service item, an error message displays "The field contains a value that cannot be found in the related table."

Additionally, if you have service contracts, service contract quotes, or service orders that include blocked service items, you can't use the following actions:

- **Lock** and **Make Contract** on the **Service Contract Quote** page (if blocked for service contract, or all).
- **Lock Contract**, **Sign Contract**, or **Change Customer** on the **Service Contract** page (if blocked for service contract, or all).
- **Make Order** on the **Service Quote** (if blocked for all).
- **Release to Ship**, **Post** on the **Service Order** (if blocked for all. If service order documents contain multiple service items, and some are blocked and others are not, you can release and post non-blocked lines. Consider whether to turn on the **One Service Item Line/Order** toggle on the **Service Management Setup** page).
- **Post** on the **Service Invoice** page (if blocked for all).

You can also view the blocked service items by applying a filter to the following reports:

- Service Items (report 5935)
- Service Items Out of Warranty (report 5937)
- Service Profit (Service Items) (report 5938)

### Data upgrade

This feature doesn't require additional setup. However, if you upgrade your [!INCLUDE [prod_short](includes/prod_short.md)], be aware of the following:

- If you have items, item variants, or item templates where the **Sales Blocked** toggle is turned on, the **Service Blocked** field is also turned on for those records during upgrade. This ensures that the existing sales blocked logic also applies to service management transactions.
- Data upgrades only if you have at least one service item in your company, which means you're using the service management functionality and need the data upgrade. If you don't have service items, the data upgrade is skipped and the **Service Blocked** toggle is turned off by default for all items, item variants, and item templates.

## Related information

[Set Up Service Items and Service Item Components](service-how-setup-service-items.md)  
[Setting Up Service Management](service-setup-service.md)  
[Service Management](service-service.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
