---
title: "Swiss Purchase Documents and Sales Documents"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "sales documents, defined (Swiss)"
  - "purchase documents, defined (Swiss)"
ms.assetid: 47ef05d6-a0be-49ca-9851-62bea37f2613
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "de-ch"
  - "fr-ch"
---
# Swiss Purchase Documents and Sales Documents
[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] includes Swiss enhancements to purchase documents and sales documents. This includes the following:  
  
-   Enhanced posting descriptions for general ledger entries, customer ledger entries, and vendor ledger entries. For more information, see the [\($ T\_17 G\/L Entry $\)](assetId:///2b5b8281-fbfa-4b7f-a154-a9ec61afadfe) table, the [\($ T\_21 Cust. Ledger Entry $\)](../Topic/\($%20T_21%20Cust.%20Ledger%20Entry%20$\).md) table, and the [\($ T\_25 Vendor Ledger Entry $\)](../Topic/\($%20T_25%20Vendor%20Ledger%20Entry%20$\).md) table.  
  
-   The ability to have subtitles, subtotals, and begin and end totals in sales quotes and sales orders.  
  
-   The ability to round invoice totals in payment journal lines if there is a payment discount.  
  
-   The ability to turn off printing of additional shipment documents for purchase invoices and sales invoices.  
  
## Purchase Documents and Sales Documents  
 The posting descriptions posted to ledger entries for purchase orders and sales orders display the name of the vendors or customers, and the invoices or credit memo numbers. For example, **Inv. 103020\/ The Cannon Group PLC** is a posting description. This posting description displays a number that is relevant for financial transactions, which helps to analyze the transactions more easily.  
  
### Sales Quotes and Sales Orders  
 When a sales quote or sales order is created, if the type of the sales quote line or sales order line is **Begin Total** or **End Total**, then the items listed on the lines are marked as physical items or as service items. The items then have subheadings for each item group, and a subtotal is created for each item group.  
  
 The items are divided based on the system generated values displayed in the **Level** field.  
  
 You can specify an item as a variant in the sales quote line. This allows you to list the alternative items without including the price in the quote. You can also refer to specific parts of a sales quote or sales order based on the value displayed in the **Position** field of the sales quote line or the sales order line. For more information, see the [\($ T\_37 Sales Line $\)](../Topic/\($%20T_37%20Sales%20Line%20$\).md) table.  
  
### Purchase Invoices and Sales Invoices with Payment Discounts  
 For purchase invoices and sales invoices, the invoice amount is reduced by the discount amount, and then rounded. The invoice total is also rounded if there is a discount. For more information, see the [\($ T\_98 General Ledger Setup $\)](assetId:///199e09dc-fe90-4792-be3e-ad395447dfd6) table.  
  
### Shipment Documents  
 In the **Sales & Receivables Setup** window, the **Shipment on Ship and Invoice** field is used to turn off printing of additional shipment documents for purchase invoices and sales invoices. When you post an order, a posted shipment and a posted invoice are automatically created. If the printed invoice is also used as a shipment document, additional shipment documentation does not need to be printed. You can turn off printing of additional shipment documents for purchase invoices and sales invoices by clearing the **Shipment on Ship and Invoice** field in the **Sales & Receivables Setup** window. For more information, see the [\($ T\_311 Sales & Receivables Setup $\)](../Topic/\($%20T_311%20Sales%20&%20Receivables%20Setup%20$\).md) table.  
  
## See Also  
 [How to: Set Up Automatic Archiving of Documents in Switzerland](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-set-up-automatic-archiving-of-documents-in-switzerland.md)   
 [How to: Import Swiss Post Codes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-import-swiss-post-codes.md)   
 [How to: Print an Inventory Picking List from a Sales Order](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-print-an-inventory-picking-list-from-a-sales-order.md)   
 [How to: Print Sales and Purchase Orders During Batch Posting](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/how-to-print-sales-and-purchase-orders-during-batch-posting.md)   
 [\($ T\_17 G\/L Entry $\)](assetId:///2b5b8281-fbfa-4b7f-a154-a9ec61afadfe)   
 [\($ T\_21 Cust. Ledger Entry $\)](../Topic/\($%20T_21%20Cust.%20Ledger%20Entry%20$\).md)   
 [\($ T\_25 Vendor Ledger Entry $\)](../Topic/\($%20T_25%20Vendor%20Ledger%20Entry%20$\).md)   
 [\($ T\_37 Sales Line $\)](../Topic/\($%20T_37%20Sales%20Line%20$\).md)   
 [\($ N\_42 Sales Order $\)](../Topic/\($%20N_42%20Sales%20Order%20$\).md)   
 [\($ T\_113 Sales Invoice Line $\)](../Topic/\($%20T_113%20Sales%20Invoice%20Line%20$\).md)   
 [\($ N\_41 Sales Quote $\)](../Topic/\($%20N_41%20Sales%20Quote%20$\).md)   
 [\($ T\_39 Purchase Line $\)](../Topic/\($%20T_39%20Purchase%20Line%20$\).md)   
 [\($ T\_123 Purch. Inv. Line $\)](../Topic/\($%20T_123%20Purch.%20Inv.%20Line%20$\).md)   
 [\($ T\_311 Sales & Receivables Setup $\)](../Topic/\($%20T_311%20Sales%20&%20Receivables%20Setup%20$\).md)   
 [\($ T\_98 General Ledger Setup $\)](assetId:///199e09dc-fe90-4792-be3e-ad395447dfd6)   
 [Switzerland Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/switzerland-local-functionality.md)