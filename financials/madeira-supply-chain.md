---
title: Supply Chain Features Supported by Financials| Microsoft Docs
description: Get a product overview and learn about key supply chain concepts and processes that are part of the ERP solution.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: product overview, ERP
ms.date: 06/02/2017
ms.author: sgroespe

---
# Overview of Supply Chain Functionality
[!INCLUDE[d365fin](includes/d365fin_md.md)] supports common supply chain processes, although limited to the needs of wholesale and distribution companies without managed warehouse handling.

In addition to sales invoice documents, you can manage your order fulfillment with sales orders allowing you to ship parts of an order quantity, for example, because the full quantity is not available at once. You can have items drop shipped directly from a vendor to a customer by linking the sales order to the related purchase order.

Your inventory quantities are dynamically updated as you sell and buy items, and availability information or warnings are shown to sales people in several ways. You can adjust inventory quantities manually by posting directly to the item ledger entries, for example, after a physical count. You can offer and sell items to your customers without maintaining inventory for them. If you want to include such nonstock items to your supply chain process, you simply convert them to normal items.

In addition to purchase invoice documents, you can manage your supply side with purchase orders allowing you to record partial receipts of an order quantity. A simple supply planning function allows you to initiate a purchase directly from the sales invoice that requires the items.

Both sales and purchase documents can be posted as shipped or received only or as shipped or received and invoiced, allowing you to split the responsibilities of order processors and accounting roles.

The following table describes a sequence of tasks, with links to the topics that describe them.

| To | See |
| --- | --- |
| Register new customers, make sales offers, sell products on orders or invoices, for example as drop shipments, and manage sales returns. |[Sales](sales-manage-sales.md) |
| Register new vendors, purchase items on orders or invoices, for example initiated from a sales invoice, and manage purchase returns. |[Purchasing](purchasing-manage-purchasing.md) |
| Register new physical or service products, adjust inventory quantities, and manage the inventory value by posting adjusted costs to the general ledger. |[Inventory](inventory-manage-inventory.md) |

## See Also
[Setting Up Sales](sales-setup-sales.md)  
[Managing Receivables](receivables-manage-receivables.md)     
[Setting Up Purchasing](purchasing-setup-purchasing.md)  
[Managing Payables](payables-manage-payables.md)    
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[General Business Functionality](ui-across-business-areas.md)
