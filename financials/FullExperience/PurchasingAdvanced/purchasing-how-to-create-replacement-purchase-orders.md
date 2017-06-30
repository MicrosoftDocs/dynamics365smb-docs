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
# How to: Create Replacement Purchase Orders
You may agree with your vendor that they compensate you for a purchased item by replacing the item. The replacement item can be the same or it can be different. This situation could occur if the vendor mistakenly shipped the wrong item.  
  
### To create a replacement purchase order  
  
1.  In the **Search** box, enter **Purchase Return Orders**, and then choose the related link.  
  
2.  Create a purchase return order. For more information, see [How to: Create Purchase Return Orders](../how-to-create-purchase-return-orders.md).  
  
3.  Enter a purchase return order line for the item that you are returning.  
  
4.  On the next line, enter a line that is a copy of the first line, except in the **Quantity** field, add a minus sign to make it a negative quantity.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Move Negative Lines**.  
  
     In the **Move Negative Purchase Lines** window, select to which document you want to move the line with the negative quantity.  
  
6.  Under **Return Order & Credit Memo**, in the **To Document** field, choose **Order**, and then choose the **OK** button.  
  
     When you run this batch job, the negative line is deleted from the purchase return order, and a new purchase order is created.  
  
7.  Choose the **Yes** button to see the replacement purchase order that is created.  
  
## See Also  
 [How to: Create Purchase Return Orders](../how-to-create-purchase-return-orders.md)   
 [Manage Purchase Returns](../manage-purchase-returns.md)