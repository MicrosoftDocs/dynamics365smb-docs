---
title: "How to: Prepare Service Line Items for Warehouse Handling"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "warehouse, service lines"
  - "service lines, warehouse handling"
ms.assetid: 7dc3bcfc-7056-4ee4-82a6-5d0b9e49cf73
caps.latest.revision: 8
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
# How to: Prepare Service Line Items for Warehouse Handling
Service lines, like other outbound document lines, such as on sales, outbound transfer, and purchase returns, can function as source document lines for picking to shipment. In addition, service lines can function as source document lines for movement to internal operation areas in the same way as assembly order lines and released production order component lines.  
  
 All source documents must signal to warehouse workers, by means of a release function, that the documents are ready for handling. On service orders, you use the Release to Ship feature to signal to warehouse workers that the items are ready to be picked and shipped to the customer’s address.  
  
 When a source document is released, the related warehouse activity document can be created from the source document to push that request for work to warehouse workers. Alternatively, warehouse workers can generate the warehouse activity document by pulling the request from one or more released source documents. The push or pull options are supported by standard warehouse features in [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)].  
  
 The following procedure shows the push scenario for service line items. For information about pull scenarios where warehouse workers fill pick documents based on released shipments, see [How to: Pick Items for Warehouse Shipment](../WarehouseActivities/how-to-pick-items-for-warehouse-shipment.md).  
  
### To prepare service line items for shipment  
  
1.  In the **Search** box, enter **Service Orders**, and then choose the related link.  
  
2.  On the **Home** tab, in the **Warehouse** group, choose **Release to Ship**. The **\($ T\_5900\_130 Release Status $\)** field on the service order header changes to **Released to Ship**. A warehouse request now exists that allows the relevant warehouse activity document to be pushed or pulled for the service order.  
  
3.  On the **Home** tab, in the **Warehouse** group, choose **Create Whse. Shipment**. A warehouse shipment document is created by using lines for each service line of type Item. The document only contains the service lines of the service order in question.  
  
 For information about shipping items for any source document in advanced warehouse configurations, see [How to: Pick Items for Warehouse Shipment](../WarehouseActivities/how-to-pick-items-for-warehouse-shipment.md). For basic warehouse configurations, see [How to: Pick Items with Inventory Picks](../DesignAndEngineering/how-to-pick-items-with-inventory-picks.md).  
  
## See Also  
 [\($ N\_5900 Service Order $\)](../Topic/\($%20N_5900%20Service%20Order%20$\).md)   
 [How to: Prepare Shipments](../Topic/How%20to:%20Prepare%20Shipments.md)   
 [\($ T\_5900\_130 Release Status $\)](../Topic/\($%20T_5900_130%20Release%20Status%20$\).md)   
 [How to: Post Shipments from Service Orders](../Service/how-to-post-shipments-from-service-orders.md)