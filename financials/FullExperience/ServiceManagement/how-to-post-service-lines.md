---
title: "How to: Post Service Lines"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "service lines, posting"
  - "posting, service lines"
ms.assetid: 8c538389-775e-4589-8175-b9512923b695
caps.latest.revision: 8
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
# How to: Post Service Lines
If you have to work on a service order for a considerable time without posting it, you may want to post some of the service lines linked to it as a way, for example, of keeping your inventory updated. You can post by specifying the relevant quantities on the lines to be posted. You may choose to post the lines one by one or by selecting several lines at a time.  
  
 The following procedure describes shipment posting directly from a service order in locations without warehouse handling set up. If the location is set up to require warehouse handling, then shipment posting happens in a different warehouse document, depending on the location setup. For more information, see [How to: Prepare Service Line Items for Warehouse Handling](../Service/how-to-prepare-service-line-items-for-warehouse-handling.md).  
  
### To post service lines  
  
1.  In the **Search** box, enter **Service Orders**, and then choose the related link.  
  
2.  Open the relevant service order.  
  
3.  Select a service line that you want to post. Choose **Actions**![Action Menu icon](../DesignAndEngineering/media/actionmenuicon.png "actionMenuIcon"), choose **Order**, and then choose **Service Lines**. The **Service Lines** window opens.  
  
4.  On the lines you are going to post, fill in the **Qty. to Ship**, **Qty. to Invoice**, and **Qty. to Consume** fields, depending on the way you are going to post the lines.  
  
5.  Select the lines you want to post. On the **Actions** tab, in the **Posting** group, choose **Post**. A window opens in which you have to select one of the following options.  
  
    |**Posting Option**|**Result**|  
    |------------------------|----------------|  
    |**Ship**|Posts shipment of the items, resource hours, or costs on the line. It creates a posted service shipment document along with the relevant ledger entries.|  
    |**Invoice**|Invoices the items, resources, or costs that have already been shipped. It creates a posted invoice document along with the corresponding ledger entries.|  
    |**Ship and Invoice**|Invoices and ships the items, resources, or costs on the lines. It creates a posted service shipment and a posted service invoice.|  
    |**Ship and Consume**|Posts shipment and consumption on the order. It updates the relevant quantities on the current service line of the order and service shipment document created for the line previously.|  
  
 It is possible to post consumption only if there is some shipped and not invoiced and not consumed quantity on the line.  
  
## See Also  
 [How to: Post Service Orders](../Service/how-to-post-service-orders.md)   
 [How to: Post Shipments from Service Orders](../Service/how-to-post-shipments-from-service-orders.md)   
 [How to: Post Invoices from Service Orders](../Service/how-to-post-invoices-from-service-orders.md)   
 [How to: Post Consumption from Service Orders](../Service/how-to-post-consumption-from-service-orders.md)   
 [Invoice Discounts on Service Documents](../Service/invoice-discounts-on-service-documents.md)   
 [How to: Pick Items for Warehouse Shipment](../WarehouseActivities/how-to-pick-items-for-warehouse-shipment.md)   
 [How to: Move Components to an Operation Area in Basic Warehousing](../WarehouseActivities/how-to-move-components-to-an-operation-area-in-basic-warehousing.md)