---
title: Use item charges to account for extra trade costs
description: Use item charges to assign costs such as freight, insurance, and duties to purchases (landed cost), or non-inventoriable costs on sales shipments.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: transportation, added cost, landed cost, freight, customs duty, insurance, import cost
ms.search.form: 5709, 5800, 5805, 5814
ms.date: 07/21/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Use item charges to account for extra trade costs

To ensure correct valuation, your inventory items must carry any added costs, such as freight, physical handling, insurance, and transportation that you incur when purchasing or selling the items. For purchases, the landed cost of a purchased item consists of the vendor's purchase price and all other direct item charges that can be assigned to individual receipts or return shipments. For sales, knowing the cost of shipping sold items can be as vital to your company as knowing the landed cost of purchased items.

Use item charges for tasks such as the following list:

* Calculate the landed cost of an item, including freight, customs duties, insurance, and handling fees.
* Make more accurate decisions on how to optimize the distribution network based on true item costs.
* Break down the unit cost or unit price of an item for analysis purposes.
* Include purchase allowances into the unit cost and sales allowances into the unit price.

Before you can assign item charges, you must set up item charge numbers for the different types of item charges. The numbers include to which G/L accounts to post costs related to sales, purchases, and inventory adjustments. An item charge number contains a combination of general product posting group, tax group code, VAT product posting group, and item charge. When you enter the item charge number on a purchase or sales document, the G/L account is retrieved. The account retrieved is selected based on the setup of the item charge number and the information on the document.

For both purchase and sales documents, you can assign an item charge in two ways:

* On the document that lists the items that the item charge relates to. Typically, you use this method for documents that aren't yet fully posted.
* On a separate invoice by linking the item charge to a posted receipt or shipment where the items that the item charge relates to are listed.

> [!NOTE]  
> You can assign item charges to orders, invoices, and credit memos, for both sales and purchases. The following procedures describe how to work with item charges for a purchase invoice. The steps are similar for all other purchase and sales documents.

## How landed cost affects inventory value and profitability

When you assign item charges to a purchase receipt, [!INCLUDE [prod_short](includes/prod_short.md)] increases the inventory value of the received items. Later, when you sell those items, the cost of goods sold (COGS) includes the item charges you assigned. This process gives you an accurate picture of the true profit margin on each sale.

For example, if you import 100 units at $10.00 each and assign $200 in freight and $100 in customs duty to the receipt, the landed cost per unit is $13.00 (purchase price + freight + duty). When you sell those units, the COGS reflects $13.00 per unit rather than just the $10.00 purchase price.

## Video example

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

    The **Item Charge Assignment** page opens showing one line for each line of type **Item** on the purchase invoice. To assign the item charge to one or more invoice lines, you can use a function that assigns and distributes it for you or you can manually fill in the **Qty. to Assign** field. The following steps describe how to use the **Suggest Item Charge Assignment** function.

9. On the **Item Charge Assignment** page, choose the **Suggest Item Charge Assignment** action.
10. If there are multiple invoice lines of type Item, choose one of the four distribution options:

    * **Equally** - Divides the item charge equally across all lines.
    * **By Amount** - Distributes the charge proportionally based on the amount on each line.
    * **By Weight** - Distributes the charge proportionally based on the net weight of items on each line.
    * **By Volume** - Distributes the charge proportionally based on the unit volume of items on each line.

    > [!NOTE]
    > The **By Weight** and **By Volume** options use the **Net Weight** and **Unit Volume** fields from the *Item** card. For an accurate distribution, make sure you fill in these fields.  

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

## Assign item charges to other document types

In addition to purchase receipts, you can assign item charges from a purchase invoice to several other posted document types. On the **Item Charge Assignment (Purch.)** page, use the following actions to select the target lines:

| Action | Target document | Typical use |
|--------|----------------|-------------|
| **Get Receipt Lines** | Posted purchase receipt | Freight, customs duties, insurance on purchased goods (landed cost). |
| **Get Transfer Receipt Lines** | Posted transfer receipt | Shipping costs incurred when transferring items between locations. |
| **Get Return Shipment Lines** | Posted return shipment | Costs related to returning items to a vendor, such as return freight. |
| **Get Sales Shipment Lines** | Posted sales shipment | Freight-out or packaging costs. |
| **Get Return Receipt Lines** | Posted return receipt | Costs related to receiving customer returns, such as handling fees. |

On the **Item Charge Assignment (Sales)** page, you can assign charges to posted sales shipment lines and posted return receipt lines.

### Non-inventoriable item charges

Whether an item charge affects inventory value depends on whether the target document represents an inventory increase or decrease:

* **Inventoriable** (increases inventory value) - Item charges assigned to documents that add items to inventory: purchase receipts, transfer receipts, and return receipts (items returned by customers).
* **Non-inventoriable** (doesn't affect inventory value) - Item charges assigned to documents that remove items from inventory: sales shipments and return shipments (items returned to vendors). [!INCLUDE [prod_short](includes/prod_short.md)] records these charges in the **Cost Amount (Non-Invtbl.)** field on the value entry.

Non-inventoriable charges don't appear on the balance sheet as inventory, but they do appear in the item's profit and sales statistics. This is useful when you incur costs that should be tracked per item for profitability analysis. For example:

* Freight-out costs on sales shipments
* Return shipping fees when sending items back to a vendor

For information about using item charges for restock fees and sales allowances on return orders, see [Create a restock charge](sales-how-process-sales-returns-orders.md#to-create-a-restock-charge).

## View posted item charges

When you post an item charge, [!INCLUDE [prod_short](includes/prod_short.md)] doesn't create a new item ledger entry. Instead, it creates a **value entry** linked to the original item ledger entry of the receipt or shipment. The **Cost Amount (Actual)** field on the item ledger entry is a FlowField that sums all related value entries, so it automatically reflects the added charge.

Each value entry also has a **Valuation Date** that determines which cost period the charge belongs to. For item charges, this date is the valuation date of the item ledger entry the charge is assigned to, not the posting date of the charge itself. For more information about how valuation dates affect average cost, see [Design Details: Average Cost](design-details-average-cost.md#setting-the-valuation-date).

You can verify posted charges in several ways:

* **From the posted invoice**  
 
  Open the posted purchase or sales invoice and choose the **Find entries...** action. Select **Value Entry**, and then choose the **Show** action. You can see which value entries were created for the item charge, including the amount and the item they were applied to.
* **From the item ledger entry**  

  Open the item ledger entry for the received item, and then choose **Value Entries**. The item charge appears as a separate value entry that's linked to the same item ledger entry as the original purchase, which shows you the total landed cost of the item.
* **From reports**  

  Run the **Item Charges - Specification** report to see all posted item charges broken down by inventory posting group and item. You can also use the **Cost Shares Breakdown** report to analyze how item charges contribute to the overall cost of goods sold.

> [!TIP]
> To see the G/L impact, use **Find entries...** on the posted invoice, and then choose **G/L Entry** to see which accounts the item charge was posted to. The account depends on the general posting setup linked to the item charge number.

## Item charges and cost adjustment

If you post an item charge after you sell the item, the cost of goods sold doesn't automatically reflect the new charge. Run the **Adjust Cost - Item Entries** batch job to forward the additional cost to the related outbound (sale) entries. The batch job recalculates the COGS so that your profit figures stay accurate.

This process applies to item charges assigned to purchase receipts, transfer receipts, and sales shipments. For more information about how cost adjustment works, see [Design Details: Cost Adjustment](design-details-cost-adjustment.md).

## Item charges on Standard Cost items

When you assign item charges to items that use the **Standard** costing method, the charge doesn't change the item's unit cost. Instead, [!INCLUDE [prod_short](includes/prod_short.md)] posts the difference as a purchase variance. The variance equals the item charge amount because the standard cost remains fixed. For more information, see [Design Details: Variance](design-details-variance.md).

## Related information

[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Adjust Item Costs](inventory-how-adjust-item-costs.md)  
[Design Details: Cost Adjustment](design-details-cost-adjustment.md)  
[Design Details: Inventory Posting](design-details-inventory-posting.md)  
[Process Sales Returns](sales-how-process-sales-returns-orders.md)  
[Assign Item Charges to Subcontracting Receipts](subcontract-item-charges.md)  
[Managing Payables](payables-manage-payables.md)  
[Record Purchases](purchasing-how-record-purchases.md)  
[Invoice Sales](sales-how-invoice-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
