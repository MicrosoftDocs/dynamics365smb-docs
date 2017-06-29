---
title: "How to: Post Subcontract Purchase Orders"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "purchase orders, subcontracts"
  - "subcontracting, purchase orders"
  - "subcontracting, posting"
ms.assetid: 9f217cf5-a2da-43e2-a324-683a3cafac04
caps.latest.revision: 6
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
# How to: Post Subcontract Purchase Orders
When the purchase order has been created from the subcontractor worksheet, then it can be posted. For more information, see [How to: Calculate Subcontracting Worksheets and Create Subcontract Purchase Orders](../OperationsPlanning/how-to-calculate-subcontracting-worksheets-and-create-subcontract-purchase-orders.md).  
  
### To post a subcontract purchase order  
  
1.  In the **Search** box, enter **Purchase Orders**, and then select the related link.  
  
2.  Open a purchase order that is created from the subcontracting worksheet.  
  
     On the purchase order lines, you see the same information that was in the worksheet. The **Prod. Order No.**, **Prod. Order Line No.**, **Operation No.**, and **Work Center No.** fields are filled in with the information from the source production order.  
  
3.  On the **Actions** tab, in the **Posting** group, choose **Post**.  
  
 When the purchase is posted as received, then an output journal entry is automatically posted for the production order. This only applies if the subcontract operation is the last operation on the production order routing.  
  
> [!CAUTION]  
>  Posting output automatically for an ongoing production order when subcontracted items are received may not be desired. Reasons for this could be that the expected output quantity that is posted may be different from the actual quantity and that the posting date of the automatic output is misleading.  
>   
>  To avoid that the expected output of a production order is posted when subcontract purchases are received, make sure the subcontracted operation is not the last one. Alternatively, insert a new last operation for the final output quantity.  
  
 When the purchase order is posted as invoiced, then the direct cost of the purchase order is posted to the production.  
  
## See Also  
 [About Subcontracting](../OperationsPlanning/about-subcontracting.md)   
 [How to: Post Purchase Orders](../Purchasing/how-to-post-purchase-orders.md)   
 Subcontracting Worksheet   
 [How to: Register Consumption and Output](../Production/how-to-register-consumption-and-output.md)   
 [How to: Calculate Subcontracting Worksheets and Create Subcontract Purchase Orders](../OperationsPlanning/how-to-calculate-subcontracting-worksheets-and-create-subcontract-purchase-orders.md)   
 [Design Details: Inventory Costing](../ApplicationDesign/design-details-inventory-costing.md)