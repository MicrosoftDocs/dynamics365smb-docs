---
title: Set up subcontractor prices
description: Learn how to set up and maintain subcontractor prices for work centers, including copying prices between vendors and filtering options.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: subcontracting, prices, work center, vendor
ms.search.form: 99001500,
ms.date: 06/10/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Set up subcontractor prices

You can store subcontractor prices and view all prices for each item at a glance. You can maintain subcontractor prices by assigning them to vendors, standard task codes, and work centers. You can access subcontractor prices from the vendor card.

## Set up subcontractor prices

The following steps describe how to set up subcontractor prices.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Subcontractor Prices**, and then choose the related link.
1. On the **General** FastTab, use the filters to find specific subcontractor prices. The following filters are available:

   - **Vendor No. Filter**
   - **Work Center No. Filter**
   - **Standard Task Code Filter**
   - **Item No. Filter**
   - **Starting Date Filter**

1. In the lines, fill in the following required fields:
   - **Work Center No.**
   - **Vendor No.**
   - **Item No.**

1. Fill in additional fields as needed:

   - **Standard Task Code** – Enter a standard task to scope the price to a specific activity for the work center.
   - **Variant Code** – Enter an item variant code if the price applies to a specific variant.
   - **Starting Date** and **Ending Date** – Define the date interval during which the price is valid.
   - **Unit of Measure Code** – Specify the unit of measure if the price differs from the item's base unit.
   - **Minimum Quantity** – Enter the minimum order quantity required to qualify for this price.
   - **Currency Code** – Specify the currency if the price isn't in the local currency. The currency defaults from the vendor card.
   - **Direct Unit Cost** – Enter the price per unit.
   - **Minimum Amount** – Enter the minimum amount per process. If the calculated amount based on order quantity is lower, the system adjusts the unit cost upward to meet this floor.

> [!NOTE]
> The **Work Center No.**, **Vendor No.**, and **Item No.** fields are required.

## Access subcontractor prices from other pages

You can also open the **Subcontractor Prices** page from the following pages by choosing the **Subcontractor Prices** action:

- **Vendor Card** or **Vendor List** – Opens prices filtered by the selected vendor.
- **Work Center Card** or **Work Center List** – Opens prices filtered by the selected work center. The action is available only for work centers that have a subcontractor assigned.
- **Item Card** or **Item List** – Opens prices filtered by the selected item.
- **Routing Lines** – Opens prices filtered by the work center and standard task code from the selected routing line.
- **Subcontracting Details FactBox** (on subcontracting purchase orders) – Shows the number of matching prices for the purchase line and lets you drill down to view them.

In each case, [!INCLUDE [prod_short](includes/prod_short.md)] prepopulates the relevant filters so you see only the prices that relate to the record you're working with.

## Copy prices between vendors

You can copy subcontractor prices from one vendor to another. This feature is useful when you negotiate similar terms with a new subcontractor and want to use an existing vendor's prices as a starting point.

1. On the **Subcontractor Prices** page, in the **Vendor No. Filter** field, enter the vendor that should receive the copied prices.
1. In the **Work Center No. Filter** field, enter the work center.

   > [!IMPORTANT]
   > Both the **Vendor No. Filter** and **Work Center No. Filter** must resolve to exactly one vendor and one work center. These values define the target for the copy.

1. Optionally, set the **Item No. Filter** to limit the lookup to a specific item.
1. Choose the **Copy Subcontractor Prices** action.

   [!INCLUDE [prod_short](includes/prod_short.md)] opens a lookup that shows prices from other vendors for the same work center. You can adjust the filters in the lookup to browse prices from different vendors or work centers.

1. Select the lines you want to copy.
1. Choose **OK**.

[!INCLUDE [prod_short](includes/prod_short.md)] copies each selected price line to the target vendor and work center. All other price details are preserved — item, variant, standard task code, dates, unit of measure, minimum quantity, currency, direct unit cost, and minimum amount. The **Vendor No.** and **Work Center No.** values are replaced with the target values from the filters. If a price line with the same key combination already exists, it's skipped.

## How price determination works

When [!INCLUDE [prod_short](includes/prod_short.md)] calculates the cost for a subcontracting operation - whether from the subcontracting worksheet, a production order routing, or a purchase order - it looks up the best matching price in the following way:

1. **Filter matching prices** by the vendor, item, variant, work center, standard task code, and currency from the order. The date must fall within the price line's **Starting Date** and **Ending Date** range.

   > [!NOTE]
   > A price line with a blank **Variant Code**, **Standard Task Code**, or **Currency Code** matches any variant, standard task, or currency, so it acts as a default. When both a specific and a blank match exist, the specific match takes priority because the system retrieves the last matching record by sort order.

1. **Select the quantity-break tier.** Among the matching prices, [!INCLUDE [prod_short](includes/prod_short.md)] finds the price line with the highest **Minimum Quantity** that is still less than or equal to the order quantity. This selects the most specific volume tier for the given quantity.

   > [!IMPORTANT]
   > The system picks the tier with the highest qualifying minimum quantity, not the tier with the lowest price. 

   For example, consider two price lines for the same vendor and item:

   | Minimum Quantity | Direct Unit Cost |
   |---|---|
   | 1 | 15.00 |
   | 50 | 18.00 |

   - **Order 5 units**: Only the Minimum Quantity = 1 tier qualifies. Direct Unit Cost = **15.00**.
   - **Order 80 units**: Both tiers qualify. The system picks Minimum Quantity = 50 (the highest qualifying tier). Direct Unit Cost = **18.00**, even though the Minimum Quantity = 0 tier offers a lower price of 15.00.

   This approach differs from standard purchase prices, where [!INCLUDE [prod_short](includes/prod_short.md)] compares all qualifying tiers and selects the best (lowest) price. 

1. **Apply the minimum amount floor.** After selecting the price line, the system checks whether the total cost (direct unit cost × quantity) meets the **Minimum Amount**. If the total is lower, the unit cost is automatically increased so the total equals the minimum amount:

   `Direct Unit Cost = Minimum Amount ÷ Quantity`

   This adjustment happens silently - no warning or confirmation is shown. It ensures the vendor receives at least the agreed minimum per production order, regardless of how few units are ordered.

1. **Convert units of measure.** If the price line's unit of measure differs from the production order's, the cost is converted proportionally using the item's unit of measure conversion factors.

1. **Convert currency.** If the price line uses a foreign currency, the cost is converted to the local currency using the exchange rate on the order date.

### Example: Quantity breaks with minimum amount

Consider a vendor with these price entries for an item:

| Minimum Quantity | Direct Unit Cost | Minimum Amount |
|---|---|---|
| 0 | 10.00 | 50.00 |
| 50 | 8.00 | |
| 100 | 5.00 | |

- **Order 30 units** → Minimum Quantity 0 tier applies → 30 × 10.00 = 300.00 ≥ 50.00 → unit cost stays **10.00**
- **Order 3 units** → Minimum Quantity 0 tier applies → 3 × 10.00 = 30.00 < 50.00 → unit cost becomes **16.67** (50.00 ÷ 3)
- **Order 60 units** → Minimum Quantity 50 tier applies → unit cost = **8.00**, total = 480.00
- **Order 100 units** → Minimum Quantity 100 tier applies → unit cost = **5.00**, total = 500.00

In this example, the minimum amount on the tier-0 line acts as a batch fee - the vendor charges at least 50.00 per order even if only a few units are needed. For larger orders that qualify for a volume discount (50+ or 100+ units), the totals are high enough that no minimum amount adjustment is needed.

> [!TIP]
> Use **Minimum Quantity** and **Minimum Amount** together to model real-world subcontracting agreements where vendors offer volume discounts but also charge a minimum batch fee for small orders.

## How indirect costs apply to subcontractor prices

The **Direct Unit Cost** field on the subcontractor price list represents the cost that you negotiate with your subcontractor, without any internal overhead. When [!INCLUDE [prod_short](includes/prod_short.md)] applies a price from the list, it uses the work center's **Indirect Cost %** and **Overhead Rate** to calculate the total cost:

`Unit Cost per = Direct Unit Cost × (1 + Indirect Cost % / 100) + Overhead Rate`

This formula means you enter the vendor's price in the price list, and [!INCLUDE [prod_short](includes/prod_short.md)] automatically adds your internal overhead on top. The same formula is used on routing lines, purchase lines, and throughout the production order.

The following table shows where each cost field appears and what it represents:

| Where | Field shown | What it includes |
|---|---|---|
| **Subcontractor Price list** | Direct Unit Cost | Vendor's agreed price only. No indirect cost. |
| **Routing line / Prod. order routing line** | Unit Cost per | Full cost: direct + indirect cost % + overhead rate. |
| **Subcontracting worksheet** | Direct Unit Cost | Vendor's price only (before overhead). |
| **Purchase order line** | Direct Unit Cost | Vendor's price only. Indirect Cost % and Overhead Rate are separate fields on the line. |
| **Purchase order posting** | Unit Cost (LCY) | Full cost: calculated from Direct Unit Cost + Indirect Cost % + Overhead Rate. Posted as separate direct cost and indirect cost value entries. |

> [!NOTE]
> On the production order routing line, the **Unit Cost per** field always includes indirect cost. If you manually enter or change the **Unit Cost per** value on a routing line, [!INCLUDE [prod_short](includes/prod_short.md)] back-calculates the **Direct Unit Cost** by removing the overhead:
>
> `Direct Unit Cost = (Unit Cost per - Overhead Rate) / (1 + Indirect Cost % / 100)`
>
> When using a subcontractor price list, you enter the direct cost (what you pay the vendor), and the system adds overhead automatically. When you edit the routing line directly, you work with the total unit cost and [!INCLUDE [prod_short](includes/prod_short.md)] derives the direct cost for you.

> [!TIP]
> If you set up indirect cost percentages or overhead rates on your subcontract work centers, make sure to account for this when you compare prices across vendors. Two vendors might have the same direct unit cost, but different overhead rates on their work centers lead to different total costs on the routing line.

## Related information

[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]