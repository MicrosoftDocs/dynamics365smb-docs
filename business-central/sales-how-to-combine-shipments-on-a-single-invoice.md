---
title: How to combine shipments on a single invoice
description: Use the Combine Shipments feature to invoice multiple posted shipments for the same customer and currency on a single sales or service invoice.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: v-soumramani
ms.topic: how-to
ms.search.keywords: combine shipments, single invoice
ms.date: 08/07/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Combine shipments on a single invoice

You can manually or automatically combine shipments from sales or service orders in a single sales or service invoice.  

Before you can create a combined shipment, you must post, but not invoice, more than one sales or service shipments for the same customer in the same currency.

> [!NOTE]
> The procedures in this article describe how to combine shipments in a sales invoice. The steps are the same for service invoices. Just replace the word "sales" with "service."

## Manually combine shipments on a single invoice

1. Choose the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Invoices**, and then choose the related link.  
1. Choose the **New** action, and then fill in the fields as necessary. Learn more in [Invoice Sales](sales-how-invoice-sales.md) or [Create service invoices or credit memos](service-how-create-invoices.md).
1. In the **Sell-to Customer No.** field, enter the customer to invoice for the shipped items.  
1. On the **Lines** FastTab, choose the **Get Shipment Lines** action.  
1. Select the shipment line that you want to include in the invoice:  

   - To insert all lines, select all lines and choose the **OK** button.  
   - To insert specific lines, select the lines and choose the **OK** button. You can use the Ctrl key to select multiple nonsequential lines.  

   If an incorrect shipment line was selected or you want to start over, you can delete the lines on the invoice and rerun the **Get Shipment Lines** action.  
1. To post the invoice, choose the **Post** action.  

> [!TIP]  
> If you shipped orders where the **Sell-to Customer No.** is different from the **Bill-to Customer No.**, those lines don't display in the **Get Shipment Lines** report. Use personalization to add the **Sell-to Customer** field to the page and remove the filter. Now you can add shipment lines to the invoice regardless of the value in the **Sell-to Customer No.** field, as long as the **Bill-to Customer No.** field on the shipment lines matches the value on the sales invoice.  

## Automatically combine shipments on a single invoice

[!INCLUDE[prod_short](includes/prod_short.md)] selects only sales orders where **Combine Shipments** is chosen.

1. Choose the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Combine Shipments**, and then choose the related link. The batch job request page opens.  
1. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
1. Choose the **Post Invoices** checkbox.  
1. Choose the **OK** button.  

> [!NOTE]  
> You must manually post the invoices if the **Post Invoices** checkbox wasn't selected on the batch job.  

## Remove open sales orders after combined shipment posting

When you combine and post shipments on an invoice, [!INCLUDE [prod_short](includes/prod_short.md)] creates a posted sales or service invoice for the invoiced lines. The **Quantity Invoiced** field on the original order updates based on the invoiced quantity. The orders from which you post the shipments still exist, even if they're fully shipped and invoiced.

1. Choose the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Delete Invoiced Sales Orders**, and then select the link.  
1. Specify in the **No.** filter field which sales orders to delete.  
1. Choose the **OK** button.  

Alternatively, delete individual sales or service orders manually.  

Repeat steps 1 through 3 for other affected documents, such as blanket sales orders.

## Related information

- [Sales](sales-manage-sales.md)  
- [Service Management](service-service.md)  
- [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
