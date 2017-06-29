---
title: "How to: Create Customers within Service Orders"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "service orders, creating customers"
ms.assetid: e4d5f067-c640-4f74-914c-d4be853fe73c
caps.latest.revision: 7
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
# How to: Create Customers within Service Orders
When you create service orders for customers that are not registered in FIX INCLUDE HERE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] -->, you can create the customers within the **Service Order** or **Service Quote** windows.  
  
 You need to set up customer templates before you can create customers within service orders. For more information, see [How to: Set Up Customer Templates](../Service/how-to-set-up-customer-templates.md).  
  
### To create a customer within a service order  
  
1.  In the **Search** box, enter **Service Orders**, and then choose the related link.  
  
2.  Create a new service order.  
  
3.  In the **No.** field, enter a number for the service order.  
  
     Alternatively, if you have set up number series for service orders in the **Service Mgt. Setup** window, you can press the Enter key to select the next available service order number.  
  
4.  Fill in the **Name** , **Address**, and **Post Code\/City** fields for the new customer.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Create Customer**. The **Customer Templates List** window opens. Browse to the relevant template, and then choose the **OK** button.  
  
 A number is automatically assigned to the new customer and a customer card is created with the relevant fields in the service order filled in by copying information from the service customer template.  
  
## See Also  
 [How to: Create Service Orders](../Service/how-to-create-service-orders.md)