---
title: Understanding How To Post Purchase Documents | Microsoft Docs
description: Learn about the different posting functions to post purchase documents, and how you can update posted documents.
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
# Posting Purchases
On a purchase document, you can choose between the following posting actions:

* **Post**
* **Preview Posting**
* **Post and Print**
* **Test Report**
* **Post Batch**

When a purchase document is posted, the vendor's account, the general ledger, the item ledger entries, and the resource ledger entries  are updated.

For each purchase document, a purchase entry is created in the **G/L Entry** table. An entry is also created in the vendor's account in the **Vendor Ledger Entry** table and a G/L entry is created in the relevant payables account. In addition, posting the purchase may result in a VAT entry and a G/L entry for the discount amount. Whether an entry for the discount is posted depends on the contents of the **Discount Posting** field on the **Purchases & Payables Setup** page.

For each purchase line, the following entries will be created:
- An entry in the **Item Ledger Entry** table if the purchase line is of type **Item**.
- An entry in the **G/L Entry** table if the purchase lines is of type **G/L Account**
- An entry in the **Resource Ledger Entry** table if the purchase line is of type **Resource**.

In addition, purchase documents are always recorded in the **Purch. Recpt. Header** and **Purch. Inv. Header** tables.

Before you start to post, you can print a test report that contains all the information in the purchase order and indicates any errors there. To print the report, choose **Posting**, and then choose **Test Report**.

> [!IMPORTANT]  
>   When you post a purchase order for items, you can create both a receipt and an invoice. These can be done simultaneously or independently. You can also create a partial receipt and a partial invoice by completing the **Qty. to Receive** and **Qty. to Invoice** fields on the individual purchase order lines before you post. Note that you cannot create an invoice for something that has not been received. That is, before you can invoice, you must have recorded a receipt, or you must choose to receive and invoice at the same time.

You can either post or post and print. If you choose to post and print, a report is printed when the order is posted. You can also choose the **Post Batch** function, which lets you post several orders at the same time. For more information, see [Post Multiple Documents at the Same Time](ui-batch-posting.md).

## Viewing Ledger Entries
When the posting is completed, the posted purchase lines are removed from the order. A message tells you when the posting is completed. After this, you will be able to see the posted entries in the various pages that contain posted entries, such as the **Vendor Ledger Entries**, **G/L Entries**, **Item Ledger Entries**, **resource ledger entries**, **Purchase Receipts**, and **Posted Purchase Invoices** pages.

In most cases, you can open ledger entries from the affected card or document. For example, on the **Vendor Card** page, choose the **Entries** action.

## Editing Ledger Entries
You can edit certain fields on posted purchase documents, such as the **Payment Reference** field. For more information, see [Edit Posted Documents](across-edit-posted-document.md). For more critical fields that affect the auditing trail, you must reverse or undo posting. For more information, see [Reverse Journal Postings and Undo Receipts/Shipments](finance-how-reverse-journal-posting.md).

## See Related Training at [Microsoft Learn](/learn/modules/receive-invoice-dynamics-d365-business-central/index)

## See Also
[Edit Posted Documents](across-edit-posted-document.md)  
[Post Multiple Documents at the Same Time](ui-batch-posting.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Posting Documents and Journals](ui-post-documents-journals.md)  
[Correct or Cancel Unpaid Purchase Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md)  
[Finding Pages and Information with Tell Me](ui-search.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
