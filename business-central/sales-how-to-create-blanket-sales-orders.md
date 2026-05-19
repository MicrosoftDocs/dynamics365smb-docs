---
title: Work with blanket sales orders or purchase orders
description: Use blanket orders when a customer agrees to buy large quantities that you deliver in small shipments over a period of time.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 507, 509, 6620, 6622, 6623, 9303, 9310
ms.date: 04/07/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Work with blanket sales orders or blanket purchase orders

Blanket sales orders and blanket purchase orders represent a framework for a long-term agreement between you and your customer or vendor. This article describes the processes for the sales blanket order side, but the steps are the same for purchasing.

Typically, you use a blanket order when a customer buys a large quantity that you deliver in small shipments over a period of time. Blanket orders often cover only one item with predetermined delivery dates. The main reason for using a blanket order rather than a sales order is that quantities entered on a blanket order don't affect item availability. You can use them as a worksheet for monitoring, forecasting, and planning.

On the blanket order, each separate shipment can be set up as an order line, which can then be converted into a sales order at the time of shipping.

## To create a blanket sales order

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Blanket Sales Orders**, and then choose the related link.  
2. Choose the **New** action.  
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Leave the **Order Date** field blank. When the separate sales orders are created from the blanket order, the order date of the sales order is set to equal the actual work date.
5. On the **Lines** FastTab, create separate lines for each shipment. For example, if your customer wants 1,000 units split equally over four weeks, you would enter four separate lines of 250 units each.  

## To create a sales order from a blanket sales order  

1. To create an order for any of the lines in the blanket sales order, remove the quantity in the **Qty. to Ship** field on all the lines that you don't wish to ship at this time.  
2. When you're ready to create orders, choose the **Make Order** action, and then choose **Yes**. A message informs you that an order number is assigned to the blanket order. The blanket order isn't deleted.  
3. Choose the **OK** button.  
4. To see the results of the preceding steps, choose the **Line** action, choose the **Unposted Lines** action, and then choose the **Orders** action.  
5. On the **Sales Lines** page, select the appropriate sales order, choose the **Line** action, and then choose the **Show Document** action.  

The following information applies to sales orders after they're created from blanket sales orders:  

- After the blanket order is converted into a sales order, the sales order contains all the lines from the blanket order. The lines where the quantity in the **Qty. to Ship** field was deleted show blank **Quantity** fields. You can choose to leave, edit, or delete the lines.  
- It's important to remember that the sales order line quantity must not exceed the quantity of the associated blanket order line. Otherwise, you can't post the sales order.  
- When the sales order is posted as shipped and/or invoiced, the **Quantity Shipped** and **Quantity Invoiced** fields are updated on the related blanket order.  
- The blanket order number and line number are recorded as properties of the sales lines when created from a blanket order.  
- When sales orders aren't created directly from the blanket order but still relate to it, a link between a sales order and a blanket order can be established by entering the associated blanket order number in the **Blanket Order No.** field on the sales order line.  
- After the sales order is created for the total quantity of a blanket order line, no other sales order can be created for the same line. Users are prevented from entering a quantity in the **Qty. to Ship** field. If, however, extra quantities need to be added to a blanket order, you can increase the value in the **Quantity** field and more orders can then be created.  
- The invoiced blanket sales order remains in the system until you delete it, either by deleting individual blanket orders or by running the **Delete Invoiced Blanket Sales Orders** batch job.  
- If a customer is also recorded as a contact in the Marketing application area, and if you specified an interaction template code for blanket sales order on the **Marketing Setup** page, an interaction is recorded in the Interaction Log Entry table when you select **Print** to print the blanket sales order.

## To view the status of a blanket sales order

You can review the status of a blanket sales order on the **Sales Blanket Order Statistics** page. This review might be relevant when you start to invoice the order that is created from the blanket sales order.  

1.  [!INCLUDE[open-search](includes/open-search.md)], enter **Blanket Sales Orders**, and then choose the related link.  
2.  Select a blanket sales order, and then choose the **Statistics** action.  
3.  On the **Sales Blanket Order Statistics** page, on the **General** FastTab, you can see summary information about the entire order based on the total quantity in the various **Quantity fields** on the blanket sales order lines.  

- On the **Invoicing** FastTab, you can see summary information based on the total quantity in the **Qty. to Invoice** fields on the sales blanket order lines.  
- On the **Shipping** FastTab, you can see summary information based on the total quantity in the **Qty. to Receive** fields on the sales blanket order lines.  
- On the **Prepayment** FastTab, you can see summary information about any prepaid amounts.  
- On the **Vendor** FastTab, you can see certain basic information about the vendor.

## To view unposted and posted blanket sales order lines

The link between the blanket sales order and the originating sales order, and any other sales document, is kept after posting.  

1. [!INCLUDE[open-search](includes/open-search.md)] enter **Blanket Sales Orders**, and then choose the related link.
2. Open the blanket sales order you want to view.
3. To view unposted entries, select the line in question, choose the **Line** action, and then choose the **Unposted Lines** action. Choose one of the following options.  

|Option|Description|
|--|--|
|**Orders**|Specifies open orders associated with the selected line.|
|**Invoices**|Specifies open invoices that were associated with the selected line. Open invoices are manually associated with a blanket order by entering the blanket order number on the sales invoice line.|
|**Return Orders**|Specifies open return orders that were associated with the selected line.|
|**Credit Memos**|Specifies open credit memos that were associated with the selected line.|

4. To view posted entries, select the line in question, choose the **Line** action, and then choose the **Posted Lines** action. Choose one of the following options.  

|Option|Description|
|---|----|
|**Shipments**|Posted shipments associated with the selected line.|
|**Invoices**|Posted invoices associated with the selected line.|
|**Return Receipts**|Posted return receipts that were associated with the selected line.|
|**Credit Memos**|Posted credit memos that were associated with the selected line.|

5. On the **Sales Lines** page, choose the **Show Document** action to view the entry.

## Related information

[Sales](sales-manage-sales.md)  
[Create Blanket Assembly Orders](assembly-how-to-create-blanket-assembly-orders.md)  
[Setting Up Sales](sales-setup-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
