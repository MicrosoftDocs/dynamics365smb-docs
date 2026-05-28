---
title: Assign item charges to subcontracting receipts
description: Learn how to assign item charges such as transport and packaging costs to subcontracting purchase receipts for accurate production order costing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: subcontracting, item charges, production order, capacity costs
ms.search.form: 99000886,
ms.date: 05/20/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Assign item charges to subcontracting receipts

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

You can assign item charges to subcontracting receipts to include costs such as transport, packaging, and other incidental expenses directly in your production order costs. When you post additional costs that should be distributed to subcontracting receipts, you can record them as a separate invoice with **Type** set to **Charge (Item)**. The item charges link to the capacity ledger entries of the production order.

## Turn on item charges for subcontracting

Before you can assign item charges to subcontracting receipts, you must turn on the feature.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Manufacturing Setup**, and then choose the related link.
2. In the **Subcontracting** section, turn on the **Item Charge to Subcontracting Purch. Receipt Lines** toggle.

After you turn on the feature, the **Get Receipt Lines for Subcontracting** action becomes available when you assign item charges.

## How item charges work with subcontracting

When you assign item charges to subcontracting receipts, [!INCLUDE [prod_short](includes/prod_short.md)] creates value entries differently than for standard item charges.

### Standard item charge assignment

When you assign item charges to regular purchase receipts, [!INCLUDE [prod_short](includes/prod_short.md)] creates value entries that:

- Reference item ledger entries.
- Use **Direct Cost** as the cost type.
- Affect inventory.

### Subcontracting item charge assignment

When you assign item charges to subcontracting receipts, [!INCLUDE [prod_short](includes/prod_short.md)] creates value entries that:

- Don't reference item ledger entries.
- Reference capacity ledger entries.
- Use **Direct Cost** as the cost type.
- Use **Production** as the order type.
- Have an invoiced quantity of 0 because the costs are capacity costs.

## Assign item charges to subcontracting receipts

Before you assign item charges to a subcontracting receipt, the following must be in place:

- A posted subcontracting purchase order.
- A purchase receipt with a subcontracting reference.

The following steps describe how to assign an item charge to a subcontracting receipt.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders** or **Purchase Invoices**, and then choose the related link.
2. Create a new purchase order or invoice.
3. On the lines, in the **Type** field, choose **Charge (Item)**.
4. Fill in the remaining fields on the line, such as the item charge, quantity, and unit cost. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]
5. Choose the **Item Charge Assignment** action.
6. On the **Item Charge Assignment** page, choose the **Get Receipt Lines for Subcontracting** action.

   [!INCLUDE [prod_short](includes/prod_short.md)] filters the receipt lines to show only subcontracting receipts.

7. Select the subcontracting receipt line, and then enter the quantity and amount to assign.
8. Close the **Item Charge Assignment** page.
9. Post the purchase order or invoice.

[!INCLUDE [prod_short](includes/prod_short.md)] creates the value entries and links them to the capacity ledger entries.

## About the Get Receipt Lines for Subcontracting action

The **Get Receipt Lines for Subcontracting** action simplifies the process of assigning item charges to subcontracting receipts. When you use the action, [!INCLUDE [prod_short](includes/prod_short.md)] filters purchase receipt lines to show only those related to subcontracting. Receipt lines must have values in the following fields to be included:

- **Production Order No.**
- **Routing No.**
- **Operation No.**

> [!NOTE]
> The **Get Receipt Lines for Subcontracting** action is only available when you turn on the **Item Charge to Subcontracting Purch. Receipt Lines** toggle on the **Manufacturing Setup** page.

## Value entries for subcontracting item charges

When you post an item charge assigned to a subcontracting receipt, [!INCLUDE [prod_short](includes/prod_short.md)] creates value entries with the following characteristics:

|Field|Value|
|-----|-----|
|Item Ledger Entry No.|0 (empty)|
|Capacity Ledger Entry No.|Reference to the capacity ledger entry|
|Order Type|Production|
|Order No.|Production order number|
|Invoiced Quantity|0|
|Cost Type|Direct Cost|

The costs are assigned directly to the production order and don't affect item inventories.

### Differences from standard item charges

The following table describes the differences between standard item charges and subcontracting item charges.

|Aspect|Standard item charge|Subcontracting item charge|
|------|-------------------|-------------------------|
|Item Ledger Entry No.|Filled|0 (empty)|
|Capacity Ledger Entry No.|0 (empty)|Filled|
|Order Type|Purchase|Production|
|Inventory impact|Yes|No|
|Cost distribution|Item|Capacity/Production order|

## Benefits of assigning item charges to subcontracting

Assigning item charges to subcontracting receipts offers the following benefits:

- **More accurate cost assignment** - Costs are assigned directly to production orders rather than to items.
- **Better cost separation** - Manufacturing costs are separated from material costs.
- **Improved calculation** - Manufacturing cost calculations are more precise.
- **Better reporting** - You can analyze subcontracting costs separately from item costs.
- **Better traceability** - You can track the total cost of subcontracting more easily.

## Examples

The following examples show how you can use item charges with subcontracting.

### Example 1: Transport costs

A subcontracting invoice includes 1,000 EUR for processing and 50 EUR for transport. You assign the transport costs as an item charge to the subcontracting receipt.

### Example 2: Packaging costs

Special packaging for sensitive parts costs 30 EUR in addition to 800 EUR for processing. You assign the packaging costs as an item charge for direct assignment to manufacturing costs.

### Example 3: Testing costs

Quality testing at the subcontractor costs 100 EUR in addition to 1,200 EUR for processing. You assign the testing costs as an item charge for better cost transparency.

## Things to consider

Keep the following in mind when you work with item charges for subcontracting:

- You must turn on the feature on the **Manufacturing Setup** page before you use it. After you turn it on, the feature only affects new postings.
- After you post an item charge to a subcontracting receipt, you can't reverse it.
- Make sure that you assign the item charge to the correct subcontracting receipt because the assignment affects cost distribution.
- Without the Subcontracting app, standard [!INCLUDE [prod_short](includes/prod_short.md)] doesn't support assigning item charges to purchase receipts for subcontracting operations. If you try to assign charges to a receipt line with a work center, you get an error. The Subcontracting app removes this limitation and routes the charges to capacity ledger entries instead of item ledger entries.

## Verify postings

To verify that [!INCLUDE [prod_short](includes/prod_short.md)] posted item charges correctly, check the value entries.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Value Entries**, and then choose the related link.
2. Filter the entries by the production order number.
3. Filter by **Cost Type** set to **Direct Cost**.
4. Verify that the **Capacity Ledger Entry No.** field is filled and the **Item Ledger Entry No.** field is empty.

The item charge costs appear in the production order cost overview under capacity costs.

## Related information

[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]