---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# How to: Create Service Items When Shipping Items
When you ship items by posting either service orders or service invoices, the shipped items are automatically registered as service items if the following condition is met. The items must belong to a service item group with the **Create Service Item** check box selected. If the items have serial numbers registered in the Item Tracking Lines window, this information is copied automatically to the **Serial No.** field on the service item card when creating service items.  
  
 The following procedure shows how to create service items when you ship items on service orders.  
  
### To create a service item when shipping items  
  
1.  In the **Search** box, enter **Service Orders**, and then choose the related link.  
  
2.  Open the relevant service order.  
  
3.  On the **Actions** tab, in the **Posting** group, choose **Post** or **Post and Print**.  
  
4.  In the window that opens, select **Ship** or **Ship and Invoice**, and then choose the **OK** button.  
  
5.  The service items are automatically created for the items on the order, provided these belong to a service item group that you have set up to create service items. If you registered specific serial numbers in the **Item Tracking Lines** window, they will be assigned to these service items correspondingly.  
  
> [!NOTE]  
>  If an item is a BOM and you have exploded the BOM, the exploded BOM items are processed the same as regular items. Service items are created based on the service items group condition and, optionally, the serial numbers condition. Furthermore, if a service item is created for an exploded BOM item that is made up of other BOM components, these items are created as service item components for the exploded BOM service item.  
>   
>  If an item is a BOM and you have not exploded the BOM, a service item is created for it based on the service item group condition and, optionally, the serial numbers condition.  
  
## See Also  
 Installed in Item No.   
 Service Item   
 Item Tracking Lines   
 [How to: Create Service Items](../how-to-create-service-items.md)   
 [How to: Set Up Service Item Groups](../how-to-set-up-service-item-groups.md)   
 [How to: Set Up Service Item Components](../how-to-set-up-service-item-components.md)   
 [How to: Explode Assembly BOMs](../how-to-explode-assembly-boms.md)