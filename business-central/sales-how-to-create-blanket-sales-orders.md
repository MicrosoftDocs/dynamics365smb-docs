---
    title: How to Create Blanket Sales Orders | Microsoft Docs
    description: Use blanket orders when a customer has agreed to buy large quantities that are to be delivered in several smaller shipments over a certain period of time.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 09/08/2017
    ms.author: sgroespe

---
# Work with Blanket Sales Orders
A blanket sales order represents a framework for a long-term agreement between you and your customer.

A blanket order is typically made when a customer has committed to purchasing large quantities that are to be delivered in several smaller shipments over a certain period of time. Often blanket orders cover only one item with predetermined delivery dates. The main reason for using a blanket order rather than a sales order is that quantities entered on a blanket order do not affect item availability and thus can be used as a worksheet for monitoring, forecasting, and planning purposes.

On the blanket order, each separate shipment can be set up as an order line, which can then be converted into a sales order at the time of shipping.

An example of when a blanket sales order could be used is if a customer calls and places an order of 1000 units of an item and they want the items to be delivered in 250 units every week over the next month.

> [!NOTE]
> Blanket purchase orders work in a similar way as blanket sales orders. This documentation does not cover blanket purchase orders.

## To create a blanket sales order  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Blanket Sales Orders**, and then choose the related link.  
2. Choose the **New** action.  
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4.  Leave the **Order Date** field blank. When the separate sales orders are created from the blanket order, the order date of the sales order is set to equal the actual work date.
5. On the **Lines** FastTab, create separate lines for each shipment. For instance, if your customer wants 1000 units split out equally between four weeks, you would enter four separate lines of 250 units each.   

## To create a sales order from a blanket sales order  

1.  To create an order for any of the lines in the blanket assembly order, remove the quantity in the **Qty. to Ship** field on all the lines that you DO NOT wish to ship at this time.  
2.  When you are ready to create orders, choose the **Make Order**m action, and then choose **Yes**. A message appears informing you that the blanket order has been assigned an order number. Note that the blanket order has not been deleted.  
3.  Choose the **OK** button.  
4.  To see the results of the preceding steps, choose the **Line** action, choose the **Unposted Lines** action, and then choose the **Orders** action.  
5.  In the **Sales Lines** window, select the appropriate sales order, choose the **Line** action, and then choose the **Show Document** action.  

The following applies to sales orders after they have been created from blanket sales orders:  

- After the blanket order is converted into a sales order, the sales order contains all the lines from the blanket order. The lines where the quantity in the **Qty. to Ship** field was deleted appear, but with blank **Quantity** fields. You may choose to leave, edit, or delete the lines.  
- It is important to remember that the sales order line quantity must not exceed the quantity of the associated blanket order line. Otherwise, posting of the sales order will not be possible.  
- When the sales order is posted as shipped and/or invoiced, the **Quantity Shipped** and **Quantity Invoiced** fields are updated on the related blanket order.  
- The blanket order number and line number are recorded as properties of the sales lines when created from a blanket order.  
- When sales orders are not created directly from the blanket order but still relate to it, a link between a sales order and a blanket order can be established by entering the associated blanket order number in the **Blanket Order No.** field on the sales order line.  
- After the sales order has been created for the total quantity of a blanket order line, no other sales order can be created for the same line. Users are prevented from entering a quantity in the **Qty. to Ship** field. If, however, additional quantities need to be added to a blanket order, the value in the **Quantity** field can be increased and additional orders can then be created.  
- The invoiced blanket sales order remains in the system until it is deleted, either by deleting individual blanket orders or by running the **Delete Invoiced Blanket Sales Orders** batch job.  
- If a customer is also recorded as a contact in the Marketing application area, and if you have specified an interaction template code for blanket sales order in the **Marketing Setup** window, an interaction is recorded in the Interaction Log Entry table when you select **Print** to print the blanket sales order.

## To view the status of a blanket purchase order  
You can see the status of a blanket sales order in the **Purchase Blanket Order Statistics** window. This may be relevant when you start to invoice the order that is created from the blanket purchase order.  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Blanket Purchase Orders**, and then choose the related link.  
2.  Select a blanket purchase order, and then choose the **Statistics** action.  
3.  In the **Purchase Blanket Order Statistics** window, on the **General** FastTab, you can see summary information about the entire order based on the total quantity in the various **Quantity fields** on the blanket purchase order lines.  

    - On the **Invoicing** FastTab, you can see summary information based on the total quantity in the **Qty. to Invoice** fields on the purchase blanket order lines.  
    - On the **Shipping** FastTab, you can see summary information based on the total quantity in the **Qty. to Receive** fields on the purchase blanket order lines.  
    - On the **Prepayment** FastTab, you can see summary information about any prepaid amounts.  
    - On the **Vendor** FastTab, you can see certain basic information about the vendor.    

## To view unposted and posted blanket sales order lines   
The link between the blanket sales order and the originating sales order, and any other sales document, is retained after posting as a list of posted and unposted sales order invoice lines.  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon enter **Blanket Sales Orders**, and then choose the related link.
2. Open the blanket sales order you want to view.
3. To view unposted entries, select the line in question, choose the **Line** action, and then choose the **Unposted Lines** action. Choose one of the following options.  

    <table>
    <tr>
    <th>Option</th>
    <th>Description</th>
    </tr>
    <tr>
    <td>**Orders**</td>
    <td>Specifies open orders associated with the selected line.</td>
    </tr>
    <tr>
    <td>**Invoices**</td>
    <td>Specifies open invoices that have been associated with the selected line. Open invoices are manually associated with a blanket order by entering the blanket order number on the sales invoice line.</td>
    </tr>
    <tr>
    <td>**Return Orders**</td>
    <td>Specifies open return orders that have been associated with the selected line.</td>
    </tr>
    <tr>
    <td>**Credit Memos**</td>
    <td>Specifies open credit memos that have been associated with the selected line.</td>
    </tr>
    </table>
4. To view posted entries, select the line in question, choose the **Line** action, and then choose the **Posted Lines** action. Choose one of the following options.  

    <table>
    <tr>
    <th>Option</th>
    <th>Description</th>
    </tr>
    <tr>
    <td>**Shipments**</td>
    <td>Posted shipments associated with the selected line.</td>
    </tr>
    <tr>
    <td>**Invoices**</td>
    <td>Posted invoices associated with the selected line.</td>
    </tr>
    <tr>
    <td>**Return Receipts**</td>
    <td>Posted return receipts that have been associated with the selected line.</td>
    </tr>
    <tr>
    <td>**Credit Memos**</td>
    <td>Posted credit memos that have been associated with the selected line.</td>
    </tr>
    </table>
5. In the **Sales Lines** window, choose the **Show Document** action to view the entry.

## See Also
[Sales](sales-manage-sales.md)  
[Setting Up Sales](sales-setup-sales.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
