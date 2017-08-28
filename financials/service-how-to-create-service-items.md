---
    title: How to Create Service Items | Microsoft Docs
    description: When you receive an unregistered item for servicing, you can register it as a service item.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# How to: Create Service Items
When you receive an unregistered item for servicing, you can register it as a service item. There are sevaral ways   
  
## To create a service item  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Items**, and then choose the related link. 2. Choose **New** to create a new service item.  
3. In the **No.** field, enter a number for the service item.  
  
     Alternatively, if you have set up number series for service items in the **Service Mgt. Setup** window, you can press Enter to select the next available service item number.  
  
4. In the **Warranty Starting Date (Parts)** field, you can enter the starting date of the spare parts warranty for this service item. The warranty-related fields are filled in with the default warranty information specified in the **Service Mgt. Setup** window. You can change the default warranty information.  
5. Fill in the rest of the fields on the **General** FastTab.  
6. On the **Customer** FastTab, in the **Customer No.**  field, choose the appropriate customer.  
7. Fill in the fields on the **Shipping**, **Vendor**, and **Detail** FastTabs.  
  
## To create service items within a service order  
When you receive items for service that you want to register as service items, you can create them as service items in the **Service Order** or **Service Quote** windows.  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Orders**, and then choose the related link.  
2. Open the service order that you want to create service items for.  
3. Enter a new service item line.  
4. Fill in the **Serial No.** field.  
5. Fill in the **Description** field.  
6. Choose **Actions**, then **Functions**, and then **Create Service Item**.  
  
A number is assigned to the service item and a service item card is created. The **Service Item No.** field is filled in with the number of the new service item.

## To create a service item when shipping items  
When you ship items by posting either service orders or service invoices, the shipped items are automatically registered as service items if the following condition is met. The items must belong to a service item group with the **Create Service Item** check box selected. If the items have serial numbers registered in the Item Tracking Lines window, this information is copied automatically to the **Serial No.** field on the service item card when creating service items.  
  
The following procedure shows how to create service items when you ship items on service orders.  
  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Orders**, and then choose the related link.  
2. Open the relevant service order.  
3. Choose the **Post** or **Post and Print** action.  
4. Choose the **Ship** or **Ship and Invoice** action.  
5. The service items are automatically created for the items on the order, provided these belong to a service item group that you have set up to create service items. If you registered specific serial numbers in the **Item Tracking Lines** window, they will be assigned to these service items correspondingly.  
  
> [!NOTE]  
>  If an item is a BOM and you have exploded the BOM, the exploded BOM items are processed the same as regular items. Service items are created based on the service items group condition and, optionally, the serial numbers condition. Furthermore, if a service item is created for an exploded BOM item that is made up of other BOM components, these items are created as service item components for the exploded BOM service item.  
>   
>  If an item is a BOM and you have not exploded the BOM, a service item is created for it based on the service item group condition and, optionally, the serial numbers condition.  

## See Also  
[How to: Set Up Service Items](service-how-setup-service-items.md)
[Service Management](service-service.md)   
