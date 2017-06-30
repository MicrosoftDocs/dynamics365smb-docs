---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# How to: Prepare Service Line Items for Warehouse Handling
Service lines, like other outbound document lines, such as on sales, outbound transfer, and purchase returns, can function as source document lines for picking to shipment. In addition, service lines can function as source document lines for movement to internal operation areas in the same way as assembly order lines and released production order component lines.  
  
 All source documents must signal to warehouse workers, by means of a release function, that the documents are ready for handling. On service orders, you use the Release to Ship feature to signal to warehouse workers that the items are ready to be picked and shipped to the customer’s address.  
  
 When a source document is released, the related warehouse activity document can be created from the source document to push that request for work to warehouse workers. Alternatively, warehouse workers can generate the warehouse activity document by pulling the request from one or more released source documents. The push or pull options are supported by standard warehouse features in [!INCLUDE[d365fin](../../includes/d365fin_md.md)].  
  
 The following procedure shows the push scenario for service line items. For information about pull scenarios where warehouse workers fill pick documents based on released shipments, see [How to: Pick Items for Warehouse Shipment](../how-to-pick-items-for-warehouse-shipment.md).  
  
### To prepare service line items for shipment  
  
1.  In the **Search** box, enter **Service Orders**, and then choose the related link.  
  
2.  On the **Home** tab, in the **Warehouse** group, choose **Release to Ship**. The **Release Status** field on the service order header changes to **Released to Ship**. A warehouse request now exists that allows the relevant warehouse activity document to be pushed or pulled for the service order.  
  
3.  On the **Home** tab, in the **Warehouse** group, choose **Create Whse. Shipment**. A warehouse shipment document is created by using lines for each service line of type Item. The document only contains the service lines of the service order in question.  
  
 For information about shipping items for any source document in advanced warehouse configurations, see [How to: Pick Items for Warehouse Shipment](../how-to-pick-items-with-inventory-picks.md).  
  
## See Also  
 Service Order   
 [How to: Prepare Shipments](../How%20to:%20Prepare%20Shipments.md)   
 Release Status   
 [How to: Post Shipments from Service Orders](../how-to-post-shipments-from-service-orders.md)