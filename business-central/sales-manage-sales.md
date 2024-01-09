---
title: Overview of Tasks to Manage Sales
description: Read all about how to use Business Central's services to manage your customers' sales activities with sales invoices, orders, quotes, and more.
author: brentholtorf
ms.topic: overview
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: trade, sell
ms.search.form: 253
ms.date: 09/02/2022
ms.author: bholtorf

---
# Sales

You create a sales invoice or sales order to record your agreement with a customer to sell certain products on certain delivery and payment terms.

You must use sales orders if your sales process requires you to ship parts of an order quantity, for example, because the full quantity is not available right away. If you sell items by delivering directly from your vendor to your customer, as a drop shipment, then you must also use sales orders. In all other respects, sales orders work the same way as sales invoices. With sales orders, you can also use the order promising functionality to communicate certain delivery dates to your customers.  

You can negotiate with the customer by first creating a sales quote, which you can convert to a sales invoice or sales order when you agree on the sale. After the customer has confirmed the agreement, you can send an order confirmation to record your obligation to deliver the products as agreed.

You can easily correct or cancel a posted sales invoice before it is paid. This is useful if you want to correct a typing mistake or if the customer requests a change early in the order process. If the posted sales invoice is paid, then you must create a sales credit memo or a sales return order to reverse the sale.

Good sales and marketing practices are all about how to make the best decisions at the right time. Marketing functionality in [!INCLUDE[prod_short](includes/prod_short.md)] provides a precise and timely overview of your contact information so you can serve your prospective customers more efficiently and increase customer satisfaction. Learn more at [Relationship Management](marketing-relationship-management.md).

If you use Microsoft Dynamics 365 Sales for customer engagement, you can enjoy seamless integration in the lead-to-cash process by using Business Central for backend activities such as processing orders, managing inventory, and doing your finances. Learn more at [Use Dynamics 365 Sales from Business Central](marketing-integrate-dynamicscrm.md).

In business environments where the customer must pay before products are delivered, such as in retail, you must wait for the receipt of payment before you deliver the products. In most cases, you process incoming payments some weeks after delivery by applying the payments to their related posted, unpaid sales invoices. Learn more at [Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md).

Sales documents can be sent as PDF files attached to email. The email body will contain an extract of the sales document, such as products, total amount, and a link to the PayPal site. Learn more at [Send Documents by Email](ui-how-send-documents-email.md).

For all sales processes, you can incorporate an approval workflow, for example, to require that large sales to certain customers are approved by the accounting manager. Learn more at [Use Workflows](across-use-workflows.md).

The following table describes a sequence of tasks, with links to the articles that cover them.

| To | See |
| --- | --- |
|Create a customer card for each customer you sell to.|[Register New Customers](sales-how-register-new-customers.md)|
| Create a sales quote to offer products on negotiable terms before converting the quote to a sales invoice. |[Make Sales Quotes](sales-how-make-offers.md) |
| Create a sales invoice to record your agreement with a customer to sell them certain products on certain delivery and payment terms. |[Invoice Sales](sales-how-invoice-sales.md) |
| Process a sales order that involves partial shipping or drop shipment. |[Sell Products](sales-how-sell-products.md) |
|Understand what happens when you post sales documents.|[Posting Sales](ui-post-sales.md)|
|Prepare to pick items for shipment.|[Print the Picking List](sales-how-print-picking-list.md)|
| Fulfill a sales order with multiple partial shipments. | [Process Partial Shipments](sales-how-send-partial-shipments.md) |
|Set up standard sales or purchase lines you can quickly insert on documents, for example, for recurring replenishment orders.|[Create Recurring Sales and Purchase Lines](sales-how-work-standard-lines.md)|  
| Link a sales order to a purchase order to sell a drop-shipment item to be delivered directly from your vendor to your customer. |[Make Drop Shipments](sales-how-drop-shipment.md) |
|Have a catalog item shipped from a vendor to your warehouse so you can ship the item on to your customer.|[Create Special Orders](sales-how-to-create-special-orders.md)|
| Perform an action on an unpaid posted sales invoice to automatically create a credit memo and either cancel the sales invoice or recreate it so you can make corrections. |[Correct or Cancel Unpaid Sales Invoices](sales-how-correct-cancel-sales-invoice.md) |
| Create a sales credit memo to revert a specific posted sales invoice to reflect the products the customer returns and the payment amount you will refund. |[Process Sales Returns or Cancellations](sales-how-process-sales-returns-cancellations.md) |
|Manage your customer's commitment to purchase large quantities delivered in several shipments over time.|[Work with Blanket Sales Orders](sales-how-to-create-blanket-sales-orders.md)|
|Sell assembly items not currently available by creating a linked assembly order to supply the full or partial sales order quantity.|[Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md)|
|Invoice a customer once for multiple shipments by combining the shipments on one invoice.|[Combine Shipments on a Single Invoice](sales-how-to-combine-shipments-on-a-single-invoice.md)|
|Inform your customers of order delivery dates by calculating either the capable-to-promise date or the available-to-promise date.|[Calculate Order Promising Dates](sales-how-to-calculate-order-promising-dates.md)|
|Resolve confusion when two or more records exist for the same customer.|[Merge Duplicate Records](sales-how-merge-duplicate-records.md)|

## See also

[Setting Up Sales](sales-setup-sales.md)  
[Register New Customers](sales-how-register-new-customers.md)  
[Managing Receivables](receivables-manage-receivables.md)  
[Managing Payables](payables-manage-payables.md)  
[Project Management](projects-manage-projects.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[General Business Functionality](ui-across-business-areas.md)

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
