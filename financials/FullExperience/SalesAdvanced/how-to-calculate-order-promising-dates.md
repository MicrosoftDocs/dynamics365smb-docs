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
# How to: Calculate Order Promising Dates
The order promising function is a tool for calculating the earliest possible date that an item is available for shipment or delivery. It also creates requisition lines for those dates that you accept.  
  
### To make an item critical  
  
1.  In the **Search** box, enter **Items**, and then choose the related link.  
  
2.  Open the relevant item card.  
  
3.  On the **Planning** FastTab, select the **Critical** field.  
  
### To calculate an order promising date  
  
1.  In the **Search** box, enter **Sales Order**, and then choose the related link.  
  
2.  Open the relevant sales order and select the sales order lines that you want the program to calculate.  
  
3.  On the **Navigate** tab, in the **Plan** group, choose **Order Promising**. The **Order Promising Lines** window opens.  
  
4.  Select a line, and on the **Navigate** tab, in the **Calculate** group, select one of the following options:  
  
    -   Select **Available-to-Promise** if you want to calculate the earliest date that the item will be available with respect to inventory, scheduled receipts, and gross requirements.  
  
    -   Select **Capable-to-Promise** if you know that the item is presently out of stock and you want to calculate the earliest date that the item can be available by issuing new replenishment requisitions.  
  
5.  Choose the **Accept** button to accept the earliest shipment date available.  
  
## See Also  
 Order Promising Lines   
 [About Order Promising](../FullExperience/about-order-promising.md)   
 [How to: Set Up Order Promising](../FullExperience/how-to-set-up-order-promising.md)