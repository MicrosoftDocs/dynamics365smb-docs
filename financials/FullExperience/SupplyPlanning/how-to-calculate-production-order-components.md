---
title: "How to: Calculate Production Order Components"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "production orders, components"
  - "consumption, calculating"
ms.assetid: 8755ff91-a877-4a39-8df2-aaa58e6477d1
caps.latest.revision: 11
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
# How to: Calculate Production Order Components
If you have amended production order lines, you must also refresh the components of the production order.  
  
 In the following procedure, the components are calculated for a firm planned production order. This can also be done for production orders with a different status.  
  
### To calculate production order components  
  
1.  In the **Search** box, enter **Firm Planned Prod. Order**, and then choose the related link.  
  
2.  Open the relevant firm planned prod. order  from the list.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Refresh**. The **Refresh Production Order** window opens.  
  
     On the **Production Order** FastTab, the current production order has been selected as a default.  
  
4.  The following table describes the options available for this batch job.  
  
    |[!INCLUDE[bp_tableoption](../ApplicationDesign/includes/bp_tableoption_md.md)]|Selection|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |----------------------------------|---------------|---------------------------------------|  
    |**Scheduling Direction**|**Forward**|This field has no effect on the outcome.|  
    ||**Backward**|This field has no effect on the outcome.|  
    |**Calculate**|**Lines**|You must leave the field blank to retain the current production order line.|  
    ||**Routings**|This field has no effect on the outcome.|  
    ||**Component Need**|Select this field to calculate component need.|  
    |**Warehouse**|**Create Inbound Request**|This field has no effect on the outcome.|  
  
5.  Choose the **OK** button to confirm your selections. The production order components are refreshed.  
  
> [!NOTE]  
>  Calculating production order components deletes previous changes in the components.  
  
## See Also  
 [How to: Refresh Production Orders](../OperationsPlanning/how-to-refresh-production-orders.md)   
 [How to: Calculate Lines from Production Order Headers](../OperationsPlanning/how-to-calculate-lines-from-production-order-headers.md)   
 [How to: Calculate Production Order Routing Lines](../OperationsPlanning/how-to-calculate-production-order-routing-lines.md)   
 [How to: Use the Manufacturing Batch Unit of Measure](../DesignAndEngineering/how-to-use-the-manufacturing-batch-unit-of-measure.md)