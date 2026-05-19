---
title: Posting sales documents
description: Learn about the different posting functions to post sales documents, and how you can update posted documents.
author: brentholtorf
ms.reviewer: bholtorf
ms.author: bholtorf
ms.topic: concept-article
ms.search.form: 130, 142, 1350
ms.date: 03/09/2026
ms.custom: bap-template
---
# Posting sales

Under the **Posting** menu in a sales document, you can choose between the following posting actions:

* **Post**
* **Post and New**
* **Post and Send**
* **Preview Posting**
* **Post Batch**
* **Test Report**

> [!NOTE]
> For sales orders, you can also access options related to the prepayments. To learn more, go to [Invoicing Prepayments](finance-invoice-prepayments.md).

After you complete all the lines and enter all the information on the sales order, you can post it to create a shipment and an invoice.

When a sales order is posted, the customer's account, the general ledger, and the item ledger entries are updated.

For each sales order, a sales entry is created in the **G/L Entry** table. An entry is also created in the customer's account in the **Cust. Ledger Entry** table and a general ledger entry is created in the relevant receivables account. In addition, posting the order might result in a VAT entry and a general ledger entry for the discount amount. Whether an entry for the discount is posted depends on the contents of the **Discount Posting** field on the **Sales & Receivables Setup** page.

For each sales order line, an item ledger entry is created in the **Item Ledger Entry** table (if the sales lines contain item numbers) or a general ledger entry is created in the **G/L Entry** table (if the sales lines contain a general ledger account). Also, sales orders are always recorded in the **Sales Shipment Header** and **Sales Invoice Header** tables.

[!INCLUDE [order-ship-invoice](includes/order-ship-invoice.md)]

You can either post, or post and send. If you choose to post and send, a PDF file is generated that you can then send. You can also choose the **Post Batch** function, which lets you post several orders at the same time. To learn more, go to [Post Multiple Documents at the Same Time](ui-batch-posting.md).

## Review ledger entries

When posting is complete, the posted sales lines are removed from the order. A message tells you when the posting is completed. Afterward, you can access the posted entries in the various pages that contain posted entries, such as the **Cust. Ledger Entries**, **G/L Entries**, **Item Ledger Entries**, **Posted Sales Shipments**, and **Posted Sales Invoices** pages.  

In most cases, you can open ledger entries from the affected card or document. For example, on the **Customer Card** page, choose the **Ledger Entries** action.

## Edit ledger entries

You can edit certain fields on posted sales documents, such as the **Package Tracking No.** field. To learn more, go to [Edit Posted Documents](across-edit-posted-document.md). For more critical fields that affect the auditing trail, you must reverse or undo posting. To learn more, go to [Reverse Journal Postings and Undo Receipts/Shipments](finance-how-reverse-journal-posting.md).

## Send posted sales invoices by email

Sales shipments are important documents for customers, and often need to be delivered promptly and accurately. By sending posted shipments and invoices by email, you reduce reliance on manual printing and mailing. This streamlined process improves communication with customers, and supports scenarios where you want to share shipment or invoice details with different contacts than the ones specified on the invoices.

The ability so send posted sales shipments and posted sales invoices by email compliments the **Print** option. There are several options:

- **Send by Email**: Send the posted document by email to the customer.
- **Send**: Use the standard sending options that are available for other posted documents.
- **Attach as PDF**: Generate and add the generated document in PDF format to the **Attachment** part.

The **Attachment** part allows you to store and manage printed document versions for future reference, and is now also available on the following pages:

 - **Posted Return Receipt** (page 6660)
 - **Posted Return Receipts** (page 6662)
 - **Posted Sales Shipment** (page 130)
 - **Posted Sales Shipments** (page 142)

## Related information

[Sales](sales-manage-sales.md)  
[Post Multiple Documents at the Same Time](ui-batch-posting.md)  
[Edit Posted Documents](across-edit-posted-document.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Correct or Cancel Unpaid Sales Invoices](sales-how-correct-cancel-sales-invoice.md)  
[Finding Pages and Information with Tell Me](ui-search.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]  
