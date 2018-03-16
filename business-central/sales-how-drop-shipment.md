---
title: Link a Sales Order to a Purchase Order for Direct Shipment | Microsoft Docs
description: Describes how to create a sales order linked to a purchase order to enable shipment directly from the vendor to the customer.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: direct shipment
ms.date: 01/25/2018
ms.author: sgroespe

---
# Make Drop Shipments
A drop shipment is the shipment of items from one of your vendors directly to one of your customers.

When a sales order is marked for drop shipment, and you create a purchase order specifying the customer in the **Sell-to Customer No.** field, you can link the two documents and thereby instruct the vendor to ship directly to the customer.

## To create a sales order for drop shipment
To prepare a drop shipment, you create a sales order for an item as normal, except you must indicate on the sales line that the sale requires drop shipment.

1. Create a sales order for an item. For more information, see [Sell Products](sales-how-sell-products.md).
2. On the sales order line for the drop shipment, select the **Drop Shipment** check box. Use the **Choose Columns** function if the field is not visible. For more information, see [Personalizing Your Workspace](ui-personalization-user.md).

## To create the purchase order for drop shipment
To prepare a drop shipment for the item to be sold, you create a purchase order as normal, except you must indicate on the purchase order that it must be shipped to your customer, not to yourself.

1. Create a purchase order. Do not fill any fields on the lines. For more information, see [Record Purchases](purchasing-how-record-purchases.md).
2. In the **Sell-to Customer No.** field, select the customer that you are selling to.
3. Choose the **Drop Shipments** action, and then choose the **Get Sales Order** action.
4. In the **Sales List** window, select the sales order that you prepared in the "To create a sales order for drop shipment" section.
5. Choose the **OK** button.

The line information from the sales order is inserted on the purchase order line(s).

You can now instruct the vendor to ship the items to your customer, for example, by mailing the purchase order as a PDF.     

## To view the linked purchase order from the sales order
* Select the drop-shipment sales order line, choose the **Order** action, choose the **Drop Shipment** action, and then choose the **Purchase Order** action.

## To post a drop shipment
After the vendor ships the items, you can post the sales order as shipped. You can also post the purchase order, but only with the **Receive** option until the sales order has been invoiced.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales orders**, and then choose the related link.
2. Open the sales order that you created in the "To create a sales order for a drop shipment" section.
3. In the **Qty. to Ship** field, specify how many of the order quantity to ship, the full or a partial order quantity.
4. Choose the **Post** or **Post and Send** action.
5. Choose either the **Ship** option to invoice later, or the **Ship and Invoice** option to invoice immediately.

## See Also
[Create Special Orders](sales-how-to-create-special-orders.md)|  
[Sell Products](sales-how-sell-products.md)  
[Record Purchases](purchasing-how-record-purchases.md)  
[Sales](sales-manage-sales.md)  
[Inventory](inventory-manage-inventory.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
