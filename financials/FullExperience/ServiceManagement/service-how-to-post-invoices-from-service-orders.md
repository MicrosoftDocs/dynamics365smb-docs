---
    title: How to Post Invoices from Service Orders | Microsoft Docs
    description: The following procedure describes how to define the part of service that you will charge the customer for.
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
# How to: Post Invoices from Service Orders
The following procedure describes how to define the part of service that you will charge the customer for.  
  
### To post an invoice from a service order  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Orders**, and then choose the related link.  
  
2.  Select the service order that you want to invoice and open the order card.  
  
3.  On the **Lines** FastTab, choose **Actions**![Action Menu icon](../media/actionmenuicon.png "actionMenuIcon"), choose **Order**, and then choose **Service Lines**.  
  
4.  In the **Service Lines** window, find the required entries and, in the **Qty. to Invoice** field, specify the quantities for which you will charge the customer.  
  
    > [!NOTE]  
    >  You can invoice the customer for the registered service either fully or in parts. If you choose to invoice the customer fully, the value in the **Qty. to Invoice** field must be equal to the value in the **Quantity** field. You can post a full invoice together with a full shipment, and you can post a full invoice for an already posted full shipment that has been neither invoiced nor consumed previously.  
    >   
    >  When you post a partial invoice, there are two ways of specifying the quantity to invoice. If you are going to post the service with **the Ship and Invoice** option, the value in the **Qty. to Invoice** field must be equal to that in the **Qty. to Ship** field. If you want to invoice an already posted shipment, the quantity to invoice must be no larger than the value in the **Quantity Shipped** field.  
  
5.  On the **Actions** tab, in the **Posting** group, choose **Post**. In the window that opens, select **Invoice** or **Ship and Invoice**.  
  
 The service line you have selected is posted. You can post several service lines at once by selecting them all and choosing **Post**. If you do this, make sure you have filled in all the necessary information on the lines you want to post.  
  
 When you post the order with the **Invoice** option, a posted service invoice is created along with the corresponding ledger entries and updates to the relevant fields on the service lines of the order. In addition, previously posted shipment documents are updated with the quantities that have been invoiced. If you select the **Ship and Invoice** posting option, a posted shipment is created.  
  
## See Also  
 [How to: Post Shipments from Service Orders](../how-to-post-shipments-from-service-orders.md)   
 [How to: Post Consumption from Service Orders](../how-to-post-consumption-from-service-orders.md)   
 [How to: Invoice Posted Shipment Lines](../how-to-invoice-posted-shipment-lines.md)   
 [Invoice Discounts on Service Documents](../invoice-discounts-on-service-documents.md)