---
title: Overview of tasks to manage sales
description: Read all about how to use Business Central's services to manage your customers' sales activities with sales invoices, orders, quotes, and more.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.keywords: trade, sell
ms.search.form: 253,
ms.date: 11/11/2024
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Sales

You create a sales invoice or sales order to record your agreement with a customer to sell certain products on certain delivery and payment terms.

You must use sales orders if your sales process requires you to ship parts of an order quantity, for example, because the full quantity isn't available right away. If you sell items by delivering directly from your vendor to your customer, as a drop shipment, then you must also use sales orders. In all other respects, sales orders work the same way as sales invoices. With sales orders, you can also use the order promising functionality to communicate certain delivery dates to your customers.  

You can negotiate with the customer by first creating a sales quote, which you can convert to a sales invoice or sales order when you agree on the sale. After the customer confirms the agreement, you can send an order confirmation to record your obligation to deliver the products as agreed.

You can easily correct or cancel a posted sales invoice before the customer pays it. For example, to correct a typing mistake or if the customer requests a change early in the order process. If the posted sales invoice is paid, then you must create a sales credit memo or a sales return order to reverse the sale.

Good sales and marketing practices are all about how to make the best decisions at the right time. Marketing functionality in [!INCLUDE[prod_short](includes/prod_short.md)] provides a precise and timely overview of your contact information so you can serve your prospective customers more efficiently and increase customer satisfaction. Learn more at [Relationship Management](marketing-relationship-management.md).

If you use Microsoft Dynamics 365 Sales for customer engagement, you can enjoy seamless integration in the lead-to-cash process by using [!INCLUDE [prod_short](includes/prod_short.md)] for backend activities. For example, to process orders, manage inventory, and do your finances. Learn more at [Use Dynamics 365 Sales from Business Central](marketing-integrate-dynamicscrm.md).

In business environments where the customer must pay before products are delivered, such as in retail, you must wait for the receipt of payment before you deliver the products. In most cases, you process incoming payments some weeks after delivery by applying the payments to their related posted, unpaid sales invoices. Learn more at [Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md).

Sales documents can be sent as PDF files attached to email. The email body contains an extract of the sales document, such as products, total amount, and a link to the PayPal site. Learn more at [Send Documents by Email](ui-how-send-documents-email.md).

For all sales processes, you can incorporate an approval workflow. For example, an approval workflow can require that a manager approves large sales to certain customers. Learn more at [Use Workflows](across-use-workflows.md).

The following sections describe a sequence of tasks, with links to the articles that cover them.

## Get started with sales capabilities

Before you to sell, specify how you want to manage your company's sales processes.

|To...| Go to... |
|---|---|
| Create a customer card for each customer you sell to.|[Register New Customers](sales-how-register-new-customers.md) |
| Set up how you do sales, such as prices and discounts, customer price and discount groups, salespeople, shipment methods and agents. | [Set up sales](sales-setup-sales.md) |

## Sales analytics

This section describes the analytical tools you can use to get insights into your sales data.

| To... | Go to... |
| --- | --- |
| Get an overview of the capabilities for analyzing sales data. | [Sales analytics overview](sales-analytics-overview.md) |
| Analyze and monitor your sales KPIs with the Power BI Sales app. | [Power BI sales app](sales-powerbi-app.md) |
| Do ad-hoc analysis of sales data directly on list pages and queries. | [Ad-hoc analysis of sales data](ad-hoc-analysis-sales.md) |
| Explore built-in sales reports. | [Built-in sales reports](sales-reports.md) |

## Quote to order to sales invoice

The following table describes how to use simple sales processes.

|To...| Go to... |
|---|---|
| Create a sales quote to offer products on negotiable terms before converting the quote to a sales invoice. |[Make Sales Quotes](sales-how-make-offers.md) |
| Process a sales order (maybe with a partial shipment, or using a drop shipment.) |[Sell Products](sales-how-sell-products.md) |
| Create a sales invoice to record your agreement with a customer to sell them certain products on certain delivery and payment terms. |[Invoice Sales](sales-how-invoice-sales.md) |
|Understand what happens when you post sales documents.|[Posting Sales](ui-post-sales.md)|

If you need more complex sales processes, the following table lists articles that explain what you can do with [!INCLUDE[prod_short](includes/prod_short.md)].

|To...| Go to... |
|---|---|
| Fulfill a sales order with multiple partial shipments. | [Process Partial Shipments](sales-how-send-partial-shipments.md) |
| Set up standard sales or purchase lines you can quickly insert on documents, for example, for recurring replenishment orders.|[Create Recurring Sales and Purchase Lines](sales-how-work-standard-lines.md)|  
|Manage your customer's commitment to purchase large quantities delivered in several shipments over time.|[Work with Blanket Sales Orders](sales-how-to-create-blanket-sales-orders.md)|
|Invoice a customer once for multiple shipments by combining the shipments on one invoice.|[Combine Shipments on a Single Invoice](sales-how-to-combine-shipments-on-a-single-invoice.md)|
|Sell assembly items that aren't currently available by creating a linked assembly order. The assembly order can supply the full or partial quantity on the sales order.|[Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md)|

## Pick and ship

The following table describes how to pick items for a sales order and ship them to the customer.

| To... | Go to... |
| --- | --- |
|Prepare to pick items for shipment.|[Print the Picking List](sales-how-print-picking-list.md)|
| Link a sales order to a purchase order to sell a drop-shipment item to be delivered directly from your vendor to your customer. |[Make Drop Shipments](sales-how-drop-shipment.md) |
|Have a catalog item shipped from a vendor to your warehouse so you can ship the item on to your customer.|[Create Special Orders](sales-how-to-create-special-orders.md)|
|Inform your customers of order delivery dates by calculating either the capable-to-promise date or the available-to-promise date.|[Calculate Order Promising Dates](sales-how-to-calculate-order-promising-dates.md)|
| Learn how to track a package from a posted sales shipment. | [Track packages](sales-how-track-packages.md) |

## Canceled orders, refunds, and returns

The following table describes how to deal with canceled orders, refunds, and returns of goods.

| To... | Go to... |
| --- | --- |
| Perform an action on an unpaid posted sales invoice to automatically create a credit memo and either cancel the sales invoice or recreate it so you can make corrections. |[Correct or Cancel Unpaid Sales Invoices](sales-how-correct-cancel-sales-invoice.md) |
| Create a sales credit memo to revert a specific posted sales invoice to reflect the products the customer returns and the refund amount. |[Process Sales Returns or Cancellations](sales-how-process-sales-returns-cancellations.md) |

## Other processes in sales

The following table describes how to deal with other sales processes.

| To... | Go to... |
| --- | --- |
|Resolve confusion when two or more records exist for the same customer.|[Merge Duplicate Records](sales-how-merge-duplicate-records.md)|

## Related information

[Setting Up Sales](sales-setup-sales.md)  
[Register New Customers](sales-how-register-new-customers.md)  
[Sales analytics overview](sales-analytics-overview.md)   
[Managing Receivables](receivables-manage-receivables.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[General Business Functionality](ui-across-business-areas.md)

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
