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
# How to: Register Costs for Service Orders
When working on service items in service orders, you may need to register additional costs for a service order in general. For example, you can insert a fee for travel to the service zone where the customer is located for whom the service order was created. You can also insert a starting fee for the order. For more information, see [How to: Insert Travel Fees for Service Orders](../Service/how-to-insert-travel-fees-for-service-orders.md) and [How to: Insert Starting Fees for Service Orders](../Service/how-to-insert-starting-fees-for-service-orders.md).  
  
 The following procedure shows how to register other costs for service orders in the **Service Lines** window.  
  
### To register costs for service orders  
  
1.  In the **Search** box, enter **Service Orders**, and then choose the related link.  
  
2.  Open the service order that you want to register a cost for.  
  
3.  Choose **Actions**![Action Menu icon](../DesignAndEngineering/media/actionmenuicon.png "actionMenuIcon"), choose **Order**, and then choose **Service Lines**. The **Service Lines** window opens.  
  
4.  If the service order requires a link between service and service items, in the **Service Lines Filter** field, select **Service Item Line Non-Related**.  
  
5.  Enter a new service line.  
  
6.  In the **Type** field, select **Cost**.  
  
7.  In the **No.** field, select the relevant cost.  
  
8.  In the **Quantity** field, enter how often you intend to invoice the cost.  
  
 Repeat these steps for each service cost you want to register.  
  
## See Also  
 [How to: Register Costs for Service Items](../Service/how-to-register-costs-for-service-items.md)   
 [How to: Set Up Service Costs](../Service/how-to-set-up-service-costs.md)