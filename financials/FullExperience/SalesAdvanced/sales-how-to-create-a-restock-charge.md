---
    title: How to: Create a Restock Charge | Microsoft Docs
    description: You may decide to charge your customer a restock fee to cover the physical handling costs of returning an item. This could occur if the customer mistakenly ordered the wrong item or changed their mind after receiving the item you sold them, for example.
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
# How to: Create a Restock Charge
You may decide to charge your customer a restock fee to cover the physical handling costs of returning an item. This could occur if the customer mistakenly ordered the wrong item or changed their mind after receiving the item you sold them, for example.  
  
 At this point, you have shipped the item to the customer.  
  
### To create a restock charge  
  
1.  In the **Search** box, enter **Sales Return Orders**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**. Create a sales return order for the customer.  
  
3.  On the **Lines** FastTab, enter a line for the returned item. In the **Type** field, select **Charge (Item)**.  
  
4.  In the **No.** field, select the appropriate value.  
  
5.  Fill in the **Quantity** field.  
  
6.  In the **Unit Price** field, enter a negative amount equivalent to the restock charge.  
  
7.  On the **Lines** FastTab, choose **Actions**![Action Menu icon](../media/actionmenuicon.png "actionMenuIcon"), choose **Line**, and then choose **Item Charge Assignment**.   
    The **Item Charge Assignment (Sales)** window opens.  
  
8.  In the **Qty. to Assign** field, enter the same amount that you entered in the **Quantity** field on the relevant sales return order.  
  
 When you post the sales return order, the restock charge is added to the relevant sales entry amount. In this way, you can maintain accurate item statistics.  
  
> [!TIP]  
>  Note that you can also select **Account (G/L)** in the **Type** field and make a negative entry for the line by inserting a negative amount in the **Quantity** field. Then the restock charge is posted directly to the specified G/L account.  
  
## See Also  
 Item Charge Assignment (Sales)%20$).md)   
 [How to: Create Sales Return Orders](../how-to-create-sales-return-orders.md)   
 Item Charges   
 [How to: Assign Item Charges to Sales Documents](../how-to-assign-item-charges-to-sales-documents.md)