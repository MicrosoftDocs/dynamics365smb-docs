---
title: "How to: Calculate Production Order Routing Lines"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "routings, calculating lines"
  - "production orders, routing lines"
  - "operations, calculating"
ms.assetid: ada4fd6e-14f8-44a0-a872-4187b92bcc8e
caps.latest.revision: 12
ms.author: "sgroespe"
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
# How to: Calculate Production Order Routing Lines
If you have amended production order lines, you must also refresh the routing of the production order.  
  
 In the following procedure, the routing lines are calculated for a firm planned production order. This can also be done for production orders with a different status.  
  
### To calculate production order routing lines  
  
1.  In the **Search** box, enter **Firm Planned Prod. Order**, and then choose the related link.  
  
2.  Open the relevant firm planned production order  from the list.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Refresh**. The **Refresh Production Order** window opens.  
  
4.  On the **Production Order** FastTab, the current production order has been selected as a default.  
  
5.  The following table describes the options available for this batch job.  
  
    |FIX INCLUDE HERE<!--[!INCLUDE[bp_tableoption](../ApplicationDesign/includes/bp_tableoption_md.md)] -->|Selection|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
    |----------------------------------|---------------|---------------------------------------|  
    |**Scheduling Direction**|**Forward**|This field has no effect on the outcome.|  
    ||**Backward**|This field has no effect on the outcome.|  
    |**Calculate**|**Lines**|You must leave the field blank to retain the current production order line.|  
    ||**Routings**|Select this field to calculate routings.|  
    ||**Component Need**|This field has no effect on the outcome.|  
    |**Warehouse**|**Create Inbound Request**|This field has no effect on the outcome.|  
  
6.  Choose the **OK** button to confirm your selections. The production order routing lines are refreshed.  
  
> [!NOTE]  
>  Calculating production order routing lines deletes previous changes in the routings.  
  
## See Also  
 [How to: Refresh Production Orders](../OperationsPlanning/how-to-refresh-production-orders.md)   
 [How to: Calculate Production Order Components](../OperationsPlanning/how-to-calculate-production-order-components.md)   
 [How to: Calculate Lines from Production Order Headers](../OperationsPlanning/how-to-calculate-lines-from-production-order-headers.md)