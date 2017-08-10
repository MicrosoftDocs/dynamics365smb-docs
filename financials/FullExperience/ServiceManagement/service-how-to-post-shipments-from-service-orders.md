---
    title: How to Post Shipments from Service Orders | Microsoft Docs
    description: After specifying the details of a service, you can adjust and post the quantities of items used, time spent, and costs incurred. As a result, [!INCLUDE[d365fin](includes/d365fin_md.md)] makes the necessary changes to reflect the new state of your inventory and current status of the specific order processing.
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
# How to: Post Shipments from Service Orders
After specifying the details of a service, you can adjust and post the quantities of items used, time spent, and costs incurred. As a result, [!INCLUDE[d365fin](includes/d365fin_md.md)] makes the necessary changes to reflect the new state of your inventory and current status of the specific order processing.  
  
 The following procedure shows how to post shipment of service line items in locations that are not set up to require warehouse handling.  
  
### To post shipments from service orders  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Order**, and then choose the related link.  
  
2.  In the window for the selected service order, click **Actions**![Action Menu icon](../media/actionmenuicon.png "actionMenuIcon"), **Order**, **Service Lines**.  
  
3.  In the **Service Lines** window, find the required entries and specify the quantity to be posted in the **Qty. to Ship** field.  
  
    > [!NOTE]  
    >  The quantity to ship value depends on whether you want to post shipment fully or partially. If you choose to ship fully, the value in the **Qty. to Ship** field must be equal to the value in the **Quantity** field. When you post a partial shipment, you must specify the quantity you want to ship initially. If you have already shipped part of the service on the order, make a note of the value in the **Quantity Shipped** field. The maximum quantity you can enter in the **Quantity to Ship** field is the number of units that have not yet been shipped.  
  
4.  Click **Actions**, **Posting**, **Post**. In the window that appears, select **Ship**.  
  
 The program creates the relevant ledger entries (in the warranty ledger, item ledger, service ledger, or G/L) in the database. The program also produces the posted service shipment document and updates the relevant fields on the service lines of the service order.  
  
 If the location is set up to require warehouse handling, then the shipping and moving of service line items function in the same ways as for other source documents. The only difference is that service line items can be consumed either externally or internally and therefore require two different release functions. For more information, see [How to: Prepare Service Line Items for Warehouse Handling](../how-to-prepare-service-line-items-for-warehouse-handling.md).  
  
 For information about shipping service line items in advanced warehousing, see [How to: Pick Items for Warehouse Shipment](../how-to-move-components-to-an-operation-area-in-basic-warehousing.md).  
  
## See Also  
 [How to: Post Invoices from Service Orders](../how-to-post-invoices-from-service-orders.md)   
 [How to: Post Consumption from Service Orders](../how-to-post-consumption-from-service-orders.md)   
 [How to: Undo Service Shipments](../how-to-undo-service-shipments.md)