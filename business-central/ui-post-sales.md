---
title: Understanding How To Post Sales Documents | Microsoft Docs
description: Learn about the different posting functions to post sales documents.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/02/2017
ms.author: solsen

---
# Posting Sales
In the **Posting group** on a sales document, you can choose between the following posting functions:

* **Post**
* **Test Report**
* **Post and Send**
* **Post and Print**
* **Post and Email**
* **Post Batch**
* **Preview Posting**

When you have completed all the lines and entered all the information on the sales order, you can post it. This creates a shipment and an invoice.

When a sales order is posted, the customer's account, the general ledger, and the item ledger entries are updated.

For each sales order, a sales entry is created in the **G/L Entry** table. An entry is also created in the customer's account in the **Cust. Ledger Entry** table and a general ledger entry is created in the relevant receivables account. In addition, posting the order may result in a VAT entry and a general ledger entry for the discount amount. Whether an entry for the discount is posted depends on the contents of the **Discount Posting** field in the **Sales & Receivables Setup** window.

For each sales order line, an item ledger entry will be created in the **Item Ledger Entry** table (if the sales lines contain item numbers) or a general ledger entry will be created in the **G/L Entry** table (if the sales lines contain a general ledger account). In addition to this, sales orders are always recorded in the **Sales Shipment Header** and **Sales Invoice Header** tables.

> [!IMPORTANT]  
>   When you post an order, you can create both a shipment and an invoice. These can be done at the same time or independently. You can also create a partial shipment and a partial invoice by completing the **Qty. to Ship** and **Qty. to Invoice** fields on the individual sales order lines before you post. Note that you cannot create an invoice for something that is not shipped. That is, before you can invoice, you must have recorded a shipment, or you must choose to ship and invoice at the same time.

When the posting is completed, the posted sales lines are removed from the order. A message tells you when the posting is completed. After this, you will be able to see the posted entries in the various windows that contain posted entries, such as the **Cust. Ledger Entries**, **G/L Entries**, **Item Ledger Entries**, **Posted Sales Shipments**, and **Posted Sales Invoices** windows.

## See Also
[Sales](sales-manage-sales.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

