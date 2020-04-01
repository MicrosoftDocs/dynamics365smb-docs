---
title: Posting Sales Documents | Microsoft Docs
description: Learn about the different posting functions to post sales documents, and how you can update posted documents.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.reviewer: edupont
ms.date: 04/01/2020
ms.author: sgroespe

---
# Posting Sales
Under the **Posting** menu in a sales document, you can choose between the following posting functions:

* **Post**
* **Post and New**
* **Post and Send**
* **Preview Posting**
* **Draft Invoice**
* **Pro Forma Invoice**
* **Test Report**

When you have completed all the lines and entered all the information on the sales order, you can post it. This creates a shipment and an invoice.

When a sales order is posted, the customer's account, the general ledger, and the item ledger entries are updated.

For each sales order, a sales entry is created in the **G/L Entry** table. An entry is also created in the customer's account in the **Cust. Ledger Entry** table and a general ledger entry is created in the relevant receivables account. In addition, posting the order may result in a VAT entry and a general ledger entry for the discount amount. Whether an entry for the discount is posted depends on the contents of the **Discount Posting** field on the **Sales & Receivables Setup** page.

For each sales order line, an item ledger entry will be created in the **Item Ledger Entry** table (if the sales lines contain item numbers) or a general ledger entry will be created in the **G/L Entry** table (if the sales lines contain a general ledger account). In addition to this, sales orders are always recorded in the **Sales Shipment Header** and **Sales Invoice Header** tables.

> [!IMPORTANT]  
>   When you post an order, you can create both a shipment and an invoice. These can be done at the same time or independently. You can also create a partial shipment and a partial invoice by completing the **Qty. to Ship** and **Qty. to Invoice** fields on the individual sales order lines before you post. Note that you cannot create an invoice for something that is not shipped. That is, before you can invoice, you must have recorded a shipment, or you must choose to ship and invoice at the same time.

You can either post, or post and print. If you choose to post and print, a report is printed when the order is posted. You can also choose the **Post Batch** function, which lets you post several orders at the same time. For more information, see [Post Multiple Documents at the Same Time](ui-batch-posting.md).

## Viewing Ledger Entries
When the posting is completed, the posted sales lines are removed from the order. A message tells you when the posting is completed. After this, you will be able to see the posted entries in the various pages that contain posted entries, such as the **Cust. Ledger Entries**, **G/L Entries**, **Item Ledger Entries**, **Posted Sales Shipments**, and **Posted Sales Invoices** pages.  

In most cases, you can open ledger entries from the affected card or document. For example, on the **Customer Card** page, choose the **Ledger Entries** action.

## Editing Ledger Entries
You can edit certain fields on posted purchase documents, such as the **Package Tracking No.** field. For more information, see [Edit Posted Documents](across-edit-posted-document.md). For more critical fields that affect the auditing trail, you must reverse or undo posting. For more information, see [Reverse Journal Postings and Undo Receipts/Shipments](finance-how-reverse-journal-posting.md).

## See Related Training at [Microsoft Learn](/learn/modules/ship-invoice-items-dynamics-365-business-central/index)

## See Also
[Sales](sales-manage-sales.md)  
[Post Multiple Documents at the Same Time](ui-batch-posting.md)  
[Edit Posted Documents](across-edit-posted-document.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Correct or Cancel Unpaid Sales Invoices](sales-how-correct-cancel-sales-invoice.md)  
[Finding Pages and Information with Tell Me](ui-search.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
