---
    title: Swiss Purchase Documents and Sales Documents
    description: Swiss enhancements include special purchase and sales document features.    
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Swiss Purchase Documents and Sales Documents
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] includes Swiss enhancements to purchase documents and sales documents. This includes the following:  

- Enhanced posting descriptions for general ledger entries, customer ledger entries, and vendor ledger entries. For more information, see the G/L Entry table, the Cust. Ledger Entry table, and the Vendor Ledger Entry table.  
- The ability to have subtitles, subtotals, and begin and end totals in sales quotes and sales orders.  
- The ability to round invoice totals in payment journal lines if there is a payment discount.  
- The ability to turn off printing of additional shipment documents for purchase invoices and sales invoices.  

## Purchase Documents and Sales Documents  
The posting descriptions posted to ledger entries for purchase orders and sales orders display the name of the vendors or customers, and the invoices or credit memo numbers. For example, **Inv. 103020/ The Cannon Group PLC** is a posting description. This posting description displays a number that is relevant for financial transactions, which helps to analyze the transactions more easily.  

### Sales Quotes and Sales Orders  
When a sales quote or sales order is created, if the type of the sales quote line or sales order line is **Begin Total** or **End Total**, then the items listed on the lines are marked as physical items or as service items. The items then have subheadings for each item group, and a subtotal is created for each item group.  

The items are divided based on the system generated values displayed in the **Level** field.  

You can specify an item as a variant in the sales quote line. This allows you to list the alternative items without including the price in the quote. You can also refer to specific parts of a sales quote or sales order based on the value displayed in the **Position** field of the sales quote line or the sales order line. For more information, see the Sales Line table.  

## Purchase Invoices and Sales Invoices with Payment Discounts  
For purchase invoices and sales invoices, the invoice amount is reduced by the discount amount, and then rounded. The invoice total is also rounded if there is a discount. For more information, see the General Ledger Setup table.  

## Shipment Documents  
On the **Sales & Receivables Setup** page, the **Shipment on Ship and Invoice** field is used to turn off printing of additional shipment documents for purchase invoices and sales invoices. When you post an order, a posted shipment and a posted invoice are automatically created. If the printed invoice is also used as a shipment document, additional shipment documentation does not need to be printed. You can turn off printing of additional shipment documents for purchase invoices and sales invoices by clearing the **Shipment on Ship and Invoice** field on the **Sales & Receivables Setup** page. For more information, see the Sales & Receivables Setup table.  

## See Also  
 [Import Swiss Post Codes](how-to-import-swiss-post-codes.md)   
 [Print an Inventory Picking List from a Sales Order](how-to-print-an-inventory-picking-list-from-a-sales-order.md)   
 [Switzerland Local Functionality](switzerland-local-functionality.md)
