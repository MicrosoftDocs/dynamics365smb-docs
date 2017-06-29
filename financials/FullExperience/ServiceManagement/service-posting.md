---
title: "Service Posting"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "service posting"
ms.assetid: af248625-709f-47b3-baaa-b61fa9a5f7ad
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
# Service Posting
Service posting functionality lets you process your documents efficiently and maintain successful customer service policy. You can create and update posted documents, and create ledger entries both in the service area and in other modules to ensure the correct update.  
  
> [!NOTE]  
>  The following describes service posting regardless of how items are physically handled in the warehouse.  
>   
>  In a location that is not set up to require warehouse handling, you perform the posting actions directly from the **Service Lines** window. In locations that involve warehouse handling, the described posting actions, except Ship and Consume, are performed indirectly through varying warehouse ship functions, depending on setup. For more information, see [Pick Items](../WarehouseActivities/pick-items.md) and [How to: Prepare Shipments](../Topic/How%20to:%20Prepare%20Shipments.md).  
  
## Ship  
 The ship option lets you register the relevant items and time entered on the lines of a service order after you complete the service. A posted shipment is created and updates occur in the Inventory module and other modules in ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> to reflect that the items have been taken out of the inventory and sent to the customer. In particular, the item ledger entries, value ledger entries, service ledger entries, and warranty ledger entries are produced.  
  
 If the location is set up to require warehouse handling, then the shipping and moving of service line items functions in the same ways as for other source documents. The only difference is that service line items can be consumed either externally or internally, which requires two different release functions. For more information, see [How to: Prepare Service Line Items for Warehouse Handling](../Service/how-to-prepare-service-line-items-for-warehouse-handling.md).  
  
## Invoice  
 You have to use the invoice option to issue an invoice to the customer you want to charge for the service. Usually, it is the difference between the shipped quantity registered by the **Post Shipment** function and the consumed quantity registered by the **Post Consumption** function that is subject to invoice. You cannot invoice what has not been shipped. When you run the **Post Invoice** function, you create a posted service invoice and update the documents posted before to make them consistent with the quantities that are contained in the issued invoice. Like in other posting procedures, the relevant ledger entries that includes general ledger entries, are generated.  
  
## Ship and Invoice  
 The ship and invoice option lets you issue both a service shipment and an invoice at the same time.  
  
## Ship and Consume  
 With the ship and consume option, you can register and post items, costs, or hours that have been used for servicing but that cannot be included in the invoice to the customer. An invoice is not issued, but you can issue both a service shipment and service consumption at the same time to reflect the fact that some items or hours have been given to the customer free of charge. The corresponding ledger entries are also created to register consumption.  
  
> [!NOTE]  
>  The service posting procedure enables you to perform partial posting. You can create a partial shipment or a partial invoice by filling in the **Qty. to Ship** and **Qty. to Invoice** fields on the individual service lines of the service orders before you post. Note that you cannot create an invoice for something that is not shipped. That is, before you can invoice, you must have registered a shipment, or you must choose to ship and invoice at the same time.  
  
 After the posting has been completed, you will be able to view the posted service documents from the corresponding **Posted Service Shipment** and **Posted Service Invoice** windows. The posted entries created can be seen in various windows that contain posted entries, such as **G\/L Entries**, **Item Ledger Entries**, **Warehouse Entries**, **Service Ledger Entries**, **Job Ledger Entries**, and **Warranty Ledger Entries**.  
  
## See Also  
 [Deliver Service](../Service/deliver-service.md)   
 Service Lines   
 Service Order   
 Item Ledger Entries   
 Location Card   
 [How to: Post Service Lines](../Service/how-to-post-service-lines.md)   
 [How to: Prepare Service Line Items for Warehouse Handling](../Service/how-to-prepare-service-line-items-for-warehouse-handling.md)