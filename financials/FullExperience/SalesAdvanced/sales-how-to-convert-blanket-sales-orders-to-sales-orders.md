---
    title: How to Convert Blanket Sales Orders to Sales Orders | Microsoft Docs
    description: You can either convert an entire blanket order into one order, or you can make it into a number of separate orders, depending upon how you want the blanket order to be invoiced.
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
# How to: Convert Blanket Sales Orders to Sales Orders
You can either convert an entire blanket order into one order, or you can make it into a number of separate orders, depending upon how you want the blanket order to be invoiced.  
  
 You must have already set up a blanket order.  
  
### To convert a blanket sales order to a sales order  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Blanket Sales Orders**, and then choose the related link.  
  
2.  Open the relevant blanket sales order.  
  
3.  On the **Shipping** FastTab, in the **Shipment Date** field, type the same date as the date in the **Shipment Date** field on the first line.  
  
4.  To create an order out of only one blanket order line, fill in the **Qty. to Ship** field on the relevant line.  
  
5.  On the **Actions** tab, in the **General** group, choose **Make Order**.  
  
 A message appears informing you that the blanket order has been assigned an order number. You can see the new sales order in the [sales order list](DynamicsNAV:////runpage?Page=9305). Note that the blanket order has not been deleted.  
  
## See Also  
 Blanket Sales Order   
 Sales Order   
 [How to: Create Blanket Sales Orders](../how-to-create-blanket-sales-orders.md)   
 [About Blanket Sales Orders](../about-blanket-sales-orders.md)