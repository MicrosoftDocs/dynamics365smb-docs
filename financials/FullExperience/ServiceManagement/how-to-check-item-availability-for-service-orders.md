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
# How to: Check Item Availability for Service Orders
You can check and see if an item you need to fulfill an order is in stock, and if it is not, when the item will be in stock. In addition, if an item is available to reserve, you can reserve it to make sure it is available for your use.  
  
### To check item availability for all orders  
  
1.  In the **Search** box, enter **Dispatch Board**, and then choose the related link.  
  
2.  Select an order, and on the **Navigate** tab, in the **Planning** group, choose **Demand Overview**.  
  
     This launches the calculation of item availability. The **Demand Overview** window opens.  
  
3.  In the **Demand Overview** window, expand the item grouping, and view information about the availability of the item. For example, you can see how many items are in inventory. You can also see if and when an item will be available if it is on back order, that is, Source Type \= Purchase, or whether it has been reserved.  
  
### To check item availability for a single order  
  
1.  In the **Search** box, enter **Dispatch Board**, and then choose the related link.  
  
2.  Select an order to review. On the **Navigate** tab, in the **Dispatch Board** group, choose **Show Document**. The **Service Order** window opens.  
  
3.  On the **Navigate** tab, in the **Order** group, choose **Demand Overview**.  
  
     This launches the calculation of item availability and opens the **Demand Overview** window.  
  
4.  In the **Demand Overview** window, expand the item grouping, and view information about the availability of the item. For example, you can see how many items are in inventory. You can also see if and when an item will be available if it is on back order, that is, Source Type \= Purchase, or whether it has been reserved.  
  
## See Also  
 Demand Overview   
 Reservation   
 [How to: Reserve Items for a Service Order](../how-to-reserve-items-for-a-service-order.md)