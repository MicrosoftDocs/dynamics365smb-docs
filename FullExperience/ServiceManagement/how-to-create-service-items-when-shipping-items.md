---
title: "How to: Create Service Items When Shipping Items"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "service items, creating when shipping items"
ms.assetid: c86d7d26-fb8d-4cf6-b4ef-91ecd68ae9cd
caps.latest.revision: 6
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
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
 [Installed in Item No.](../Topic/\($%20T_90_5901%20Installed%20in%20Item%20No.%20$\).md)   
 [Service Item](../Topic/\($%20T_5940%20Service%20Item%20$\).md)   
 [Item Tracking Lines](../Topic/\($%20N_6510%20Item%20Tracking%20Lines%20$\).md)   
 [How to: Create Service Items](../Service/how-to-create-service-items.md)   
 [How to: Set Up Service Item Groups](../Service/how-to-set-up-service-item-groups.md)   
 [How to: Set Up Service Item Components](../Service/how-to-set-up-service-item-components.md)   
 [How to: Explode Assembly BOMs](../DesignAndEngineering/how-to-explode-assembly-boms.md)