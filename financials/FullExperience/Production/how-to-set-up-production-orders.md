---
title: "How to: Set Up Production Orders"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "production orders, setting up"
ms.assetid: 40875cd7-06f9-4537-b8d9-262e49739e50
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
# How to: Set Up Production Orders
When you set up a new production order, there are fields that must always be filled in, fields that can be filled in as needed, and fields in which you cannot enter anything.  
  
 In the following procedure, a firm planned production order is used.  
  
### To set up a production order  
  
1.  In the **Search** box, enter **Firm Planned Prod. Order**, and then choose the related link.  
  
2.  Fill in the fields on the production order header. The following fields are required.  
  
    |FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../ApplicationDesign/includes/bp_tablefield_md.md)] --> -->|FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)] --> -->|  
    |---------------------------------|---------------------------------------|  
    |**No.**|Specifies the next number from the production order number series.|  
    |**Source Type**|Specifies either of the following types:<br /><br /> -   **Item** \- Standard items are produced for inventory.<br />-   **Familiy** \- A predefined family of items is produced for inventory.<br />-   **Sales header** \- Items are produced for the sales order that you select in the **Source No.** field.|  
    |**Source No.**|Specifies the production order source according to the value that you select in the **Source Type** field.|  
    |**Search Description**|Specifies the description of the source that you enter in the **Source No.** field.|  
    |**Quantity**|Specifies how many units to produce.|  
    |**Due Date**|Specifies when the produced output is needed, for example, on a sales order.|  
  
3.  Fill in the fields on the production order lines. The following fields are required.  
  
    |[!INCLUDE[bp_tablefield](../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Item No.**|Specifies the item that is produced.|  
    |**Due Date**|Specifies when the produced item is needed, for example, on a sales order.|  
    |**Starting Date\-Time**|Specifies the starting date and time when the first operation must start. **Note:**  This field is automatically filled based on the item’s routing and the value that you enter in the **Due Date** field.|  
    |**Ending Date\-Time**|Specifies the ending date and time when the last operation must end. **Note:**  This field is automatically filled based on the item’s routing and the value that you enter in the **Due Date** field.|  
    |**Quantity**|Specifies how many units to produce.|  
  
 Instead of filling the production order line fields manually, use the **Refresh** function. For more information, see [How to: Refresh Production Orders](../OperationsPlanning/how-to-refresh-production-orders.md).  
  
## See Also  
 [How to: Create Production Order Headers](../OperationsPlanning/how-to-create-production-order-headers.md)   
 [How to: Refresh Production Orders](../OperationsPlanning/how-to-refresh-production-orders.md)   
 [How to: Refresh Production Orders](../OperationsPlanning/how-to-refresh-production-orders.md)   
 [About Production Orders](../Production/about-production-orders.md)   
 [How to: Use the Manufacturing Batch Unit of Measure](../DesignAndEngineering/how-to-use-the-manufacturing-batch-unit-of-measure.md)