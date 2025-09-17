---
title: Assign item charges to sales and purchases
description: Assign item charges when you need inventory items to carry added costs, such as freight and physical handling.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: transportation, added cost, landed cost
ms.search.form: 5709, 5800, 5805, 5814
ms.date: 06/17/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Use item charges to account for extra trade costs

To ensure correct valuation, your inventory items must carry any added costs, such as freight, physical handling, insurance, and transportation that you incur when purchasing or selling the items. For purchases, the landed cost of a purchased item consists of the vendor's purchase price and all other direct item charges that can be assigned to individual receipts or return shipments. For sales, knowing the cost of shipping sold items can be as vital to your company as knowing the landed cost of purchased items.

In addition to recording the added cost in your inventory value, you can use item charges for the following tasks:

* Identify the landed cost of an item for making more accurate decisions on how to optimize the distribution network.
* Break down the unit cost or unit price of an item for analysis purposes.
* Include purchase allowances into the unit cost and sales allowances into the unit price.

Before you can assign item charges, you must set up item charge numbers for the different types of item charges. The numbers include to which G/L accounts to post costs related to sales, purchases, and inventory adjustments. An item charge number contains a combination of general product posting group, tax group code, VAT product posting group, and item charge. When you enter the item charge number on a purchase or sales document, the G/L account is retrieved. The account retrieved is selected based on the setup of the item charge number and the information on the document.

For both purchase and sales documents, you can assign an item charge in two ways:

* On the document that lists the items that the item charge relates to. Typically, you use this method for documents that aren't yet fully posted.
* On a separate invoice by linking the item charge to a posted receipt or shipment where the items that the item charge relates to are listed.

> [!NOTE]  
> You can assign item charges to orders, invoices, and credit memos, for both sales and purchases. The following procedures describe how to work with item charges for a purchase invoice. The steps are similar for all other purchase and sales documents.

## Example

This video shows how to handle an extra shipping cost as part of inventory costing.
<br><br>  
> [!Video https://learn-video.azurefd.net/vod/player?id=35aa5336-39c8-46a2-b8eb-9ac925a17802]

## To set up item charge numbers

You use item charge numbers to distinguish between the different kinds of item charges.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Item Charges**, and then choose the related link.
2. On the **Item Charges** page, choose the **New** action to create a new line.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To assign an item charge directly to the purchase invoice for the item

If you know the item charge when you post a purchase invoice for the item, follow this procedure.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Purchase Invoices**, and then choose the related link.
2. Create a new purchase invoice. For more information, see [Record Purchases](purchasing-how-record-purchases.md).
3. Make sure the purchase invoice has one or more lines of type Item.
4. On a new line, in the **Type** field, select **Charge (Item)**.
5. In the **Quantity** field, enter the units of the item charge that you're invoiced for.
6. In the **Direct Unit Cost** field, enter the amount of the item charge.
7. Fill in the remaining fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    Do the following steps to perform the actual assignment. Until the item charge is fully assigned, the value in the **Qty. to Assign** field is in red font.
8. On the **Lines** tab, choose the **Item Charge Assignment** action.

    The **Item Charge Assignment** page opens showing one line for each line of type Item on the purchase invoice. To assign the item charge to one or more invoice lines, you can use a function that assigns and distributes it for you or you can manually fill in the **Qty. to Assign** field. The following steps describe how to use the Suggest Item Charge Assignment function.

9. On the **Item Charge Assignment** page, choose the **Suggest Item Charge Assignment** action.
10. If there are more than one invoice lines of type Item, choose one of the four distribution options.  

If the item charge is fully assigned, the value in the **Qty. to Assign** field on the purchase invoice is zero.

The item charge is now assigned to the purchase invoice. When you post the receipt of the purchase invoice, the items' inventory values are updated with the cost of the item charge.  

## To assign an item charge from a separate invoice to the purchase invoice for the item

If you received an invoice for the item charge after you posted the original purchase receipt, follow this procedure.

1. Repeat steps 1 through 8 in [To assign an item charge directly to the purchase invoice for the item](payables-how-assign-item-charges.md#to-assign-an-item-charge-directly-to-the-purchase-invoice-for-the-item).
2. On the **Item Charge Assignment** page, choose the **Get Receipt Lines** action.
3. On the **Purch. Receipt Lines** page, select the posted purchase receipt for the item that you want to assign the item charge to, and then choose the **OK** button.
4. Choose the **Suggest Item Charge Assignment** action.

The item charge on the separate purchase invoice is now assigned to the item on the posted purchase receipt. The item's inventory value updates with the cost of the item charge.

## Handle item charges for partial receipts

Let's explore an example of how to handle item charges for a partial receipt.

You have a purchase order with three lines:

* Two lines are for items.
* One line captures item charges allocated across the items by amount.

When the items are delivered, you find that one of the items is missing, so you can't mark that line as received. You can receive and post the purchase invoice for the second item only, and deal with the missing item later.

To handle the item cost for the partial receipt, on the **Item Charge Assignment** page, enter **0** in the **Quantity to Handle** field on the line for the missing item. Then, copy the value from the **Item Charge Qty. to Handle** field to the **Quantity to Invoice** field on the purchase order lines.

When you're ready to handle the item that was missing, update the **Quantity to Handle** field and post the order.

## Related information

[Managing Payables](payables-manage-payables.md)  
[Record Purchases](purchasing-how-record-purchases.md)  
[Invoice Sales](sales-how-invoice-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
