---
title: "How to: Post Shipments from Service Orders"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "posting, service shipments"
  - "service posting, shipments"
ms.assetid: d6314902-e70c-4be2-8226-5bf8ff81a45e
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
# How to: Post Shipments from Service Orders
After specifying the details of a service, you can adjust and post the quantities of items used, time spent, and costs incurred. As a result, [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] makes the necessary changes to reflect the new state of your inventory and current status of the specific order processing.  
  
 The following procedure shows how to post shipment of service line items in locations that are not set up to require warehouse handling.  
  
### To post shipments from service orders  
  
1.  In the **Search** box, enter **Service Order**, and then choose the related link.  
  
2.  In the window for the selected service order, click **Actions**![Action Menu icon](../DesignAndEngineering/media/actionmenuicon.png "actionMenuIcon"), **Order**, **Service Lines**.  
  
3.  In the **Service Lines** window, find the required entries and specify the quantity to be posted in the **Qty. to Ship** field.  
  
    > [!NOTE]  
    >  The quantity to ship value depends on whether you want to post shipment fully or partially. If you choose to ship fully, the value in the **Qty. to Ship** field must be equal to the value in the **Quantity** field. When you post a partial shipment, you must specify the quantity you want to ship initially. If you have already shipped part of the service on the order, make a note of the value in the **Quantity Shipped** field. The maximum quantity you can enter in the **Quantity to Ship** field is the number of units that have not yet been shipped.  
  
4.  Click **Actions**, **Posting**, **Post**. In the window that appears, select **Ship**.  
  
 The program creates the relevant ledger entries \(in the warranty ledger, item ledger, service ledger, or G\/L\) in the database. The program also produces the posted service shipment document and updates the relevant fields on the service lines of the service order.  
  
 If the location is set up to require warehouse handling, then the shipping and moving of service line items function in the same ways as for other source documents. The only difference is that service line items can be consumed either externally or internally and therefore require two different release functions. For more information, see [How to: Prepare Service Line Items for Warehouse Handling](../Service/how-to-prepare-service-line-items-for-warehouse-handling.md).  
  
 For information about shipping service line items in advanced warehousing, see [How to: Pick Items for Warehouse Shipment](../WarehouseActivities/how-to-pick-items-for-warehouse-shipment.md). For information about moving service line items in advanced warehousing, see [How to: Move Items in Advanced Warehousing](../WarehouseActivities/how-to-move-items-in-advanced-warehousing.md). For basic warehousing, see [How to: Move Components to an Operation Area in Basic Warehousing](../WarehouseActivities/how-to-move-components-to-an-operation-area-in-basic-warehousing.md).  
  
## See Also  
 [How to: Post Invoices from Service Orders](../Service/how-to-post-invoices-from-service-orders.md)   
 [How to: Post Consumption from Service Orders](../Service/how-to-post-consumption-from-service-orders.md)   
 [How to: Undo Service Shipments](../Service/how-to-undo-service-shipments.md)