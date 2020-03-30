---
    title: How to Create Service Items | Microsoft Docs
    description: When you receive an unregistered item for servicing, you can register it as a service item.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Create Service Items
In [!INCLUDE[d365fin](includes/d365fin_md.md)], the term "service item" refers to equipment or items that require service. When you create a service order, you specify the items that need service. In the order, you can link a service item to an item in inventory or a service item group.    

When you receive an item that needs service, you can register it as a service item. There are several ways to do so. For example, you can create a service item on the **Service Items** page, or as part of another process, such as when working with a service order.   

## To create a service item  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Items**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## To create service items within a service order  
When you receive items for service that you want to register as service items, you can create them as service items in the **Service Order** or **Service Quote** pages.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Orders**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Choose the **Create Service Item** action.  

    A number is assigned to the service item and a service item card is created. The **Service Item No.** field is filled in with the number of the new service item.

## To create a service item when shipping items  
When you ship items by posting either sales orders or sales invoices, the shipped items are automatically registered as service items if the following condition is met. The items must belong to a service item group with the **Create Service Item** check box selected. If the items have serial numbers registered in the Item Tracking Lines page, this information is copied automatically to the **Serial No.** field on the service item card when creating service items.  

The following procedure shows how to create service items when you ship items on sales orders.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
2. Open the relevant sales order.  
3. Choose the **Post** or **Post and Print** action.  
4. Choose the **Ship** or **Ship and Invoice** action.  
5. The service items are automatically created for the items on the order, provided these belong to a service item group that you have set up to create service items. If you registered specific serial numbers on the **Item Tracking Lines** page, they will be assigned to these service items.  

> [!NOTE]  
>  If an item is a BOM and you have exploded the BOM, the exploded BOM items are processed in the same way as regular items. Service items are created based on the service items group condition and, optionally, the serial numbers condition. Additionally, if a service item is created for an exploded BOM item that is made up of other BOM components, these items are created as service item components for the exploded BOM service item.  
>   
>  If an item is a BOM and you have not exploded the BOM, a service item is created for it based on the service item group condition and, optionally, the serial numbers condition.  

## To insert a starting fee for a service item
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Tasks**, and then choose the related link.
2. Choose the **Item Worksheet** action.
3. Choose the service line, and then choose **Actions**, choose **Functions**, and then choose **Insert Starting Fee** action.  

    A service line of type **Cost** is inserted with the starting fee. The starting fee applies to the selected service item.

## See Also  
[Set Up Service Items and Service Item Components](service-how-setup-service-items.md)  
[Setting Up Service Management](service-setup-service.md)  
[Service Management](service-service.md)  
