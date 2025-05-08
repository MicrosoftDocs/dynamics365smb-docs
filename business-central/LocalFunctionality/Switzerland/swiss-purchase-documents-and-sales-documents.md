---
title: Swiss Purchase Documents and Sales Documents
description: This article describes enhancements made to the Swiss version of Business Central including special Swiss purchase document and sales document features.    
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: purchase documents, sales documents, enhancements, sales quotes, sales orders, Swiss version
ms.date: 04/30/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Swiss purchase documents and sales documents

[!INCLUDE[prod_short](../../includes/prod_short.md)] includes Swiss enhancements to purchase documents and sales documents. This includes the following features:  

- Enhanced posting descriptions for general ledger entries, customer ledger entries, and vendor ledger entries. For more information, see the G/L Entry table, the Cust. Ledger Entry table, and the Vendor Ledger Entry table.  
- The ability to have subtitles, subtotals, and begin and end totals in sales quotes and sales orders.  
- The ability to round invoice totals in payment journal lines if there's a payment discount.  
- The ability to turn off printing of additional shipment documents for purchase invoices and sales invoices.  

## Purchase documents and sales documents

The posting descriptions posted to ledger entries for purchase orders and sales orders display the name of the vendors or customers, and the invoices or credit memo numbers. For example, **Inv. 103020/ The Cannon Group PLC** is a posting description. This posting description displays a number that is relevant for financial transactions, which helps to analyze the transactions more easily.  

### Sales quotes and sales orders

When a sales quote or sales order is created, if the type of the sales quote line or sales order line is **Begin Total** or **End Total**, then the items listed on the lines are marked as physical items or as service items. The items then have subheadings for each item group, and a subtotal is created for each item group.  

The items are divided based on the system generated values displayed in the **Level** field.  

You can specify an item as a variant in the sales quote line. This allows you to list the alternative items without including the price in the quote. You can also refer to specific parts of a sales quote or sales order based on the value displayed in the **Position** field of the sales quote line or the sales order line. For more information, see the Sales Line table.  

> [!NOTE]
> This functionality is only available in [!INCLUDE[prod_short](../../includes/prod_short.md)] on-premises.

## Purchase invoices and sales invoices with payment discounts

For purchase invoices and sales invoices, the invoice amount is reduced by the discount amount, and then rounded. The invoice total is also rounded if there's a discount. For more information, see the General Ledger Setup table.  

## Shipment documents

On the **Sales & Receivables Setup** page, the **Shipment on Ship and Invoice** field is used to turn off printing of additional shipment documents for purchase invoices and sales invoices. When you post an order, a posted shipment and a posted invoice are automatically created. If the printed invoice is also used as a shipment document, additional shipment documentation doesn't need to be printed. You can turn off printing of additional shipment documents for purchase invoices and sales invoices by clearing the **Shipment on Ship and Invoice** field on the **Sales & Receivables Setup** page. For more information, see the Sales & Receivables Setup table.  

## Related information

- [Import Swiss Post Codes](how-to-import-swiss-post-codes.md)
- [Print an Inventory Picking List from a Sales Order](how-to-print-an-inventory-picking-list-from-a-sales-order.md)
- [Switzerland Local Functionality](switzerland-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
