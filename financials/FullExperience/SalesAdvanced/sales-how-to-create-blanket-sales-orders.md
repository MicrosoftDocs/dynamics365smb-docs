---
    title: How to: Create Blanket Sales Orders | Microsoft Docs
    description: Use blanket orders when a customer has agreed to buy large quantities that are to be delivered in several smaller shipments over a certain period of time. For more information, see [About Blanket Sales Orders](../about-blanket-sales-orders.md).
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
# How to: Create Blanket Sales Orders
Use blanket orders when a customer has agreed to buy large quantities that are to be delivered in several smaller shipments over a certain period of time. For more information, see [About Blanket Sales Orders](../about-blanket-sales-orders.md).  
  
 The topic contains the following sections:  
  
-   To create a blanket sales order.  
  
-   To create a sales order from a blanket sales order.  
  
### To create a blanket sales order  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Blanket Sales Orders**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**. Create a new blanket sales order.  
  
3.  In the **No.** field, you can press the Enter key to select the next available number. Fill in the **Sell-to Customer No.** field.  
  
4.  Leave the **Order Date** field blank. When the separate sales orders are created from the blanket order, the order date of the sales order is set to equal the actual work date.  
  
     On the **Lines** FastTab, create separate lines for each shipment. For instance, if your customer wants 1000 units split out equally between four weeks, you would enter four separate lines of 250 units each.  
  
5.  Select **Item** in the **Type** field for each line, and fill in the **No.** field.  
  
6.  In the **Quantity** field, for each line, type the amount to be ordered for this line.  
  
     The **Qty. to Ship** field is filled in automatically to indicate the quantity that the sales orders are to be created for on the respective shipment dates.  
  
7.  In the **Shipment Date** field for each line, enter the date this item must be shipped.  
  
8.  Choose the **OK** button.  
  
### To create a sales order from a blanket sales order  
  
1.  To create an order for any of the lines in the blanket assembly order, remove the quantity in the **Qty. to Ship** field on all the lines that you DO NOT wish to ship at this time.  
  
2.  When you are ready to create orders, on the **Actions** tab, in the **Process** group, choose **Make Order**, and then choose **Yes**. A message appears informing you that the blanket order has been assigned an order number. Note that the blanket order has not been deleted.  
  
3.  Choose the **OK** button.  
  
4.  To see the results of the preceding steps, on the **Lines** FastTab, choose **Actions**![Action Menu icon](../media/actionmenuicon.png "actionMenuIcon"), choose **Line**, choose **Unposted Lines**, and then choose **Orders**.  
  
5.  In the **Sales Lines** window, select the appropriate sales order, on the **Lines** FastTab, choose **Actions**![Action Menu icon](../media/actionmenuicon.png "actionMenuIcon"), choose **Line**, and then choose **Show Document**.  
  
 The following applies to sales orders after they have been created from blanket sales orders:  
  
-   After the blanket order is converted into a sales order, the sales order contains all the lines from the blanket order. The lines where the quantity in the **Qty. to Ship** field was deleted appear, but with blank **Quantity** fields. You may choose to leave, edit, or delete the lines.  
  
-   It is important to remember that the sales order line quantity must not exceed the quantity of the associated blanket order line. Otherwise, posting of the sales order will not be possible.  
  
-   When the sales order is posted as shipped and/or invoiced, the **Quantity Shipped** and **Quantity Invoiced** fields are updated on the related blanket order.  
  
-   The blanket order number and line number are recorded as properties of the sales lines when created from a blanket order.  
  
-   When sales orders are not created directly from the blanket order but still relate to it, a link between a sales order and a blanket order can be established by entering the associated blanket order number in the **Blanket Order No.** field on the sales order line.  
  
-   After the sales order has been created for the total quantity of a blanket order line, no other sales order can be created for the same line. Users are prevented from entering a quantity in the **Qty. to Ship** field. If, however, additional quantities need to be added to a blanket order, the value in the **Quantity** field can be increased and additional orders can then be created.  
  
-   The invoiced blanket sales order remains in the system until it is deleted, either by deleting individual blanket orders or by running the **Delete Invoiced Blanket Sales Orders** batch job.  
  
-   If a customer is also recorded as a contact in the Marketing application area, and if you have specified an interaction template code for blanket sales order in the **Marketing Setup** window, an interaction is recorded in the Interaction Log Entry table when you select **Print** to print the blanket sales order.  
  
## See Also  
 [How to: Convert Blanket Sales Orders to Sales Orders](../how-to-convert-blanket-sales-orders-to-sales-orders.md)   
 [How to: View the Status of Blanket Sales Orders](../how-to-view-the-status-of-blanket-sales-orders.md)   
 [How to: View Unposted and Posted Blanket Sales Order Lines](../how-to-view-unposted-and-posted-blanket-sales-order-lines.md)   
 Delete Invd Blnkt Sales Orders