---
title: Post Purchase Documents
description: Learn about the different ways to post purchase documents, and how to update posted documents.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.reviewer: edupont
ms.search.form: 
ms.date: 08/08/2022
ms.author: edupont

---
# Posting Purchases

On a purchase document, you can choose between the following posting actions:

* **Post**
* **Preview Posting**
* **Post and Print**
* **Test Report**
* **Post Batch**

When a purchase document is posted, the vendor's account, the general ledger (G/L), the item ledger entries, and the resource ledger entries are updated.

For each purchase document, a purchase entry is created in the **G/L Entry** table. An entry is also created in the vendor's account in the **Vendor Ledger Entry** table and a G/L entry is created in the relevant payables account. In addition, posting the purchase may result in a value-added tax (VAT) entry and a G/L entry for the discount amount. Whether an entry for the discount is posted depends on the contents of the **Discount Posting** field on the **Purchases & Payables Setup** page.

For each purchase line, as applicable, entries are created in the:

* **Item Ledger Entry** table if the purchase line is of the **Item** type.
* **G/L Entry** table if the purchase line is of the **G/L Account** type.
* **Resource Ledger Entry** table if the purchase line is of the **Resource** type.

In addition, purchase documents are always recorded in the **Purch. Recpt. Header** and **Purch. Inv. Header** tables.

Before you start to post, you can print a test report that contains all the information in the purchase order and indicates any errors there. To print the report, choose **Posting**, and then choose **Test Report**.

> [!IMPORTANT]  
> When you post a purchase order for items, you can create both a receipt and an invoice. These can be done simultaneously or independently. You can also create a partial receipt and a partial invoice by completing the **Qty. to Receive** and **Qty. to Invoice** fields on the individual purchase order lines before you post. Note that you cannot create a purchase invoice for products or services that have not been received. That is, before you can invoice, you must have recorded a receipt, or you must choose to receive and invoice at the same time.
><!--So, in the last sentence above it says one thing, then in the first sentence below it seems to say another. Is that correct?-->
> To post a purchase invoice without recording a purchase receipt in [!INCLUDE[prod_short](includes/prod_short.md)], create the document on the **Purchase Invoices** page. Learn more at [Record Purchases with Purchase Invoices](purchasing-how-record-purchases.md).

You can either post or post and print. If you choose to post and print, a report is printed when the order is posted. You can also choose the **Post Batch** action to post several orders at the same time. Learn more at [Post Multiple Documents at the Same Time](ui-batch-posting.md).

## Viewing ledger entries

When the posting is completed, the posted purchase lines are removed from the order. A message tells you when the posting is completed. After this, you'll be able to see the posted entries in various pages, including the **Vendor Ledger Entries**, **G/L Entries**, **Item Ledger Entries**, **Resource Ledger Entries**, **Purchase Receipts**, and **Posted Purchase Invoices** pages.

In most cases, you can open ledger entries from the affected card or document. For example, on the **Vendor Card** page, choose the **Entries** action.

## Editing ledger entries

You can edit certain fields on posted purchase documents, such as the **Payment Reference** field. Learn more at [Edit Posted Documents](across-edit-posted-document.md). For more critical fields that affect the auditing trail, you must reverse or undo posting. Learn more at [Reverse Journal Postings and Undo Receipts/Shipments](finance-how-reverse-journal-posting.md).

## See related training at [Microsoft Learn](/learn/modules/receive-invoice-dynamics-d365-business-central/index).

## See also

[Edit Posted Documents](across-edit-posted-document.md)  
[Post Multiple Documents at the Same Time](ui-batch-posting.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Posting Documents and Journals](ui-post-documents-journals.md)  
[Correct or Cancel Unpaid Purchase Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md)  
[Finding Pages and Information with Tell Me](ui-search.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
