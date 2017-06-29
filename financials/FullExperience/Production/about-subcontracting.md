---
title: "About Subcontracting"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "subcontracting, about"
ms.assetid: 37bd1c5b-1821-4999-9ea2-ae7a90535c79
caps.latest.revision: 9
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
# About Subcontracting
Subcontracting, when a vendor performs one or more operational steps in production, is a standard operational step in many manufacturing companies. Subcontracting can be a rare occurrence or can be an integral part of all production processes.  
  
 The program provides several tools for managing subcontract work:  
  
-   Work Centers with assigned vendor: This feature enables you to set up a work center that is associated with a vendor \(subcontractor\). This is called a subcontract work center. You can specify a subcontract work center on a routing operation, which allows you to easily process the subcontracted activity. In addition, the cost of the operation can be designated at the routing or the work center level.  
  
-   Work Center cost based on units or time: This feature enables you to specify whether costs associated with the work center are based on the production time or a flat charge per unit. Although subcontractors commonly use a flat charge per unit to charge for their services, the program can handle both options \(production time and flat charge per unit\).  
  
-   Subcontracting Worksheet: This feature allows you to find the production orders with material ready to send to a subcontractor and to automatically create purchase orders for subcontract operations from production order routings. Then the program automatically posts the purchase order charges to the production order during the posting of the purchase order. Only production orders with a status of released can be accessed and used from a subcontracting worksheet.  
  
## Subcontract Work Centers  
 Subcontract Work Centers are set up the same as regular work centers with additional information. They are assigned to routings in the same manner as other work centers.  
  
### Subcontract Work Center Fields  
 This **Subcontractor No.** field designates the work center as a subcontract work center. You can enter the number of a subcontractor who supplies the work center. This field can be used to administer work centers, which are not in\-house but perform processing under contract.  
  
 If you subcontract with the vendor for a different rate for each process, then select the **Specific Unit Cost** field. This lets you set up a cost on each routing line and saves the time of re\-entering each purchase order. The cost on the routing line is used in processing instead of the cost on the work center cost fields. Selecting the **Specific Unit Cost** field calculates costs for the vendor by the routing operation.  
  
 If you subcontract at a single rate per vendor, leave the **Specific Unit Cost** field blank. The costs will be set up by filling in **Direct Unit Cost**, **Indirect Cost %**, and **Overhead Rate** fields.  
  
 For information about how to use the subcontract work center in a routing, see [How to: Update Calendar Entries for Work Centers](../OperationsPlanning/how-to-update-calendar-entries-for-work-centers.md).  
  
### Routings that use Subcontract Work Centers  
 Subcontract work centers can be used for operations on routings in the same way as regular work centers.  
  
 You can set up a routing that uses an outside work center as a standard operational step. Alternatively, you can modify the routing for a particular production order to include an outside operation. This might be needed in an emergency such as a server not working correctly, or during a temporary period of higher demand, where the work generally performed in\-house must be sent to a subcontractor.  
  
 For more information, see [How to: Create Routings](../DesignAndEngineering/how-to-create-routings.md).  
  
## Subcontracting Worksheet  
 Once you have [calculated the Subcontracting Worksheet](../OperationsPlanning/how-to-calculate-subcontracting-worksheets-and-create-subcontract-purchase-orders.md), the relevant document, in this case a purchase order, is created.  
  
## Posting Subcontract Purchase Orders  
 Once the Subcontractor Purchase Orders have been created, they can be [posted](../Purchasing/how-to-post-subcontract-purchase-orders.md). Receiving the order posts a Capacity Ledger Entry to the production order and invoicing the order posts the direct cost of the purchase order to the production order.  
  
 When the purchase is posted as received, then an output journal entry is automatically posted for the production order. This only applies if the subcontract operation is the last operation on the production order routing.  
  
> [!CAUTION]  
>  Posting output automatically for an ongoing production order when subcontracted items are received may not be desired. Reasons for this could be that the expected output quantity that is posted may be different from the actual quantity and that the posting date of the automatic output is misleading.  
>   
>  To avoid that the expected output of a production order is posted when subcontract purchases are received, make sure the subcontracted operation is not the last one. Alternatively, insert a new last operation for the final output quantity.  
  
## See Also  
 [How to: Calculate Subcontracting Worksheets and Create Subcontract Purchase Orders](../OperationsPlanning/how-to-calculate-subcontracting-worksheets-and-create-subcontract-purchase-orders.md)   
 [How to: Post Subcontract Purchase Orders](../Purchasing/how-to-post-subcontract-purchase-orders.md)   
 [About Production Orders](../Production/about-production-orders.md)