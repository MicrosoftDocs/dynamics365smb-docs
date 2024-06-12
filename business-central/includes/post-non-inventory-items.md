---
author: brentholtorf
ms.topic: include
ms.date: 09/21/2023
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

Warehouse employees can ship and receive non-inventory items along with physical goods on sales and purchase orders. Non-inventory items are intangibles, such as insurance or extra costs.

Sales and purchase orders often have various types of things on their lines. For example, orders might include general ledger items, accounts, and fixed assets. If you use warehouse documents to handle physical items, you can also post some types of non-inventory items. The following are examples of warehouse documents:

* Inventory put-aways
* Warehouse receipts
* Inventory picks
* Warehouse shipments

To enable warehouse workers to ship and receive non-inventory items, fill in the **Auto Post Non-Invt. via Whse.** field on the **Sales & Receivables Setup** and **Purchases & Payables Setup** pages. The field provides the following options:

|Option  |Description  |
|---------|---------|
|None     |Do not ship or receive non-inventory items.         |
|Attached/Assigned     | Post item charges and other non-inventory item lines that are assigned or attached to physical items. To attach non-inventory lines to physical items, use the **Attach to inventory line** action.        |
|All     | Post all non-inventory lines on the source document as soon as at least one item is posted by the warehouse document.        |

> [!NOTE]
> The **Complete** option in the **Shipping Advice** field of the sales order has priority over the selection in the **Auto Post Non-Invt. via Whse.** field on the **Sales & Receivables Setup** page.