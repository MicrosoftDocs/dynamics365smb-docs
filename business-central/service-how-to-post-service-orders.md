---
title: How to post service orders
description: After creating and updating a service order with all required details, you can proceed to post it.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: v-soumramani
ms.topic: how-to
ms.search.keywords: post service order, consumption, post consumption, undo consumption, service shipment, service lines
ms.date: 10/03/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Post service orders and credit memos

After you create a service order, when you're ready you can post it. The order must contain at least one service item line and one service line. If the order has more than one service line, all lines post at the same time.  

If you have a large number of service orders, you can save time by using a batch job to post them. You can run the batch job from any service order.

> [!Tip]
> Before you post a service document, it's a good idea to use the **Test Report** action to to check for errors or missing information. If there are errors, you must correct the problem. You can print a new test report to verify the fix, and then post the document.

## Post a service order

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Orders**, and then choose the related link.  
2. Open the service order.  
3. On the **Service Order** page, choose one of the following actions.  

    |**Action**|**Result**|  
    |------------------|----------------|  
    |**Test Report** | Checks all parts of the document and presents the result in a report. If the report indicates any errors or a lack of information, you must correct the problem. You can then print a new test report.|  
    |**Post** | Posts the order without printing a shipment or an invoice.|  
    |**Post and Print** | Posts the order and prints a shipment (if you ship the order without invoicing it) or an invoice (if you invoice the order).|  
    |**Post Batch** | Posts multiple service orders at one time once.|  

4. For the **Post** action, there are several options that control what happens.  

    |**Posting Option**|**Result**|  
    |------------------------|----------------|  
    |**Ship** | Posts shipment of the items.|  
    |**Invoice** | Invoices items that have already been shipped.|  
    |**Ship and Invoice** | Invoices and ships the items.|  
    |**Ship and Consume** | Posts shipment and consumption on the order. It updates the relevant quantities on the service lines of the order and on the previously posted service shipment document.|  

You can post consumption only if the line contains a quantity that shipped but isn't invoiced or consumed.  

When you post the order, [!INCLUDE [prod_short](includes/prod_short.md)] creates the corresponding ledger entries and posted documents and updates the service order.  

## Batch post service orders

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Orders**, and then choose the related link.  
2. Choose the **Post Batch** action.  
3. You can set a filter to select specific service order numbers or an interval of order numbers for the batch job to process.  
4. Choose **OK** to start the batch job.  

## Post a service credit memo  

After you create a service credit memo, you can post it when you're ready. If there are errors or a lack of information on the credit memo while posting, an error message displays and stops the process.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Credit Memos**, and then choose the related link.  
2. Create a new service credit memo. Choose the **New** action.  
3. Fill in the necessary fields.  
4. Choose the **Post** action. If you want to print the credit memo at the same time as your post, choose the **Post and Print** action instead.  
5. To test credit memos before you post them, choose **Test Report**. When you run the report, [!INCLUDE [prod_short](includes/prod_short.md)] verifies the posting dates in the document.  
6. To post several service credit memos at the same time, run the **Batch Post Service Cr. Memos** batch job. Using the batch job is helpful when you have to post a lot of credit memos.  

> [!NOTE]  
> It's important to enter all the necessary information on the credit memos before you batch post them. Otherwise, it's possible that they aren't posted. When the batch job finishes, a message shows how many of the service credit memos it posted.  

## Post consumption from a service order  

The following procedure describes how to post the items, resource hours, and costs used for a specific service operation for which you won't charge your customer. You can post consumed items, hours, or costs only for a posted shipment that has no posted invoices or consumption.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Orders**, and then choose the related link.  
2. Open the service order to post consumption for.  
3. Choose the service item. Choose the **Service Lines** action.  
4. Find the required entries, and specify the quantities for which you'll post consumption in the **Qty. to Consume** field. The quantity can't be larger than the quantity already shipped and the quantity remaining but not invoiced after partial invoicing of this shipment.  

    > [!NOTE]  
    > To register consumption for a project, fill in the **Project No.**, **Project Task No.**, and the **Project Line Type** fields on the service line.  

5. Choose the lines to post, and then choose the **Post** action. On the page that opens, select **Ship and Consume**.  

The service is posted as either partially or fully consumed, depending on the value in the **Qty. to Consume** field, and the relevant ledger entries are created. Also, previously posted service shipment documents are updated chronologically with the consumed quantities. The relevant quantities are updated on the service lines of the order.  

## Post shipments from service orders  

After you specify the details of a service, you can adjust and post the quantities of items used, time spent, and costs incurred. As a result, [!INCLUDE[prod_short](includes/prod_short.md)] makes the necessary changes to reflect the new state of your inventory and current status of the specific order processing.  

The following procedure shows how to post shipment of service line items in locations that aren't set up to require warehouse handling.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Order**, and then choose the related link.
2. Open the service order, and then choose the **Service Lines** action.  
3. On the **Service Lines** page, find the required entries and then specify the quantity to post in the **Qty. to Ship** field.  

   > [!NOTE]  
   > The quantity to ship value depends on whether you want to fully or partially post the shipment. If you choose to ship fully, the value in the **Qty. to Ship** field must be equal to the value in the **Quantity** field. When you post a partial shipment, you must specify the quantity you want to ship initially. If you already shipped part of the service on the order, make a note of the value in the **Quantity Shipped** field. The maximum quantity you can enter in the **Quantity to Ship** field is the number of units that haven't shipped.  

4. Choose the **Post** action, and then choose **Ship**.

[!INCLUDE[prod_short](includes/prod_short.md)] creates ledger entries (in the warranty ledger, item ledger, service ledger, or G/L), produces the posted service shipment document, and updates the relevant fields on the service lines of the service order.  

If the location is set up to require warehouse handling, shipping and moving service line items works in the same way as they do for other source documents. The only difference is that service line items can be consumed either externally or internally, and therefore require two different release functions. Learn more in [Picking Items for Warehouse Shipments] (warehouse-how-to-pick-items-for-warehouse-shipment.md) for information about shipping service line items in advanced warehouse configurations.

## Combine shipments from multiple service orders into a single service invoice

If needed, you can gather posted shipments that you haven't invoiced in a single invoice. For example, combining shipments can reduce the overall number of invoices to process, which can lower administrative costs and save time for your bookkeeping team. Learn more in [Combine shipments on a single invoice](sales-how-to-combine-shipments-on-a-single-invoice.md).

## Undo posted consumption  

You can cancel the consumption on the service orders. For example, because it was posted by mistake.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Posted Service Shipments**, and then choose the related link.  
2. Open the posted service shipment for which the erroneous consumption was posted.  
3. Choose the **Service Shipment Lines** action.  
4. Choose the lines that contain the incorrect consumption, and then choose the **Undo Consumption** action.  

 A balancing service shipment line is inserted with negative values in the quantity fields for the selected lines.  
  
> [!NOTE]  
> You can't undo service consumption if:
>
> * The service order has been closed.  
> * It was posted to a project, so there are project ledger entries linked to it.  

## Post service lines  

If you have to work on a service order for a considerable time without posting it, you might want to post some of the service lines linked to it as a way, for example, of keeping your inventory updated. You can post by specifying the relevant quantities on the lines to be posted. You might choose to post the lines one by one or by selecting several lines at a time.  

The following procedure describes shipment posting directly from a service order in locations without warehouse handling setup. If the location is set up to require warehouse handling, then shipment posting happens in a different warehouse document, depending on the location setup.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Orders**, and then choose the related link.  
2. Open the service order, and then choose the **Service Lines** action.  
3. On the lines you're going to post, fill in the **Qty. to Ship**, **Qty. to Invoice**, and **Qty. to Consume** fields, depending on how you post the lines.  
4. Choose the **Post** action.

## Related information

[Posting in Service Management](service-service-posting.md)  
[Create a Service Order](service-how-to-create-service-orders.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
