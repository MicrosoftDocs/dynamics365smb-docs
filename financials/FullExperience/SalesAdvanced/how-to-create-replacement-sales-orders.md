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
# How to: Create Replacement Sales Orders
You may decide to compensate a customer for an item that you have sold them by replacing the item. You can make a replacement with the same item or a different item. This situation could occur if you mistakenly shipped the wrong item to the customer, for example.  
  
 At this point, you have shipped the original item to the customer.  
  
### To create a replacement sales order from a sales return order  
  
1.  In the **Search** box, enter **Sales Return Orders**, and then choose the related link.  
  
2.  Create a sales return order for the customer. On the **Home** tab, in the **New** group, choose **New**.  
  
3.  Enter a line for the returned item.  
  
4.  On the next line, make a negative entry for the replacement item by inserting a negative amount in the **Quantity** field.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Move Negative Lines**.   
    The **Move Negative Sales Lines** batch job request window opens.  
  
6.  When you run this batch job, the negative line for the replacement item is deleted from the sales return order and inserted itto a new **Sales Order** window.  
  
## See Also  
 Sales Return Order   
 [How to: Create Sales Return Orders](../how-to-create-sales-return-orders.md)   
 [Manage Sales Returns](../manage-sales-returns.md)