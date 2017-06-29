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
# How to: Create Blanket Purchase Orders
You can use blanket orders when you have committed to buying large quantities of an item that are to be received in several smaller shipments over a certain period of time. For more information, see [About Blanket Purchase Orders](../about-blanket-purchase-orders.md).  
  
### To create a blanket purchase order  
  
1.  In the **Search** box, enter **Blanket Purchase Orders**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New** to open a new blanket purchase order.  
  
3.  In the **No.** field, press Enter to assign the default number series.  
  
4.  In the **Buy-from Vendor No.** field, select the vendor.  
  
5.  Leave the **Order Date** field blank. When the separate purchase orders are created from the blanket order, the order date of the purchase order will be set to equal to the actual work date.  
  
     In the detail lines, create separate lines for each receipt. For instance, if you want 1,000 units split out equally between four months, you would enter four separate lines of 250 units each.  
  
6.  On the **Lines** FastTab, in the **Type** field for each line, select **Item**. In the **No.** field, select the item.  
  
7.  In the **Quantity** field for each line, enter the amount to be ordered for this line.  
  
     The **Qty. to Receive** field is automatically filled in to indicate the quantity that the purchase orders are to be created for on the respective receipt dates.  
  
8.  In the **Expected Receipt Date** field for each line, enter the date on which this item must be received.  
  
### To create a purchase order from a blanket purchase order  
  
1.  To create an order for any of the lines, remove the quantity in the **Qty. to Receive** field on all the lines that you do not want to receive at this time.  
  
2.  When you are ready to create orders, on the **Actions** tab, in the **General** group, choose **Make Order**. Choose the **Yes** button. A message appears that states that the blanket order has been assigned an order number. Note that the blanket order has not been deleted.  
  
3.  Choose the **OK** button.  
  
4.  To see the results of the previous steps, on the **Lines** toolbar, on the **Lines** menu, select **Unposted Lines**, and then choose **Orders**.  
  
5.  In the **Purchase Lines** window, select the appropriate purchase order. On the **Home** tab, in the **Process** group, choose **Show Document**.  
  
### Converted Blanket Order Details  
  
-   After the blanket order is converted into a purchase order, the purchase order contains all the lines from the blanket order. The quantities for the lines where the quantity in the **Qty. to Receive**  field was deleted appear but with blank **Quantity**  fields. You may choose to leave, edit, or delete the lines.  
  
-   The purchase order line quantity must not exceed the quantity of the associated blanket order line. Otherwise, you cannot post the purchase order.  
  
    -   When the purchase order is posted as received or invoiced, ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> updates the **Quantity Received** and **Quantity Invoiced** fields on the related blanket order.  
  
    -   The blanket order number and line number are recorded as properties of the purchase lines when it is created from a blanket order.  
  
-   When purchase orders are not created directly from the blanket order but still relate to it, a link between a purchase order and a blanket order can be established by entering the associated blanket order number in the **Blanket Order No.** field on the purchase order line.  
  
-   After the purchase order has been created for the total quantity of a blanket order line, ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> ensures that other purchase orders cannot created for the same line by preventing users from entering a quantity in the **Qty. to Receive** field. If additional quantities must be added to a blanket order, the value in the **Quantity** field can be increased and additional orders can then be created.  
  
-   The invoiced blanket purchase order remains until it is deleted, either by using the delete \(Ctrl\+D\) function on individual blanket orders or by running the **Delete Invoiced Blanket Purchase Orders** batch job.  
  
### Recording Blanket Order Interactions  
  
-   If a vendor is also recorded as a contact in Sales & Marketing, and if you have specified an interaction template code for blanket purchase orders in the **Marketing Setup** window, when you print the blanket purchase order, an interaction is automatically recorded in the **Interaction Log Entry** table.  
  
## See Also  
 [How to: Convert Blanket Purchase Orders to Purchase Orders](../how-to-convert-blanket-purchase-orders-to-purchase-orders.md)   
 [How to: View the Status of Blanket Purchase Orders](../how-to-view-the-status-of-blanket-purchase-orders.md)   
 [How to: View Unposted and Posted Blanket Purchase Order Lines](../how-to-view-unposted-and-posted-blanket-purchase-order-lines.md)